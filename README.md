# Jason Android Engineering Marketplace 中文文档

> 一个面向 Android 开发、质量检查与交付流程的 Claude Code Marketplace。  
> 该 Marketplace 聚焦代码 Review、多语言资源管理，以及 APK / AAB 构建产物检查。

---

## 1. 项目简介

`Jason-Android-Marketplace` 是一个专门为 Android 工程团队设计的 Claude Code 插件市场。它将常见的 Android 开发、发布前检查、本地化管理、构建产物验证等流程封装成可复用的 Claude Code Plugins / Skills，让团队可以通过统一的命令完成代码审查、Crash 分析、Release 检查、翻译资源审计和 APK / AAB 报告生成。

当前 Marketplace 覆盖三类真实 Android 工作流：

1. **代码与发布质量检查**
   - Kotlin 代码 Review
   - Android Lifecycle 检查
   - Crash 分析
   - Release Configuration Review
   - SDK Integration Check

2. **多语言资源管理**
   - `strings.xml` 审计
   - Excel 翻译流转
   - Placeholder 检查
   - 多语言 UI 溢出风险检查
   - 本地化 HTML 报告生成

3. **构建产物验证**
   - APK / AAB 信息检查
   - APK 签名检查
   - 构建差异比较
   - Release 交付 HTML 报告生成

---

## 2. Marketplace 信息

```text
Marketplace name: jason-android-plugins
Version:          0.3.0
Repository:       jason0404/Jason-Android-Marketplace
```

---

## 3. 当前包含的 Plugins

| Plugin | 当前版本 | 用途 |
|---|---:|---|
| `android-review` | `0.2.0` | Android 代码 Review、Crash 分析、Release 检查、HTML 报告 |
| `android-localization-toolkit` | `0.1.0` | 多语言资源审计、Excel 导入导出、UI 风险检查、HTML 报告 |
| `android-artifact-inspector` | `0.1.0` | APK / AAB 检查、APK 签名、构建比较、HTML 报告 |

---

## 4. Repository 结构

```text
Jason-Android-Marketplace/
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
├── PLUGIN_FILE_INDEX.md
├── INSTALL_AND_COPY_GUIDE.md
├── CHANGELOG.md
└── LICENSE
```

### 主要目录说明

| 路径 | 说明 |
|---|---|
| `.claude-plugin/` | Marketplace 元数据配置目录 |
| `plugins/` | 存放所有 Claude Code Plugins |
| `plugins/android-review/` | Android Review 插件 |
| `plugins/android-localization-toolkit/` | Android 多语言工具插件 |
| `plugins/android-artifact-inspector/` | APK / AAB 构建产物检查插件 |
| `templates/consumer-android-project/` | 给消费端 Android 项目复制使用的模板 |
| `CLAUDE.md` | Marketplace 或项目级 Claude 使用说明 |
| `claude.json.example` | 常见配置文件参考示例 |
| `PUBLISH_TO_GITHUB.md` | 发布到 GitHub 的说明 |
| `PLUGIN_FILE_INDEX.md` | Plugin 文件索引 |
| `INSTALL_AND_COPY_GUIDE.md` | 安装与复制指南 |

---

## 5. Plugin 1：Android Review

### 5.1 用途

`android-review` 用于 Android 项目的代码质量检查、Crash 分析、Release 配置检查、SDK 集成检查，以及最终 HTML Review 报告生成。

适合使用在：

- Android Release 前代码审查
- Pull Request Review
- Crash Log 分析
- Kotlin / Android Lifecycle 问题排查
- SDK 接入检查
- 发布前配置检查

### 5.2 Skills

```text
/android-review:review-changes
/android-review:analyze-crash
/android-review:release-check
/android-review:localization-check
/android-review:sdk-integration-check
/android-review:full-review-report
```

### 5.3 示例命令

```text
/android-review:review-changes Review the current Android git diff and identify lifecycle, crash, memory leak, and release-risk issues.
```

```text
/android-review:analyze-crash Analyze this Android crash log and explain root cause, affected code path, and recommended fix.
```

```text
/android-review:release-check Check this Android project before release, including build type, signing, analytics, push, SDK flags, and release configuration.
```

```text
/android-review:full-review-report Review the current Android git diff before release and generate the final HTML report.
```

### 5.4 报告输出

```text
android-review-reports/android-review-report-YYYYMMDD-HHmm.html
```

---

## 6. Plugin 2：Android Localization Toolkit

### 6.1 用途

`android-localization-toolkit` 用于 Android 多语言资源管理，尤其适合多国家、多品牌、多语言项目。

它可以帮助处理：

- `strings.xml` 资源审计
- Base locale 与其他 locale 对齐
- Placeholder 检查
- 缺失翻译检查
- Excel 翻译表导出
- Excel 翻译表导入
- UI 文案过长风险检查
- 多语言 HTML 报告生成

### 6.2 Skills

```text
/android-localization-toolkit:validate-strings
/android-localization-toolkit:export-excel
/android-localization-toolkit:import-excel
/android-localization-toolkit:check-ui-overflow
/android-localization-toolkit:full-localization-report
```

### 6.3 示例命令

```text
/android-localization-toolkit:validate-strings Validate all Android strings.xml files and report missing keys, duplicate keys, and placeholder mismatches.
```

```text
/android-localization-toolkit:export-excel Export all locale strings.xml files using values/strings.xml as the base locale and create a translation workbook.
```

```text
/android-localization-toolkit:import-excel Import translated Excel content back into Android strings.xml files while preserving placeholders.
```

```text
/android-localization-toolkit:check-ui-overflow Check translated Android strings for possible UI overflow risks.
```

```text
/android-localization-toolkit:full-localization-report Audit the locale resources in the app module and generate the final HTML report.
```

### 6.4 输出路径

```text
android-localization-output/
```

---

## 7. Plugin 3：Android Artifact Inspector

### 7.1 用途

`android-artifact-inspector` 用于检查 Android Release 产物，尤其适合发布前交付验证。

它可以帮助检查：

- APK 基本信息
- AAB 基本信息
- APK 签名信息
- Version Code / Version Name
- Package Name
- 构建差异
- Release 产物 HTML 报告

### 7.2 Skills

```text
/android-artifact-inspector:inspect-apk
/android-artifact-inspector:inspect-aab
/android-artifact-inspector:check-signature
/android-artifact-inspector:compare-builds
/android-artifact-inspector:full-artifact-report
```

### 7.3 示例命令

```text
/android-artifact-inspector:inspect-apk Inspect this APK and summarize package name, version, minSdk, targetSdk, permissions, and signing information: <APK path>
```

```text
/android-artifact-inspector:inspect-aab Inspect this AAB and summarize bundle metadata, package name, version, and release risk: <AAB path>
```

```text
/android-artifact-inspector:check-signature Check the signing certificate and fingerprint information for this APK: <APK path>
```

```text
/android-artifact-inspector:compare-builds Compare these two APK files and explain version, signing, permissions, and metadata differences: <old APK path> <new APK path>
```

```text
/android-artifact-inspector:full-artifact-report Audit this release APK and generate a final HTML delivery report: <APK path>
```

### 7.4 报告输出

```text
android-artifact-reports/android-artifact-report-YYYYMMDD-HHmm.html
```

---

## 8. 从 GitHub 安装 Marketplace

将本 repository push 到 GitHub 后，可以在 Claude Code 中执行：

```text
/plugin marketplace add jason0404/Jason-Android-Marketplace
```

然后安装需要的插件：

```text
/plugin install android-review@jason-android-plugins
/plugin install android-localization-toolkit@jason-android-plugins
/plugin install android-artifact-inspector@jason-android-plugins
```

---

## 9. 在 Android 项目中让团队自动发现 Plugins

Claude Code 的项目共享配置文件为：

```text
.claude/settings.json
```

本 repository 已提供可复制模板：

```text
templates/consumer-android-project/.claude/settings.json
templates/consumer-android-project/CLAUDE.md
```

### 操作步骤

1. 将模板配置复制到你的 Android 项目：

```text
templates/consumer-android-project/.claude/settings.json
```

复制到：

```text
<android-project>/.claude/settings.json
```

2. 将模板说明复制到 Android 项目根目录：

```text
templates/consumer-android-project/CLAUDE.md
```

复制到：

```text
<android-project>/CLAUDE.md
```

3. 将配置中的占位 repository 替换为实际 GitHub repository：

```text
jason0404/Jason-Android-Marketplace
```

> 注意：`claude.json.example` 是为了对应常见叫法而提供的复制参考文件；Plugin Marketplace 的团队共享生效配置应优先使用 `.claude/settings.json`。

---

## 10. 本地测试

在 Marketplace repository 根目录执行：

```bash
claude plugin validate .
claude plugin validate ./plugins/android-review
claude plugin validate ./plugins/android-localization-toolkit
claude plugin validate ./plugins/android-artifact-inspector
```

在任意 Android 项目中测试本地 Marketplace：

```text
/plugin marketplace add /absolute/path/to/Jason-Android-Marketplace
/plugin install android-review@jason-android-plugins
/plugin install android-localization-toolkit@jason-android-plugins
/plugin install android-artifact-inspector@jason-android-plugins
```

---

## 11. 发布与更新约定

当更新任一 Plugin 后，请遵循以下流程：

1. 修改对应 plugin 文件。
2. 提高该 plugin 的 `.claude-plugin/plugin.json` 中的 `version`。
3. 更新 `CHANGELOG.md`。
4. Push 到 GitHub。
5. 在 Claude Code 中执行：

```text
/plugin marketplace update jason-android-plugins
/reload-plugins
```

### 不应提交到 Marketplace Repository 的内容

请勿提交以下文件：

```text
APK
AAB
keystore
签名证书
生成的 HTML 报告
Excel 翻译输出
临时构建产物
```

这些内容应保留在业务项目或本地输出目录中。

---

## 12. 推荐团队使用场景

### 12.1 Release 前代码审查

```text
/android-review:full-review-report Review the current Android git diff before release and generate the final HTML report.
```

适合检查：

- Kotlin 代码风险
- Fragment / Activity 生命周期问题
- ViewModel / Coroutine 使用风险
- Memory Leak
- Release Flag
- SDK 配置
- Push / Analytics / Deep Link 配置

### 12.2 多语言翻译流转

```text
/android-localization-toolkit:export-excel Export all locale strings.xml files using values/strings.xml as the base locale and create a translation workbook.
```

适合流程：

```text
strings.xml
→ Excel 翻译表
→ 翻译团队处理
→ import-excel
→ validate-strings
→ full-localization-report
```

### 12.3 Release APK / AAB 交付检查

```text
/android-artifact-inspector:full-artifact-report Audit this release APK and generate a final HTML delivery report: <APK path>
```

适合检查：

- Package Name
- Version Code
- Version Name
- Signing Certificate
- Permissions
- 构建差异
- 发布风险

---

## 13. 推荐 Obsidian 笔记链接

如果你将本文档放入 Obsidian，可以加入以下关联笔记：

```text
[[Claude Code]]
[[Android Code Review]]
[[Android Localization]]
[[APK Release Checklist]]
[[AI Engineering Workflow]]
[[Release Management]]
[[Android Build Artifact]]
```

---

## 14. TODO

后续可以继续完善：

- [ ] 增加每个 Plugin 的完整示例输入与输出。
- [ ] 增加 HTML 报告截图。
- [ ] 增加 Android Release Checklist 模板。
- [ ] 增加 CI/CD 中调用 Claude Code 的示例。
- [ ] 增加多品牌 Android 项目使用范例。
- [ ] 增加常见错误排查，例如 plugin install 失败、marketplace update 失败。
- [ ] 增加版本发布规范。
- [ ] 增加团队成员 Onboarding 指南。

---

## 15. 总结

`Jason-Android-Marketplace` 的核心价值是把 Android 团队常见的质量检查、发布验证、本地化管理和构建产物审计流程，封装为可复用、可安装、可团队共享的 Claude Code Plugins。

它适合用于：

- Android Release 前检查
- Pull Request Review
- 多语言资源管理
- APK / AAB 交付检查
- Android 团队 AI 工程化流程建设

推荐将该 Marketplace 作为团队内部 Android AI Review 工作流的基础模板，并根据具体业务项目持续扩展新的 Skills 与 Reports。
