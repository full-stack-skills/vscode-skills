---
name: vscode-project-init
description: Initialize a new VS Code Extension project using TypeScript.
license: Complete terms in LICENSE.txt
---

## When to use this skill

Use this skill when the user wants to start a new VS Code extension project. This is the first step in the development workflow.

## How to use this skill

1.  **Ask for Project Name**: If the user hasn't provided a name, ask for it (e.g., "my-awesome-extension").
2.  **Execute Initialization Command**: Run the following command to scaffold the project non-interactively.

```bash
# Replace <project-name> with the actual name
npx --package yo --package generator-code -- yo code <project-name> --template typescript --quick
```

3.  **Post-Initialization**:
    *   Change directory into the new project: `cd <project-name>`
    *   Explain the structure briefly:
        *   `src/extension.ts`: Main entry point.
        *   `package.json`: Manifest file.
    *   Run `npm install` (if not already done by the generator, though `--quick` usually handles it).

## Example Interaction

User: "Create a new vscode extension named helper"
Agent: 
"I'll initialize the project for you.
Running: `npx --package yo --package generator-code -- yo code helper --template typescript --quick`
...
Project created! You can now start adding features."

## 国内适配

- 支持中文文档和中文注释
- 示例代码兼容国内开发环境
- 提供中文 FAQ 和常见问题解答

## 能力边界

### ✅ 适用场景
- 当你需要使用此技能对应的技术栈时
- 当项目需要遵循最佳实践时
- 当需要快速上手或深入理解核心概念时

### ⚠️ 需要注意
- 复杂业务逻辑需要结合具体场景调整
- 性能优化需要根据实际数据量评估

### ❌ 不适用场景
- 不相关的技术栈或框架
- 需要完全自定义的特殊场景

## 使用流程

### Step 1: 环境准备
确保开发环境已安装必要的依赖和工具。

### Step 2: 配置初始化
根据项目需求进行基础配置。

### Step 3: 核心功能使用
按照示例代码实现核心功能。

### Step 4: 测试验证
运行测试确保功能正常。

### Step 5: 部署上线
完成开发后进行部署和监控。
