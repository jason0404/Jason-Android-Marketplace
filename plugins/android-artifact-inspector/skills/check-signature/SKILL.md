---
description: Verify Android APK signing certificates and compare signer fingerprints with apksigner
disable-model-invocation: true
---

Verify signing for one or more `.apk` files.

## Workflow
1. Confirm supplied files exist and are APKs.
2. Locate `apksigner` cross-platform through PATH or Android SDK build-tools locations.
3. Invoke `android-apk-signing-verifier`.
4. Use `apksigner verify --print-certs` when available.
5. Report verification status, signer count and certificate SHA-256 digest where returned.
6. When comparing APKs, state whether the confirmed certificate fingerprints match.
7. Generate an HTML report only when requested.

## Safety
Never request or expose keystore passwords or private signing material. Do not claim which Play Console key a certificate represents unless that evidence was separately provided.
