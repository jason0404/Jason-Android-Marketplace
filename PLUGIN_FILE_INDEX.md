# Plugin Source File Index

本文件列出此 marketplace 内所有 plugin 的源码组成，便于上传 GitHub 后检查内容是否完整。

## Marketplace

```text
jason-android-plugins
```

## `android-review` (`0.2.0`)

### Skills

```text
/android-review:analyze-crash
/android-review:full-review-report
/android-review:localization-check
/android-review:release-check
/android-review:review-changes
/android-review:sdk-integration-check
```

### Agent files

```text
plugins/android-review/agents/android-build-release-reviewer.md
plugins/android-review/agents/android-correctness-reviewer.md
plugins/android-review/agents/android-html-report-generator.md
plugins/android-review/agents/android-lifecycle-reviewer.md
plugins/android-review/agents/android-resource-reviewer.md
```

### Required plugin files

```text
plugins/android-review/.claude-plugin/plugin.json
plugins/android-review/README.md
```

## `android-localization-toolkit` (`0.1.0`)

### Skills

```text
/android-localization-toolkit:check-ui-overflow
/android-localization-toolkit:export-excel
/android-localization-toolkit:full-localization-report
/android-localization-toolkit:import-excel
/android-localization-toolkit:validate-strings
```

### Agent files

```text
plugins/android-localization-toolkit/agents/android-localization-import-validator.md
plugins/android-localization-toolkit/agents/android-localization-report-generator.md
plugins/android-localization-toolkit/agents/android-localization-ui-reviewer.md
plugins/android-localization-toolkit/agents/android-localization-workbook-generator.md
plugins/android-localization-toolkit/agents/android-strings-auditor.md
```

### Required plugin files

```text
plugins/android-localization-toolkit/.claude-plugin/plugin.json
plugins/android-localization-toolkit/README.md
```

## `android-artifact-inspector` (`0.1.0`)

### Skills

```text
/android-artifact-inspector:check-signature
/android-artifact-inspector:compare-builds
/android-artifact-inspector:full-artifact-report
/android-artifact-inspector:inspect-aab
/android-artifact-inspector:inspect-apk
```

### Agent files

```text
plugins/android-artifact-inspector/agents/android-aab-analyzer.md
plugins/android-artifact-inspector/agents/android-apk-analyzer.md
plugins/android-artifact-inspector/agents/android-apk-signing-verifier.md
plugins/android-artifact-inspector/agents/android-artifact-comparator.md
plugins/android-artifact-inspector/agents/android-artifact-report-generator.md
```

### Required plugin files

```text
plugins/android-artifact-inspector/.claude-plugin/plugin.json
plugins/android-artifact-inspector/README.md
```
