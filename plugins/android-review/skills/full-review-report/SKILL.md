---
description: Run a complete Android review workflow and create a well-styled standalone HTML report as the mandatory final deliverable
disable-model-invocation: true
---

Run a comprehensive Android review for the user's provided scope, current changes, crash trace or requested build/flavour.

## Workflow

1. Determine the requested review scope from the user prompt or current git diff.
2. Use the relevant Android specialist agents to inspect the scope:
   - `android-correctness-reviewer` for Kotlin correctness and runtime behavior.
   - `android-lifecycle-reviewer` for lifecycle, Glide, callbacks, leaks and crash paths.
   - `android-build-release-reviewer` for Gradle, manifests, flavours and production delivery risks.
   - `android-resource-reviewer` for XML, Compose resources, localization and visible brand text.
3. Run only the specialist agents relevant to the actual scope. For a general pre-release or pull-request review, run all four.
4. Consolidate their findings, remove duplicates and retain only evidence-backed findings.
5. Produce a clear risk/release recommendation and focused verification checklist.
6. **Mandatory final step:** invoke the `android-html-report-generator` agent with the consolidated findings, scope, validation steps and release recommendation. This final stage must write a standalone HTML report under `android-review-reports/`.

## Rules

- Never generate the final HTML report before specialist analysis is completed.
- Do not omit the final HTML report unless file-writing permission is explicitly denied.
- If report writing is denied, still provide the consolidated review result and clearly say that the HTML file could not be created.
- Do not claim a build/test passed unless it was actually run successfully.
- Treat secrets, tokens and credentials as sensitive and redact them in the report.

## Final response format

Report:
- Review status and highest risk.
- Agents/tasks completed.
- HTML report output path.
- Build/test verification performed or still required.
