# Android Localization Toolkit Checklist

## Technical correctness
- Base locale is explicitly selected or reliably inferred.
- Keys remain aligned across locale resource files.
- Formatting placeholders match the base value exactly in type and indexed structure.
- XML escaping and markup remain resource-compiler safe.
- Resource/source-set scope is kept clear.

## Translation workbook
- Keys are never translated.
- Placeholders remain visible and unchanged.
- Missing or invalid values are marked rather than silently repaired.
- Different brand/flavour source sets are separated or labelled clearly.

## UI risk checks
- Review long labels in dialogs, tabs and buttons.
- Review RTL behaviour where relevant.
- Review font scaling and scrolling needs.
