# 安装与复制指南

## 上传此 Marketplace Repository

将整个 `android-review-marketplace` 文件夹上传到 GitHub。不要只上传 `plugins/`，因为根目录还需要：

```text
.claude-plugin/marketplace.json
README.md
CLAUDE.md
```

## 在 Claude Code 安装

```text
/plugin marketplace add YOUR_GITHUB_USERNAME/YOUR_REVIEWER_MARKETPLACE_REPO
/plugin install android-review@jason-android-plugins
/plugin install android-localization-toolkit@jason-android-plugins
/plugin install android-artifact-inspector@jason-android-plugins
```

## 分享给 Android 项目团队

将模板复制到实际 Android repository：

### macOS / Linux

```bash
mkdir -p /path/to/android-project/.claude
cp templates/consumer-android-project/.claude/settings.json /path/to/android-project/.claude/settings.json
cp templates/consumer-android-project/CLAUDE.md /path/to/android-project/CLAUDE.md
```

### Windows PowerShell

```powershell
New-Item -ItemType Directory -Force -Path C:\path\to\android-project\.claude
Copy-Item .\templates\consumer-android-project\.claude\settings.json C:\path\to\android-project\.claude\settings.json
Copy-Item .\templates\consumer-android-project\CLAUDE.md C:\path\to\android-project\CLAUDE.md
```

随后将 `.claude/settings.json` 内 GitHub repository placeholder 替换为实际 repository。
