# Android Review Plugin

专用于 Android/Kotlin 项目的 Claude Code review plugin，提供代码审查、crash 分析、release 配置检查与最终 HTML 报告。

## Skills

```text
/android-review:review-changes
/android-review:analyze-crash
/android-review:release-check
/android-review:localization-check
/android-review:sdk-integration-check
/android-review:full-review-report
```

## 使用示例

```text
/android-review:review-changes Review the current Android git diff and report only evidence-backed findings.
```

```text
/android-review:full-review-report Review the current changes before release and generate the final HTML report.
```

## HTML 输出

```text
android-review-reports/android-review-report-YYYYMMDD-HHmm.html
```

## 包含的 Agents

| Agent | 用途 |
|---|---|
| `android-correctness-reviewer` | Kotlin correctness、状态流与运行时错误 |
| `android-lifecycle-reviewer` | Fragment/Activity lifecycle、Glide 与 memory leak |
| `android-build-release-reviewer` | Gradle、manifest、flavour 与 production release 风险 |
| `android-resource-reviewer` | XML/Compose resources 与 localization 风险 |
| `android-html-report-generator` | 最终 HTML 报告生成 |
