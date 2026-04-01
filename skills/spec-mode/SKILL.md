---
name: "spec-mode"
description: "Drives AI to complete requirement development with spec as goal and checklist as guide. Invoke when starting a new feature with clear requirements or user mentions spec-mode/spec-driven development."
---

# Spec Mode Skill

## 这组 skill 的用途
驱动 AI 以 spec 为目标、checklist 为导线，完成完整的需求开发流程。

## 适用场景
- 需求明确、有一定规模的功能开发
- 小需求请使用 /plan 模式，不要用这组 skill

## 使用方式
| 场景 | 调用 |
|------|------|
| 开始新任务 | 参考 commands/init.md |
| 推进当前任务 | 参考 commands/advance.md |
| 需求发生变更 | 参考 commands/change.md |

## 文档生命周期规则
| 类型 | 长期保留 | 示例 |
|------|---------|------|
| 核心文档 | ✅ | spec.md、checklist.md |
| 设计文档 | ✅ | api-design.md、db-schema.md、test-cases.md |
| 决策记录 | ✅ | ADR-xxx.md |
| 临时文档 | ❌ | scratch.md、research.md、任何以 temp/draft 开头的文件 |

临时文档在对应 step 完成后必须删除。

## 目录约定
所有产出存放于 `.trae/documents/tasks/active/{任务ID}_{描述}/`
