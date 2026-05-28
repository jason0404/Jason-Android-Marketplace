---
description: Check Android release readiness across flavours, Gradle, manifests, SDK metadata, R8 and production flags
disable-model-invocation: true
---

Perform a release-readiness review for the Android application and requested flavour/build type. If none is specified, infer candidates from Gradle files and clearly state the scope.

## Inspect when present
- `build.gradle`, `build.gradle.kts`, `gradle.properties`, `settings.gradle`.
- Base and flavour-specific `AndroidManifest.xml`.
- `proguard-rules.pro`, consumer rules and signing/version configuration.
- Source/resources containing `isOfficial`, `releaseDebugEnable`, `mappingFileUploadEnable`, `baseUrl`, `sandbox`, `debug`, `AF_STORE`, Firebase, Braze or AppsFlyer configuration.
- Application IDs, app names, deep-link schemes/hosts and brand resource overrides.

## Release checks
- Debug/test endpoints, logs, menus or feature flags enabled in release.
- Incorrect environment, signing, version, app ID or distribution-store metadata.
- Incorrect `AF_STORE`, Firebase/Braze/AppsFlyer settings or deep-link declarations.
- Brand leakage between VT, AU, PU, UM or any detected flavour names.
- Exported components, cleartext traffic, embedded secrets or unsafe WebView/URI handling.
- Missing R8/ProGuard rules or mapping-upload risks.

## Output format

# Release Readiness
- Target build:
- Result: PASS / PASS WITH WARNINGS / BLOCK RELEASE
- Highest risk:

# Blocking Issues
Include only genuine blockers and exact evidence.

# Warnings
Include non-blocking but actionable risks.

# Build Verification Checklist
Provide exact checks or commands appropriate to the detected Gradle setup.
