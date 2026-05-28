---
description: Check Android XML or Compose usage of translated strings for long-text, font scaling and RTL layout risks
disable-model-invocation: true
---

Review selected localisation strings together with the Android UI locations that display them.

## Workflow

1. Inspect flagged keys or selected layouts/composables.
2. Invoke `android-localization-ui-reviewer`.
3. Identify only evidence-backed risks: fixed widths/heights, clipping, inappropriate ellipsize, non-scrollable dialogs, missing RTL support or constrained button labels.
4. Provide focused XML/Compose correction recommendations.

Do not claim the translated wording is linguistically correct unless the user separately provides that review scope.
