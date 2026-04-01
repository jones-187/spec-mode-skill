# 命令：推进任务

## 触发时机
用户要求继续推进当前任务时。

## 执行规则

### 推进前检查
1. 读取当前任务目录下的 checklist.md
2. 找到第一个状态为 TODO 或 REOPENED 的 step
3. 检查其前置 step 是否全部 DONE（或 SKIPPED）
   - 未完成：标记当前 step 为 BLOCKED，停止并报告阻塞原因

### 执行当前 step
1. 将 step 状态改为 IN_PROGRESS
2. 逐一完成该 step 下的每个 check 项
3. **每个 check 项必须有可验证的产出**，不允许仅凭描述标记完成
4. 需要生成文档时，在 checklist 的 `📎 产出` 字段写入文件链接

### 完成判断
该 step 所有 check 项完成后：
1. 将 step 状态改为 DONE
2. 删除该 step 产生的所有临时文档
3. **ADR 触发检查**：本 step 中是否有重要技术决策？
   - 如果有，使用提问工具询问用户：
     "本步骤中存在以下决策：[列出决策]，是否需要生成 ADR 记录？"
   - 用户确认后，按 `templates/adr-template.md` 生成对应 ADR 文件
4. 展示当前 checklist 整体进度，等待用户指令继续

### 禁止行为
- 禁止一次推进多个 step
- 禁止在 check 项未全部完成时将 step 标记为 DONE
- 禁止跳过 BLOCKED 状态直接推进
