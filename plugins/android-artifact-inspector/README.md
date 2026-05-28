# Android Artifact Inspector Plugin

用于审计 Android APK / AAB 构建产物、验证 APK 签名、比较版本差异并生成 HTML 交付报告。

## Skills

```text
/android-artifact-inspector:inspect-apk
/android-artifact-inspector:inspect-aab
/android-artifact-inspector:check-signature
/android-artifact-inspector:compare-builds
/android-artifact-inspector:full-artifact-report
```

## 使用示例

```text
/android-artifact-inspector:inspect-apk Inspect this APK for package metadata, permissions, native libraries and release risks: <APK path>
```

```text
/android-artifact-inspector:compare-builds Compare these release APKs for certificate, permission, ABI and size changes: <old APK> <new APK>
```

## 使用的 Android 工具

Plugin workflow 会在可用时使用：

```text
apkanalyzer
apksigner
bundletool
```

工具必须通过 PATH、Android SDK 环境或用户指定路径定位，不应写死操作系统路径。

## HTML 输出

```text
android-artifact-reports/android-artifact-report-YYYYMMDD-HHmm.html
```
