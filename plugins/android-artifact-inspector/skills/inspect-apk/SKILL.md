---
description: Inspect an Android APK for release metadata, permissions, components, native libraries, size and security concerns
disable-model-invocation: true
---

Inspect the user's APK as an untrusted build artifact. Do not install or run it.

## Workflow
1. Confirm the `.apk` path exists and record file name and file size.
2. Locate Android SDK tooling cross-platform: try tools available in PATH, then locations discoverable through `ANDROID_HOME`, then any path supplied by the user. Never hard-code a macOS path.
3. Invoke `android-apk-analyzer`.
4. Use `apkanalyzer` where available to gather package/version, manifest data, permissions, DEX/resources/files, ABI libraries and major size contributors.
5. Invoke `android-apk-signing-verifier` when signature confirmation is requested or needed for release delivery.
6. Invoke `android-artifact-report-generator` when the user requests a report or final deliverable.

## Rules
- Report only fields confirmed through tool output.
- Treat tokens, credentials and sensitive metadata as redacted content.
- List unavailable SDK tools as verification limitations.
- Never modify the input APK.

## Output
Provide the inspected artifact, tools used/unavailable, confirmed metadata, findings ordered by severity, verification steps and report path when generated.
