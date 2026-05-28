# Android Localization Toolkit Plugin

用于 Android `strings.xml` 多语言资源检查、翻译 Excel 工作簿流转、导入验证与 HTML 报告的 Claude Code plugin。

## Skills

```text
/android-localization-toolkit:validate-strings
/android-localization-toolkit:export-excel
/android-localization-toolkit:import-excel
/android-localization-toolkit:check-ui-overflow
/android-localization-toolkit:full-localization-report
```

## 使用示例

```text
/android-localization-toolkit:validate-strings Validate all locale resources against app/src/main/res/values/strings.xml.
```

```text
/android-localization-toolkit:export-excel Export locale strings into a styled XLSX workbook using English as the base locale.
```

## 输出

```text
android-localization-output/translation-workbook-YYYYMMDD-HHmm.xlsx
android-localization-output/localization-report-YYYYMMDD-HHmm.html
```

## 安全原则

- 不自动翻译资源内容。
- 导入前验证 placeholder 与 XML 内容。
- 不自动合并不同 brand 或 flavour scope 的资源。
- 不将结构检查误称为语言翻译质量检查。
