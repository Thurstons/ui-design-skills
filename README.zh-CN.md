# UI Design Skills

[English](README.md) | [简体中文](README.zh-CN.md)

一套面向 Codex 等 AI Coding Agent 的三阶段 UI 设计工作流，把模糊的自然语言反馈逐步转换为可执行规范，并对最终实现进行验收。

```text
用户白话
  ↓ ui-intent-translator
结构化 UI Design Brief
  ↓ ui-design-spec-generator
可执行 UI Design Specification
  ↓ 前端实现
页面 / 代码
  ↓ ui-design-reviewer
Spec vs Actual + Fix Plan
```

## Skills

| Skill | 解决的问题 | 主要产物 |
|---|---|---|
| `ui-intent-translator` | 用户真正想表达什么？ | UI Design Brief |
| `ui-design-spec-generator` | 页面具体应该怎样设计？ | UI Design Specification |
| `ui-design-reviewer` | 当前实现是否符合规范？ | Review Report、差异矩阵、修复计划 |

三个 Skill 职责彼此隔离：Translator 不输出 CSS 数值，Generator 不重新猜用户原意，Reviewer 不在验收时擅自改设计方向。

## 安装

将需要的 Skill 文件夹复制到 Codex 的个人 Skill 目录：

```bash
cp -R skills/ui-intent-translator ~/.codex/skills/
cp -R skills/ui-design-spec-generator ~/.codex/skills/
cp -R skills/ui-design-reviewer ~/.codex/skills/
```

重新打开 Codex 后即可显式调用：

```text
$ui-intent-translator 这个页面太挤了，按钮太多，看起来不高级，风格参考 OpenAI。
```

把输出继续交给下一阶段：

```text
$ui-design-spec-generator 根据下面的 UI Design Brief 生成可执行规范：...
```

实现完成后验收：

```text
$ui-design-reviewer 根据这份 UI Design Spec 审查当前页面截图和代码：...
```

Skills 默认允许自动发现；在意图明确时，Agent 也可自动选择相应 Skill。

## 仓库结构

每个 Skill 都包含：

- `SKILL.md`：核心工作流、职责边界和输出要求。
- `agents/openai.yaml`：Codex UI 展示信息和默认调用提示。
- `references/`：按需读取的术语、设计系统和审查规则。
- `schemas/`：机器可校验的 JSON Schema。
- `templates/`：可复制的 Markdown/YAML 输出模板。

## 设计原则

- 保留用户原话和明确约束，避免术语化过程中丢失意图。
- 将观察、解释、设计决策与实现验收分开。
- 所有设计数值都应有上下文、Design Token 或明确假设作为依据。
- Reviewer 必须区分“实现不符合规范”和“规范本身需要修订”。
- 没有证据时标记为 `unverified`，不把推测写成事实。

## 发布前

公开发布前请补充你选择的开源许可证，并根据实际使用反馈迭代术语表和规则。不要把单个项目的品牌 Token 写成所有项目都必须遵循的通用规则。
