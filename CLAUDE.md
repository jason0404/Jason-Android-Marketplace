# Jason Android Reviewer Marketplace — Development Guide

这是一个 Claude Code plugin marketplace repository，用于分发 Android 工程工具。

## Marketplace 包含的 Plugins

1. `android-review`
   - Android Kotlin / lifecycle / crash / release review
   - HTML review report

2. `android-localization-toolkit`
   - `strings.xml` 技术检查
   - Excel 翻译工作簿导入/导出
   - placeholder 与 UI overflow 检查
   - HTML localization report

3. `android-artifact-inspector`
   - APK / AAB artifact inspection
   - APK signature verification
   - Build comparison
   - HTML artifact report

## Repository 修改规则

- 每个 plugin 必须保持独立，所有依赖文件放在自己的 plugin 目录中。
- 每次发布 plugin 更新时，提高对应 `.claude-plugin/plugin.json` 内的 `version`。
- 不把 APK、AAB、keystore、翻译产出文件或生成报告提交到此 marketplace 仓库。
- 修改后运行：
  - `claude plugin validate .`
  - `claude plugin validate ./plugins/<plugin-name>`

## 重要配置说明

`claude.json.example` 仅是便于复制的示例。团队项目实际应将 marketplace 自动发现与 plugin 启用配置写入：

```text
.claude/settings.json
```
