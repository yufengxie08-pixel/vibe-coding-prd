# AI Product PRD Template

Use this template only when the user confirms the product is an AI product.

````md
# {产品名}

## 1. 需求定义

- 目标用户：
- 核心场景：
- 核心痛点：
- 产品形态：
- 本次目标：

## 2. 范围结论

- MVP 要做：
- 本期不做：
- 后续可做：

## 3. 功能清单

| 一级模块 | 二级功能 | 功能描述 | 优先级 | 阶段 |
| --- | --- | --- | --- | --- |
|  |  |  | P0/P1/P2 | MVP/v1.1/later |

## 4. 技术栈建议

### 4.1 总体推荐

- 前端：
- 后端：
- 数据存储：
- AI/模型：
- 部署方式：

### 4.2 推荐理由

- 为什么适合这个产品规模：
- 为什么适合这个开发时限：
- 为什么适合技术小白协作：

## 5. 核心原型框架

### 5.1 页面结构

- 页面 A：
- 页面 B：
- 页面 C：

### 5.2 核心页面低保真草图

```text
+--------------------------------------------------+
| Header                                           |
+-------------------+------------------------------+
| Left nav          | Main work area               |
| - item            | - input area                 |
| - item            | - result area                |
|                   | - actions                    |
+-------------------+------------------------------+
```

## 6. Agent 设计

### 6.1 Agent 角色

- 主 Agent：
- 子流程或子 Agent：

### 6.2 Agent 工作流

1. 用户输入：
2. 信息解析：
3. 决策或规划：
4. 工具调用：
5. 结果生成：
6. 异常处理：

### 6.3 Prompt 设计

- System prompt 要点：
- User prompt 模板：
- 输出格式约束：
- 失败重试规则：

### 6.4 Tool 体系

| Tool 名称 | 用途 | 输入 | 输出 | 是否必须 |
| --- | --- | --- | --- | --- |
|  |  |  |  | 是/否 |

### 6.5 风险与兜底

- 模型输出不稳定时：
- 工具失败时：
- 用户输入不完整时：

## 7. 明细功能设计

### 7.1 模块 A

- 触发条件：
- 处理逻辑：
- 输入输出：
- 边界情况：

### 7.2 模块 B

- 触发条件：
- 处理逻辑：
- 输入输出：
- 边界情况：

## 8. 验收标准

### 8.1 功能 A

- 当用户执行：
- 系统应表现为：
- 判定通过标准：

### 8.2 功能 B

- 当用户执行：
- 系统应表现为：
- 判定通过标准：
````

## Writing Rules

- Keep each section short and concrete.
- Prefer tables over long prose.
- Acceptance criteria must be action-result based.
- Do not write vague goals such as `体验良好` or `更加智能`.
