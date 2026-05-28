# Android Artifact Inspector Tooling Guide

The plugin is designed for Windows, macOS and Linux and must not hard-code operating-system-specific SDK paths.

## Tools
- `apkanalyzer`: inspect APK metadata/content and compare APK composition.
- `apksigner`: verify APK signatures and display certificate information.
- `bundletool`: inspect Android App Bundles or produce local `.apks` sets from `.aab` files for further analysis.

## Discovery order
1. Tool available in PATH.
2. Android SDK paths available through environment/project context, such as `ANDROID_HOME`.
3. A tool path explicitly supplied by the user.
4. Report the tool as missing and limit conclusions.

## Important boundaries
- Do not install or execute unknown APK files during inspection.
- An AAB is not directly installable like an APK.
- `apksigner` is for APK verification, not for claiming an AAB has a verified APK signature.
