---
description: Run a full Android localization audit and produce a professional standalone HTML report
disable-model-invocation: true
---

Run a complete technical localization audit.

## Workflow

1. Invoke `android-strings-auditor`.
2. Invoke `android-localization-ui-reviewer` when matching UI files are available or UI-risk review is requested.
3. Consolidate missing/extra keys, formatting blockers, XML/resource risks, UI risks and scoped brand findings.
4. Mandatory final step: invoke `android-localization-report-generator`.

## Output file

The final agent must create:

```text
android-localization-output/localization-report-YYYYMMDD-HHmm.html
```

Distinguish technical validation from human linguistic review, and do not invent translation accuracy findings.
