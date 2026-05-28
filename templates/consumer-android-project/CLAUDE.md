# Android Engineering Plugins

本项目使用团队维护的 Claude Code Android marketplace。

## 可使用的 Plugins

- `android-review`：Android code review、crash diagnosis、release safety 与 HTML 报告。
- `android-localization-toolkit`：`strings.xml` 检查、翻译 Excel 导入导出与 localization 报告。
- `android-artifact-inspector`：APK/AAB 检查、签名验证、构建产物比较与 HTML 报告。

## 团队约定

- 不在日志或报告中暴露 token、密钥、keystore 密码或 private key。
- 导入翻译前必须完成 placeholder 与 XML 验证。
- 检查 APK/AAB 时不要安装或执行未知构建产物。
- Release 结论必须基于实际检查结果，不得假设构建成功。
