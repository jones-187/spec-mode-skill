# Spec Mode Skill

[![GitHub stars](https://img.shields.io/github/stars/jones-187/spec-mode-skill?style=social)](https://github.com/jones-187/spec-mode-skill/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/jones-187/spec-mode-skill?style=social)](https://github.com/jones-187/spec-mode-skill/network/members)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Skill Version](https://img.shields.io/badge/version-1.0.0-green.svg)](https://github.com/jones-187/spec-mode-skill)

驱动 AI 以 spec 为目标、checklist 为导线，完成完整的需求开发流程。

## 特性

- 规范化需求管理 - 明确的目标边界、可量化的验收标准
- Checklist 驱动流程 - 9 个标准化步骤，自动识别阻塞和依赖
- 变更影响分析 - 自动识别受影响步骤，生成变更报告
- ADR 决策记录 - 自动识别技术决策，保留决策上下文

## 安装

```bash
npx skill install spec-mode
```

## 适用场景

**适合**：需求明确、有一定规模的功能开发；需要完整文档追溯的项目

**不适合**：小型需求、快速原型、简单 bug 修复（建议用 `/plan` 模式）

## 流程概览

| Step | 名称        | 产出              |
| ---- | --------- | --------------- |
| 1    | 需求确认      | spec.md         |
| 2    | 风险预审      | risk-review\.md |
| 3    | 设计        | 设计文档            |
| 4    | 原型确认      | 原型文件            |
| 5    | 测试用例      | test-cases.md   |
| 6    | 分阶段编码     | 代码实现            |
| 7    | 代码 Review | Review 记录       |
| 8    | 测试执行      | 测试报告            |
| 9    | 交付        | 完整交付物           |

## 目录约定

- 工作目录：`.trae/documents/tasks/active/{任务ID}_{描述}/`
- 归档目录：`archive/{YYYY-MM-DD}_{任务ID}_{描述}/`

## 核心规则

- 每个 check 项必须有可验证的产出
- 禁止一次推进多个 step
- 禁止在 check 项未完成时标记 step 为 DONE
- 禁止跳过 BLOCKED 状态直接推进

## 贡献

1. Fork 本仓库
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 开启 Pull Request

## 许可证

本项目采用 MIT 许可证 - 详见 [LICENSE](LICENSE) 文件。

## 致谢

感谢所有为这个项目做出贡献的开发者！

***

**Made with ❤️ by jones-187**
