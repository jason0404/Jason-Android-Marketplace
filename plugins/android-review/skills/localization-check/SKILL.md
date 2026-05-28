---
description: Audit Android strings.xml localization consistency, placeholders, locale qualifiers and brand leakage
disable-model-invocation: true
---

Review Android localization resources using the default `values/strings.xml` file as the base reference unless the project indicates a different source of truth.

## Check
- Missing and extra string keys across locale folders.
- Duplicate keys and inconsistent resource naming.
- Placeholder mismatches including `%s`, `%1$s`, `%d`, formatted HTML and `${app_name_normal}` style brand substitutions.
- Incorrect Android locale qualifiers, such as regional variants.
- Hardcoded user-visible strings in XML or Kotlin where discoverable.
- Escaping problems with apostrophes, ampersands, CDATA or markup.
- Brand text leaking into the wrong flavour.
- Translation expansion risks in dialogs, tabs, buttons and fixed-size layouts.

## Output format

# Localization Summary
- Base locale:
- Locales inspected:
- Missing keys:
- Placeholder risks:
- Brand leakage risks:

# Findings
For every issue include severity, resource file, key, affected locale/flavour, evidence and correction.

# Fix Order
Prioritize runtime formatting crashes and brand leakage before completeness or visual issues.
