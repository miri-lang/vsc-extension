# AI Agent Guidelines for Miri VS Code Extension

Welcome, AI Agent. This directory contains the VS Code extension for the Miri programming language. When working here, apply the persona of a **VS Code Extension Developer and Tools Engineer**.

## 1. Project Overview & Architecture
- **Purpose**: Provides syntax highlighting (via TextMate grammars) and basic language configuration for `.mi` files.
- **Tools**: Built using standard VS Code extension capabilities (`package.json`, `tmLanguage.json`).

## 2. TextMate Grammars (`syntaxes/miri.tmLanguage.json`)
- The primary focus is correct syntax highlighting.
- Match tokens with the upstream [Miri compiler lexer](../src/lexer/token.rs).
- Use standard TextMate scopes (`keyword.control`, `storage.type`, `constant.numeric`, `entity.name.function`, `string.quoted`, etc.) to ensure compatibility across different VS Code themes.

## 3. Testing
- Testing syntax highlighting is mandatory.
- You must write or update tests in `tests/` using `vscode-tmgrammar-test`.
- After modifying the grammar, run `npm run test` and ensure the snapshot updates correctly.

## 4. Verification & Publish Prep
Before proposing changes, ensure:
1. `npm install` works.
2. `npm run test` passes.
3. The extension packages correctly using `npx vsce package`.

Remember to avoid generating extra files (`.vsix` should be matched by `.gitignore` and `.vscodeignore`). No random scripts should clutter the extension directory.
