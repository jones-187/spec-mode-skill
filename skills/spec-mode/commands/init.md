# 命令：初始化任务

## 职责
创建任务工作区，生成 spec 草稿和 checklist 骨架。
不执行任何流程步骤，流程从 checklist Step 1 开始驱动。

## 执行步骤

### Step 1：创建任务目录
在 `.trae/documents/tasks/active/` 下创建目录：
- 有任务 ID：`PROJ-123_功能描述`
- 无任务 ID：`2026-04-01_功能描述`

### Step 2：生成 spec 草稿
按 `templates/spec-template.md` 生成 `spec.md`。
状态标记为 `DRAFT`，不需要用户在此确认，确认动作在 checklist Step 1 中完成。

### Step 3：生成 checklist
按 `templates/checklist-template.md` 生成 `checklist.md`。
所有 step 状态初始化为 `TODO`。

### Step 4：完成提示
输出以下提示后停止，等待用户指令：

---
✅ 工作区已创建：{任务目录路径}
📄 spec.md 草稿已生成，待 Step 1 确认
📋 checklist.md 已生成，共 9 个 Step

下一步：执行 advance 命令，从 Step 1 需求确认开始。
---
