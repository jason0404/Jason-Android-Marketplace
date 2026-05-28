---
description: Review Android Firebase, Braze, AppsFlyer and deep-link integration for configuration and lifecycle problems
disable-model-invocation: true
---

Review Android third-party SDK and navigation integration code, focusing on Firebase Cloud Messaging, Braze, AppsFlyer, Android App Links and custom URI schemes.

## Check
- Token registration flow, user association, environment endpoint and initialization ordering.
- Manifest metadata, intent filters, schemes/hosts and assetlinks-related configuration.
- Deep-link parameter validation, routing correctness and unsafe external URI handling.
- Lifecycle-related observer, receiver or callback cleanup.
- Debug versus release and flavour-specific configuration leakage.
- Logging of tokens, identifiers or sensitive payload data.

## Output
Provide:
1. Integration scope found.
2. Confirmed issues with evidence and severity.
3. Configuration verification steps.
4. Suggested Kotlin or manifest patch snippets only where needed.
