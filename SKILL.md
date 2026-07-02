---
name: vibe-coding-prd
description: 把需求、原始 PRD、竞品分析或飞书文档内容提炼成可直接发给 Claude Code 或 Codex 的精简 Vibe Coding PRD。当用户说“帮我写一个用来vibe coding的PRD”或想把想法整理成可直接编码的 PRD 时使用。
---

# Vibe Coding PRD

## Overview

Use this skill to turn messy product input into a short Markdown PRD that a coding agent can implement directly.

The skill must not guess hidden intent. At every key decision point, present 2-4 numbered options and wait for the user to reply with an option number before continuing.

## When to Use

Use this skill when the user wants to:

- write a PRD for vibe coding
- turn a requirement, raw PRD, or competitor analysis into an implementation-ready PRD
- strip business or stakeholder language from an engineering-facing PRD
- extract coding-relevant details from Feishu/Lark doc, wiki, markdown, or slides links

## Hard Rules

- Never infer what the user wants if a key product decision is still ambiguous.
- Every key node must end with a 2-4 option multiple-choice confirmation.
- Keep the final PRD concise, practical, and easy for Claude Code or Codex to execute.
- Remove low-signal sections such as vision statements, market sizing, org planning, and stakeholder narratives unless they directly change implementation.
- Output the final PRD as a complete Markdown document.
- If the user input is still unclear after clarification, stop and output `待确认项`, not a guessed PRD.

## Input Routing

### Step 1: Classify the input

Classify the user input into exactly one of these four types:

1. `明确需求`
2. `原始 PRD`
3. `竞品分析`
4. `信息不足`

Use these heuristics:

- `明确需求`: the input already contains a clear target user, scenario, pain point, and product shape
- `原始 PRD`: the input is an engineer-facing or stakeholder-facing PRD, often long, structured, or linked
- `竞品分析`: the input mainly compares products, features, or market examples
- `信息不足`: core problem, user, or product shape is missing

After classifying, ask the user to confirm with a 2-4 option choice. Use the question format in [references/question-flow.md](references/question-flow.md).

### Step 2: Read linked source material when needed

If the source is a link, read it before summarizing:

- Feishu/Lark docx or wiki links: use `lark-doc`
- Feishu/Lark markdown links: use `lark-markdown`
- Feishu/Lark slides links: use `lark-slides`

Only extract implementation-relevant information:

- target users
- usage scenarios
- user problems
- product scope
- feature constraints
- workflow details
- technical constraints
- acceptance signals

Discard or compress:

- business value narratives
- background repetition
- strategy slogans
- team ownership tables
- launch process notes

## Workflow

### Path A: Clear requirement

If the input is already a clear requirement, skip source extraction and move into feature design.

### Path B: Raw PRD

Read the source, then rewrite it into coding-agent language:

- keep only information needed to design and build
- convert vague statements into explicit open questions
- ask the user to confirm scope before writing the full PRD

### Path C: Competitor analysis

Convert the analysis into a candidate requirement set:

- what user problem the competitor solves
- what experience pattern is worth borrowing
- what should be copied, simplified, or ignored

Then confirm the target scope with the user before continuing.

### Path D: Information insufficient

Use the clarification flow in [references/question-flow.md](references/question-flow.md).

Do not continue into PRD drafting until the user has confirmed:

- who the user is
- what scenario this is for
- what pain point must be solved
- what product shape is expected
- whether this is an AI product

## PRD Construction Order

Once the requirement is clear, build the PRD in this order and confirm each major step with options:

1. `需求定义`
2. `功能清单与 MVP 优先级`
3. `技术栈建议`
4. `核心原型框架`
5. `明细功能设计`
6. `验收标准`

For the detailed questions and answer formats, read [references/question-flow.md](references/question-flow.md).

## Output Requirements

The final PRD must include:

- product name or working title
- requirement definition: user, scenario, problem, product shape
- feature list: level-1 module, level-2 feature, short description, priority, release phase
- MVP scope and excluded scope
- recommended tech stack with plain-language rationale
- core interface wireframe in low-fidelity text form
- detailed feature design
- explicit acceptance criteria per feature

Choose exactly one output template:

- AI product: read [references/prd-template-ai.md](references/prd-template-ai.md)
- Traditional product: read [references/prd-template-traditional.md](references/prd-template-traditional.md)

## Special Handling for AI Products

If the user confirms this is an AI product, the detailed design must include:

- agent roles or single-agent definition
- workflow steps
- prompt design
- tool system
- model or inference choices if relevant
- failure handling and fallback rules

Do not include this section for non-AI products.

## Acceptance Criteria Standard

Acceptance criteria must be observable and testable.

Good examples:

- `点击“新建任务”按钮后，出现包含标题、截止日期、优先级的表单弹窗`
- `输入一段 PRD 文本并提交后，30 秒内生成一份包含模块、优先级和验收标准的 Markdown PRD`

Bad examples:

- `体验良好`
- `界面简洁`
- `生成结果比较准确`

## Final Response Shape

When the PRD is ready, output only:

1. a short one-line status
2. the full Markdown PRD

Do not add long explanations after the PRD unless the user asks.
