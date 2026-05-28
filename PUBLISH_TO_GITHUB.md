# 发布 Marketplace 到 GitHub

## 1. 使用原 Reviewer Marketplace Repository

这是对原 `android-review` marketplace 的扩展版本，建议覆盖或更新你原本存放 reviewer marketplace 的 GitHub repository，而不是另建不相关目录。

## 2. Push 更新

```bash
cd /path/to/android-review-marketplace

git add .
git commit -m "Add Android Localization Toolkit and Android Artifact Inspector plugins"
git push
```

## 3. Claude Code 安装或更新

首次添加：

```text
/plugin marketplace add YOUR_GITHUB_USERNAME/YOUR_REVIEWER_MARKETPLACE_REPO
/plugin install android-review@jason-android-plugins
/plugin install android-localization-toolkit@jason-android-plugins
/plugin install android-artifact-inspector@jason-android-plugins
```

已有 marketplace 时：

```text
/plugin marketplace update jason-android-plugins
/plugin install android-localization-toolkit@jason-android-plugins
/plugin install android-artifact-inspector@jason-android-plugins
/reload-plugins
```

## 4. 在 Android App Repository 提供团队配置

把以下模板复制到实际 Android app repository：

```text
templates/consumer-android-project/.claude/settings.json → <android-project>/.claude/settings.json
templates/consumer-android-project/CLAUDE.md            → <android-project>/CLAUDE.md
```

替换模板中的 GitHub repository placeholder 后提交到 Android app repository，团队成员信任该项目目录时即可看到 marketplace/plugin 安装提示。
