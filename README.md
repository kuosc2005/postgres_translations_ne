# NDFP Nepali PostgreSQL Message Draft v0.1

This package contains AI-assisted controlled Nepali draft translations for **all PostgreSQL message components present in the supplied pgtranslation/messages snapshot**.

This is **not a final translation** and must not be submitted upstream as-is. Native Nepali review and PostgreSQL technical review are required.

## Scope

- Components: 29
- Draft entries: 12008
- Plural entries: 73
- Entries marked `[REVIEW: ...]`: 7971
- Placeholder issues detected by local checker: 0

## Components

See `stats/component_stats.tsv`.

## Method

The generator uses a conservative controlled-draft policy:

1. simple operational messages are translated into Nepali where confidence is reasonable;
2. technical PostgreSQL terms, SQL keywords, utility names, options, and placeholders are preserved;
3. hard semantic terms are marked with `[REVIEW: term]`;
4. long help strings, complex sentences, or mostly untranslated messages are marked `[REVIEW: ...]`;
5. placeholders are checked after generation.

This is intentionally not a fully polished Nepali translation. It is a work-saving pre-review layer.

## Review workflow

1. Review `glossary/NDFP_NEPALI_GLOSSARY_v0_1.md`.
2. Review `review/review_entries.tsv`.
3. Fix terms and remove `[REVIEW: ...]` markers component by component.
4. Run gettext validation (`msgfmt --check --statistics`) in a system with gettext tools installed.
5. Only then create clean `ne/*.po` files for upstream discussion.

## Directory layout

- `po/<component>/ne.draft.<component>.po` — draft `.po` files.
- `glossary/` — glossary draft.
- `review/` — review index and placeholder check output.
- `stats/` — per-component statistics.
- `scripts/` — generator script placeholder.

## Important limitation

This draft is designed to save mechanical work, preserve PostgreSQL syntax, and focus human review on difficult terminology. It is not a substitute for native Nepali translation.
