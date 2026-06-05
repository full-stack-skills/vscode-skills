---
name: vscode-feature-command
description: Add a new command to the VS Code extension.
license: Complete terms in LICENSE.txt
---

## When to use this skill

Use this skill when the user wants to add a new functional command (e.g., "Hello World", "Format Text") to the extension.

## How to use this skill

Adding a command requires updates to two files: `package.json` and `src/extension.ts`.

### Step 1: Update `package.json`

Add the command definition to the `contributes.commands` array.

```json
// package.json
{
  "contributes": {
    "commands": [
      {
        "command": "extension.myCommand", // Unique ID
        "title": "My Extension: Do Something" // Display Name
      }
    ]
  }
}
```

### Step 2: Update `src/extension.ts`

Register the command in the `activate` function.

```typescript
// src/extension.ts
import * as vscode from 'vscode';

export function activate(context: vscode.ExtensionContext) {
    // ... existing code ...

    let disposable = vscode.commands.registerCommand('extension.myCommand', () => {
        // Implementation logic here
        vscode.window.showInformationMessage('Command executed!');
    });

    context.subscriptions.push(disposable);
}
```

## Best Practices

*   **Command ID Naming**: Use `extensionName.actionName` format to avoid conflicts.
*   **Async Handling**: If the command logic is asynchronous, use `async () => { await ... }`.
*   **Error Handling**: Wrap logic in try-catch blocks if it involves external operations.

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
