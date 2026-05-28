# Jason Android Engineering Marketplace for Claude Code

一个面向 Android 开发、质量检查与交付流程的 Claude Code marketplace。

当前 marketplace 聚焦三类真实工作流：

- **代码与发布质量**：Kotlin、lifecycle、crash、release configuration review。
- **多语言资源管理**：`strings.xml` 审计、Excel 翻译流转、placeholder 与布局风险。
- **构建产物验证**：APK/AAB 信息、APK 签名、构建差异与 HTML 交付报告。

## Marketplace 信息

```text
Marketplace name: jason-android-plugins
Version:          0.3.0
```

## 包含的 Plugins

| Plugin | 当前版本 | 用途 |
|---|---:|---|
| `android-review` | `0.2.0` | Android review、crash analysis、release check、HTML 报告 |
| `android-localization-toolkit` | `0.1.0` | Localization 审计、Excel 导入导出、UI 风险与 HTML 报告 |
| `android-artifact-inspector` | `0.1.0` | APK/AAB 检查、APK 签名、构建比较与 HTML 报告 |

## Repository 结构

```text
android-review-marketplace/
├── .claude-plugin/
│   └── marketplace.json
├── plugins/
│   ├── android-review/
│   ├── android-localization-toolkit/
│   └── android-artifact-inspector/
├── templates/
│   └── consumer-android-project/
│       ├── .claude/
│       │   └── settings.json
│       └── CLAUDE.md
├── CLAUDE.md
├── claude.json.example
├── PUBLISH_TO_GITHUB.md
├── CHANGELOG.md
└── LICENSE
```

## Plugin 1：Android Review

Skills：

```text
/android-review:review-changes
/android-review:analyze-crash
/android-review:release-check
/android-review:localization-check
/android-review:sdk-integration-check
/android-review:full-review-report
```

示例：

```text
/android-review:full-review-report Review the current Android git diff before release and generate the final HTML report.
```

报告输出：

```text
android-review-reports/android-review-report-YYYYMMDD-HHmm.html
```

## Plugin 2：Android Localization Toolkit

Skills：

```text
/android-localization-toolkit:validate-strings
/android-localization-toolkit:export-excel
/android-localization-toolkit:import-excel
/android-localization-toolkit:check-ui-overflow
/android-localization-toolkit:full-localization-report
```

示例：

```text
/android-localization-toolkit:export-excel Export all locale strings.xml files using values/strings.xml as the base locale and create a translation workbook.
```

```text
/android-localization-toolkit:full-localization-report Audit the locale resources in the app module and generate the final HTML report.
```

产出路径：

```text
android-localization-output/
```

## Plugin 3：Android Artifact Inspector

Skills：

```text
/android-artifact-inspector:inspect-apk
/android-artifact-inspector:inspect-aab
/android-artifact-inspector:check-signature
/android-artifact-inspector:compare-builds
/android-artifact-inspector:full-artifact-report
```

示例：

```text
/android-artifact-inspector:full-artifact-report Audit this release APK and generate a final HTML delivery report: <APK path>
```

报告输出：

```text
android-artifact-reports/android-artifact-report-YYYYMMDD-HHmm.html
```

## 从 GitHub 安装 Marketplace

将本 repository push 到 GitHub 后，在 Claude Code 中执行：

```text
/plugin marketplace add YOUR_GITHUB_USERNAME/YOUR_REVIEWER_MARKETPLACE_REPO
/plugin install android-review@jason-android-plugins
/plugin install android-localization-toolkit@jason-android-plugins
/plugin install android-artifact-inspector@jason-android-plugins
```

## 在 Android 项目中让团队自动发现 Plugins

Claude Code 当前正式的项目共享配置文件是：

```text
.claude/settings.json
```

本 repository 已提供可复制模板：

```text
templates/consumer-android-project/.claude/settings.json
templates/consumer-android-project/CLAUDE.md
```

操作方法：

1. 复制 `templates/consumer-android-project/.claude/settings.json` 到你的 Android 项目根目录下的 `.claude/settings.json`。
2. 将文件中的：

```text
YOUR_GITHUB_USERNAME/YOUR_REVIEWER_MARKETPLACE_REPO
```

替换为实际 GitHub repository，例如：

```text
hongxingpeng/android-review-marketplace
```

3. 将 `templates/consumer-android-project/CLAUDE.md` 复制到 Android 项目根目录，作为团队使用说明。

> `claude.json.example` 是为了对应常见叫法而提供的复制参考文件；Plugin marketplace 的团队共享生效配置应使用 `.claude/settings.json`。

## 本地测试

在 marketplace repository 根目录：

```bash
claude plugin validate .
claude plugin validate ./plugins/android-review
claude plugin validate ./plugins/android-localization-toolkit
claude plugin validate ./plugins/android-artifact-inspector
```

在任意 Android 项目中测试本地 marketplace：

```text
/plugin marketplace add /absolute/path/to/android-review-marketplace
/plugin install android-review@jason-android-plugins
/plugin install android-localization-toolkit@jason-android-plugins
/plugin install android-artifact-inspector@jason-android-plugins
```

## 发布与更新约定

- 更新任一 plugin 后，必须提高该 plugin 的 `.claude-plugin/plugin.json` 中的 `version`。
- Push 到 GitHub 后，用户可执行：

```text
/plugin marketplace update jason-android-plugins
/reload-plugins
```

- 请勿将 APK、AAB、keystore、生成报告或翻译输出提交到 marketplace repository。
