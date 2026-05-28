---
description: Inspect an Android App Bundle for modules, packaging, manifest risk and locally generated APK verification using bundletool
disable-model-invocation: true
---

Inspect the user's `.aab` release artifact.

## Workflow
1. Confirm the AAB path and record name and size.
2. Locate `bundletool` from a user-provided path or available project/environment context.
3. Invoke `android-aab-analyzer`.
4. Report confirmed package/version/module/native-library/manifest observations where available.
5. When requested and `bundletool` is available, generate a local `.apks` archive in an output directory for further APK inspection. Never overwrite the original AAB.
6. Invoke `android-artifact-report-generator` when an HTML deliverable is required.

## Rules
- An AAB is not an installable APK.
- Do not claim that `apksigner` verifies an AAB.
- If `bundletool` is missing, state the limitation instead of guessing.
