# AGENT.md

Quick onboarding notes for future AI agents working in this repository.

## Project at a glance

- VS Code theme extension: **QCD Theme**.
- Main theme definition: `themes/qcd.json`.
- Extension manifest/version: `package.json`.
- Release notes: `CHANGELOG.md`.

## Important files

- `themes/qcd.json`: UI colors, `semanticTokenColors`, and `tokenColors`.
- `package.json`: extension metadata and packaged file allowlist.
- `.github/workflows/release.yml`: builds VSIX and publishes GitHub Releases on `v*` tags.

## Local workflow

- Package extension: `vsce package` (or `npx @vscode/vsce package`).
- Check packaged files: `vsce ls`.
- This repo intentionally does **not** track VSIX binaries in git (`*.vsix` in `.gitignore`).

## Release workflow

1. Bump version in `package.json`.
2. Update `CHANGELOG.md`.
3. Commit and push to `main`.
4. Create/push tag like `v1.0.1`.
5. GitHub Action `Release VSIX` creates release and uploads `qcd-theme-*.vsix`.

## Syntax-highlighting gotcha

- Python `class`/`def` is semantically reported as `storage.type` but should be colored as a `keyword`.
