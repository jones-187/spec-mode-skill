# 命令：处理 Spec 变更

## 触发时机
用户提出需求变更，或在推进过程中发现 spec 需要修正时。

## 执行步骤

### Step 1：更新 spec.md
在 `变更历史` 表格追加一条记录：
| 日期 | 变更内容 | 原因 | 影响 Spec ID |
然后更新对应的 Spec ID 内容。

### Step 2：影响评估
扫描 checklist.md，找出所有关联了受影响 Spec ID 的 step：
- 状态为 DONE 的：改为 AFFECTED
- 状态为 IN_PROGRESS 的：改为 AFFECTED，停止当前工作
- 状态为 TODO 的：保持 TODO，但在备注中标注"受变更影响，执行前需重新评估"

### Step 3：展示影响报告
输出变更影响报告，格式：
---
📋 Spec 变更影响报告
变更内容：xxx
受影响 step：Step 3（DONE → AFFECTED）、Step 5（IN_PROGRESS → AFFECTED）
建议：Step 3 需重新执行；Step 5 需从头开始
---
等待用户确认处理方式后，将 AFFECTED 的 step 改为 REOPENED 并继续。

### Step 4：在 checklist 的变更记录中追加
| 日期 | 影响 Step | 处理方式 |
