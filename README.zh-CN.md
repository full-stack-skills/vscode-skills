<div align="center">

# vscode-skills

**VS Code extension development skills**

[![GitHub](https://img.shields.io/badge/github-full--stack--skills%2Fvscode-skills-green.svg)](https://github.com/full-stack-skills/vscode-skills)
[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](LICENSE)
[![Agent Skills](https://img.shields.io/badge/Agent%20Skills-兼容-purple.svg)](https://agentskills.io)

[English](./README.md) | 简体中文

</div>

---

## 📖 简介

**VS Code 技能** 是一组 AI 编码智能体技能，属于 [Full Stack Skills](https://github.com/partme-ai/full-stack-skills) 生态，由 [PartMe.AI](https://github.com/partme-ai) 维护。包含 **4 个技能**。

## 📦 安装

```bash
npx skills add full-stack-skills/vscode-skills
```

## 🎯 技能列表 (4)

| 技能 | 描述 |
|------|------|
| `vscode-deploy-package` | Package the extension into a .vsix file for distribution. |
| `vscode-feature-command` | Add a new command to the VS Code extension. |
| `vscode-feature-webview` | Add a Webview panel to display custom HTML content. |
| `vscode-project-init` | Initialize a new VS Code Extension project using TypeScript. |

## 🤖 支持的智能体

适用于 [Claude Code](https://code.claude.com)、[Codex](https://developers.openai.com/codex)、[Cursor](https://cursor.com)、[OpenCode](https://opencode.ai)、[Gemini CLI](https://geminicli.com)、[GitHub Copilot](https://github.com/features/copilot)、[Windsurf](https://codeium.com/windsurf) 及 [70+ 其他](https://agentskills.io/clients)。

### Claude Code 安装

**方式一：npx skills CLI（推荐）**

```bash
npx skills add full-stack-skills/vscode-skills
```

**方式二：手动安装**

```bash
git clone https://github.com/full-stack-skills/vscode-skills.git
cp -r vscode-skills/skills/* .claude/skills/
```

更多详情请参阅 [Claude Code 技能指南](https://code.claude.com/docs/en/skills) 和 [Agent Skills 规范](https://agentskills.io/)。

## 📄 License

Apache 2.0
