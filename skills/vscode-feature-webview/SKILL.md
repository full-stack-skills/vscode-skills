---
name: vscode-feature-webview
description: Add a Webview panel to display custom HTML content.
license: Complete terms in LICENSE.txt
---

## When to use this skill

Use this skill when the user needs a custom UI (forms, charts, complex layouts) that cannot be achieved with standard VS Code UI elements.

## How to use this skill

1.  **Register Command**: First, create a command (using `vscode-feature-command`) that will open the webview.
2.  **Implement Webview Logic**: In the command callback, create the panel.

### Code Template

```typescript
import * as vscode from 'vscode';

export function activate(context: vscode.ExtensionContext) {
    let currentPanel: vscode.WebviewPanel | undefined = undefined;

    context.subscriptions.push(
        vscode.commands.registerCommand('extension.showWebview', () => {
            const columnToShowIn = vscode.window.activeTextEditor
                ? vscode.window.activeTextEditor.viewColumn
                : undefined;

            if (currentPanel) {
                // If we already have a panel, show it in the target column
                currentPanel.reveal(columnToShowIn);
            } else {
                // Otherwise, create a new panel
                currentPanel = vscode.window.createWebviewPanel(
                    'catCoding', // Identifies the type of the webview. Used internally
                    'Cat Coding', // Title of the panel displayed to the user
                    columnToShowIn || vscode.ViewColumn.One, // Editor column to show the new webview panel in.
                    {
                        enableScripts: true // Enable JS in the webview
                    }
                );

                currentPanel.webview.html = getWebviewContent();

                // Reset when the current panel is closed
                currentPanel.onDidDispose(
                    () => {
                        currentPanel = undefined;
                    },
                    null,
                    context.subscriptions
                );
            }
        })
    );
}

function getWebviewContent() {
    return `<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cat Coding</title>
</head>
<body>
    <img src="https://media.giphy.com/media/JIX9t2j0ZTN9S/giphy.gif" width="300" />
    <h1>Hello Webview</h1>
</body>
</html>`;
}
```

## Security Note

Always use `vscode-resource:` scheme for local content and Content Security Policy (CSP) in production.

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
