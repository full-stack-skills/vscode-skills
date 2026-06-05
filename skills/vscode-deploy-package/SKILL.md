---
name: vscode-deploy-package
description: Package the extension into a .vsix file for distribution.
license: Complete terms in LICENSE.txt
---

## When to use this skill

Use this skill when the development is complete and the user wants to install the extension or share it.

## How to use this skill

1.  **Install `vsce`**: Ensure the packaging tool is installed.
    ```bash
    npm install -g vsce
    ```
2.  **Package**: Run the package command in the project root.
    ```bash
    vsce package
    ```
3.  **Result**: This generates a `.vsix` file (e.g., `my-extension-0.0.1.vsix`).

## Pre-flight Checklist

Before packaging, ensure:
*   `package.json` has a valid `publisher` field. (If not, user can use any string for local testing, e.g., "local").
*   `README.md` is updated.
*   `CHANGELOG.md` is updated.
*   No strict linting errors prevent compilation.

## Installation

To install the `.vsix` file:
*   **GUI**: Open VS Code Extensions view -> "..." menu -> "Install from VSIX..."
*   **CLI**: `code --install-extension my-extension-0.0.1.vsix`

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
