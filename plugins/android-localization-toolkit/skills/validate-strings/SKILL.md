---
description: Validate Android strings.xml locale resources for missing keys, placeholders, XML safety and scoped brand text risks
disable-model-invocation: true
---

Audit Android localization resources for the selected module, source set or flavour.

## Workflow

1. Find `src/**/res/values*/strings.xml` files within the requested scope.
2. Use the selected base locale or default `values/strings.xml` as the source of truth.
3. Keep separate source sets/flavours clearly separated; do not silently merge unrelated resource scopes.
4. Invoke `android-strings-auditor`.
5. When the user requests a deliverable, invoke `android-localization-report-generator`.

## Validate

- Missing and extra string keys.
- Duplicate keys and malformed XML.
- Placeholder signatures such as `%s`, `%1$s`, `%d`, `%f`, escaped `%`, newlines and formatted content.
- XML escaping, CDATA/HTML markup and Android build-safety risks.
- `translatable="false"` handling when applicable.
- Brand-keyword contamination only when the user provides intended/forbidden brand rules.
- Potential overflow or RTL risks only when matching UI layouts/composables can be inspected.

## Output

Provide locale folders inspected, issue counts, exact file/key findings, severity, recommended correction and any limits of the analysis.

Do not change translations unless explicitly asked.
