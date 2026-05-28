---
description: Safely import approved translations from an XLSX workbook into Android strings.xml after validation
disable-model-invocation: true
---

Apply reviewed translations from a workbook into selected Android locale resources.

## Workflow

1. Identify the workbook path, base locale, target resource scope and locale-column mapping.
2. Invoke `android-localization-import-validator`.
3. Block any invalid row before writing:
   - key absent from base resources
   - placeholder mismatch
   - malformed XML/escaping
   - ambiguous locale folder mapping
   - unintended update to base/source text
4. On explicit approval to import, update only confirmed target-locale values.
5. Re-run `android-strings-auditor` against changed resources.
6. Optionally invoke `android-localization-report-generator`.

## Safety rules

- Never rename or delete base keys automatically.
- Preserve Android placeholders, markup and resource metadata.
- Keep the diff minimal and deterministic.
- List each modified locale file and number of changed values.
