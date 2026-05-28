---
description: Export Android strings.xml resources to a translator-friendly XLSX workbook with missing-key and placeholder-risk tracking
disable-model-invocation: true
---

Create a structured translation workbook from Android string resources.

## Workflow

1. Locate the requested Android resource scope and establish the base locale.
2. Invoke `android-strings-auditor` before export.
3. Invoke `android-localization-workbook-generator` to write an `.xlsx` workbook under:
   `android-localization-output/translation-workbook-YYYYMMDD-HHmm.xlsx`
4. Summarize the output workbook and technical issues detected.

## Workbook requirements

- Base locale key order determines row order.
- Columns must include `key`, base text, each locale, `placeholder_signature`, `status`, and `notes`.
- Preserve placeholders, escaped content and raw Android resource keys.
- Mark missing values and placeholder mismatches clearly.
- Use readable header styling, auto-filter, frozen header row and suitable widths.
- When source sets represent different product/flavour contexts, separate or clearly label them.

Do not translate text automatically and do not modify source XML files.
