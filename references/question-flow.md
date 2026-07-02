# Question Flow

Use this file when the requirement is ambiguous or when a major product decision needs confirmation.

## General Rule

Each key node must:

1. summarize the current understanding in 1-2 lines
2. present 2-4 numbered options
3. ask the user to reply with the option number

Use this exact shape:

```md
当前我理解的是：...

请确认这一项：
1. ...
2. ...
3. ...
4. ...

回复选项编号即可，我再继续下一步。
```

## Classification Confirmation

After the first pass, confirm the input type with:

```md
我先判断这份内容更接近：

1. 明确需求：已经能直接进入功能设计
2. 原始 PRD：需要从长文档里提炼编码所需信息
3. 竞品分析：需要先转成自己的产品需求
4. 信息不足：要先补齐用户、场景和痛点

回复选项编号即可。
```

## Clarification Questions for Unclear Input

Ask these in order, one node at a time.

### 1. Target user

```md
先确认这是谁要用的：

1. 个人用户
2. 小团队/工作协作场景
3. 企业内部系统
4. 还不确定，需要你帮我缩小范围
```

### 2. Usage scenario

```md
这个产品最核心的使用场景更接近：

1. 高频日常操作
2. 低频但复杂任务
3. 内容生成/信息整理
4. 数据录入/查询/管理
```

### 3. Core pain point

```md
你最想解决的问题更接近：

1. 现在太费时间
2. 现在流程太乱，容易出错
3. 现在信息太分散，很难整理
4. 现在不会做，需要 AI 或系统代劳
```

### 4. Product shape

```md
你想要的产品形态更接近：

1. Web 页面/后台
2. AI 工具或 Agent
3. 表单/工作流工具
4. 还没想好，需要你给建议
```

### 5. Delivery pressure

```md
开发节奏更接近：

1. 先做一个 1-3 天内能跑起来的 MVP
2. 先做一版 1-2 周可交付的产品
3. 可以做完整一些，优先考虑可扩展性
4. 还不确定，你来帮我平衡
```

## Feature Priority Confirmation

After drafting feature modules, ask:

```md
我先把功能拆成了一个候选清单。请确认你想怎么排优先级：

1. 先只做 MVP，能闭环即可
2. MVP + 1 个增强功能
3. 直接做较完整版本
4. 你先给我推荐一版最合理的优先级
```

Then show a flat table or list with:

- 一级模块
- 二级功能
- 说明
- 建议优先级
- 建议阶段：MVP / v1.1 / later

## Tech Stack Confirmation

After recommending the stack, ask:

```md
技术方案我建议这样选，请确认方向：

1. 优先简单好做，技术成熟即可
2. 优先开发速度，方便快速上线
3. 优先后续扩展性
4. 你给我保守推荐，不要太复杂
```

## Wireframe Confirmation

After drafting the text wireframe, ask:

```md
核心界面我先按这个框架设计。你更希望下一步：

1. 保持这个结构，继续写详细 PRD
2. 调整页面布局后再继续
3. 减少页面数量，先聚焦 MVP
4. 增加一个关键页面或关键区域
```

## AI Product Confirmation

If the product may be AI-native, ask:

```md
这个产品里 AI 的角色更接近：

1. AI 只是一个辅助功能
2. AI 是核心工作流的一部分
3. 这是一个以 Agent 为核心的产品
4. 暂时不要做 AI 版本
```

## Stop Condition

If the user still cannot confirm the basics, stop and output:

```md
# 待确认项

- 目标用户：
- 核心场景：
- 核心痛点：
- 产品形态：
- MVP 时间要求：

以上信息未确认前，不继续生成正式 PRD。
```
