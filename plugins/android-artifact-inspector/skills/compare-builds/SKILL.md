---
description: Compare two Android APK or AAB artifacts for release-significant differences and generate a comparison report
disable-model-invocation: true
---

Compare the two supplied artifacts.

## Workflow
1. Detect whether each input is APK or AAB.
2. Invoke the relevant analysis agent for each artifact.
3. For APKs, use `apkanalyzer` when available and `apksigner` for certificate comparison.
4. For AABs, use `bundletool` where available.
5. Invoke `android-artifact-comparator` to consolidate differences.
6. Invoke `android-artifact-report-generator` to generate the final HTML comparison report unless the user explicitly requests text only.

## Compare
- File size and major composition changes.
- Package/version/SDK metadata.
- Permissions, exported components and deep links when confirmed.
- Native libraries and ABI changes.
- APK certificate fingerprint match/mismatch.
- AAB modules or delivery differences when confirmed.

Clearly label expected differences, warnings, blockers and unknowns.
