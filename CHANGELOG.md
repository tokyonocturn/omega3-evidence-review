# Changelog

All notable changes to the datasets, generated tables, and report are recorded here.
The format follows Keep a Changelog; versions use semantic versioning.

## [1.0.0] - 2026-11-18

### Added

- Comprehensive scientific report covering EPA/DHA biology, sources and
  formulations, bioavailability, cardiovascular outcomes, triglycerides,
  cognition, mental health, joints and muscle, pregnancy, eye and other outcomes,
  safety, dosing, oxidation, contaminants, certification, sourcing,
  sustainability, brand value, and regulation.
- `data/products.csv`: 20 products priced 2026-11-18 across fish oil concentrate,
  cod liver oil, krill oil and algal oil, normalised to cost per gram of labelled
  EPA+DHA.
- `data/evidence.csv`: 70 graded evidence rows across ten domains.
- `data/claims.csv`: 35 claims adjudicated as supported, partially supported,
  misleading, unsupported or false.
- `data/dosing.csv`: dose ranges by purpose with their basis.
- `data/quality_standards.csv` and `data/quality_surveys.csv`: oxidation and
  contaminant limits, and published market testing results.
- `data/references.csv`: 125 references with DOI, PMID or stable URL.
- `analysis/build_tables.py`: schema validation, cost model, generated Markdown,
  relative-link checking, and a `--check` mode for CI.
- GitHub Actions workflow that validates the datasets on every push.
- Methodology, dosage, safety, quality, sourcing, brand and regulation chapters,
  plus a one-page verdict.

### Notes

- Prices are US one-time retail snapshots and exclude tax and shipping;
  promotional prices are marked.
- No new laboratory testing was commissioned. Every product row records that its
  EPA/DHA values are label values, and contamination conclusions rely on
  published independent testing and peer-reviewed market surveys.
- The review is AI-assisted and has not been peer reviewed. See
  `docs/01-methodology.md`.

## Correction policy

Substantive corrections are recorded here with the date, the affected row or claim,
and the source that justified the change. Generated tables are never edited by hand;
they are rebuilt from the CSVs and verified in CI.
