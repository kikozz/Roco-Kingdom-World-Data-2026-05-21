# Roco Kingdom World Data 2026-05-24 Pak Split

This directory keeps files from each pak chunk separated.
No same-path files are merged together.

Pak folders:
- `pakchunk4-WindowsNoEditor`
- `pakchunk4-WindowsNoEditor_0_P`
- `pakchunk4-WindowsNoEditor_1_P`

Each pak folder keeps the decoded repo-style structure: `Bin/`, `Config/`, `PB/`, `_logs/`.
When a data file needs a schema that is not present in the same pak, only the schema is used for decoding and the source is recorded in `_logs/schema_usage.csv`.
