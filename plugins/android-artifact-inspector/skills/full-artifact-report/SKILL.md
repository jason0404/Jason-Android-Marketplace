---
description: Run a full APK or AAB release artifact audit and generate a styled standalone HTML report as the final deliverable
disable-model-invocation: true
---

Perform a complete release-artifact audit.

## Workflow
1. Identify artifact type(s) and the user's requested comparison/release context.
2. For APK files invoke `android-apk-analyzer` and `android-apk-signing-verifier`.
3. For AAB files invoke `android-aab-analyzer`, using `bundletool` where available.
4. For multiple files invoke `android-artifact-comparator`.
5. Consolidate evidence-backed findings and determine result: `PASS`, `PASS WITH WARNINGS`, `BLOCK RELEASE`, or `INCOMPLETE VERIFICATION`.
6. Mandatory final step: invoke `android-artifact-report-generator`, writing a standalone HTML report under `android-artifact-reports/`.

## Rules
- Do not install or execute supplied artifacts.
- Do not overwrite artifacts.
- Do not claim a tool result that was not obtained.
- Redact any sensitive values encountered.
