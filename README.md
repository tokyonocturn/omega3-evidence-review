# Fish Oil and Omega-3 Supplements: An Independent Evidence Review and Product Database

A source-linked investigation of EPA/DHA supplements — what they do, what they do
not do, how formulations differ, how fresh and pure they are, and what 20 real
products cost per gram of **actual EPA+DHA** rather than per gram of fish oil.

Built as a reproducible repository: every quantitative claim traces to a
reference, and every table is generated from the CSV datasets in [`data/`](data/).

**No brand funding, affiliate links, or sponsorship.** Prices were collected on
18 November 2026 and will change. No product was assayed by this project; label
values and published third-party testing are the evidence base, and that limit is
recorded in the data.

---

## Bottom line

**Omega-3 supplements are worth taking for a narrow set of reasons, at doses most
products do not provide, and at prices that vary 21-fold for the same nutrient.**

| Question | Answer | Confidence |
| --- | --- | --- |
| Do they lower triglycerides? | **Yes, at 2–4 g/day**: 20–30% reduction. The strongest effect in the field. | High |
| Do they prevent heart attacks? | **Partly.** 1 g/day cut total MI by 28% (HR 0.72) in VITAL, but the primary composite was null (HR 0.92). | Moderate |
| Do they reduce death? | **No.** All-cause mortality RR 0.97 (0.93–1.01) across 45 trials. | High |
| Do they help cognition or prevent dementia? | **No.** High-certainty null in healthy older adults; supplement trials show no dementia prevention. | High |
| Do they treat depression? | **At most as an adjunct**, small effect (SMD 0.40), low certainty, EPA-predominant. | Low |
| Do they help ADHD, dry eye, joints? | **No.** ADHD is a high-certainty null; DREAM and VITAL knee substudy were null. | High |
| Do they prevent preterm birth? | **Probably, in some women.** Pooled RR 0.58 for early preterm, but the largest trial was null. | Moderate |
| Which formulation? | **Concentrated fish oil.** rTG is modestly better absorbed; EE is cheaper; a fatty meal narrows the gap. Krill is 6–15× the cost per gram. | Moderate |
| How much? | **250 mg/day** for adequacy; **~1 g/day** for primary prevention; **2–4 g/day** for triglycerides. The median US product delivers only **600 mg/day**. | High |
| Is it safe? | **Yes at ≤3 g/day for most people.** Main signal: atrial fibrillation at higher doses (HR 1.49 above 1 g/day). Bleeding risk is small (RR 1.09). | Moderate–High |
| Who should avoid a formulation? | **Cod liver oil** in pregnancy or with vitamin A intake (8.5–45% of the UL per teaspoon; high-vitamin products can exceed it); **DHA-dominant** products with high LDL; **high doses** with prior AF. | Moderate |
| Best value? | **Viva Naturals Triple Strength** and **Sports Research Triple Strength**, about **$0.30–0.31 per gram of EPA+DHA**, IFOS-tested. | Price snapshot |
| Worst value? | **Krill oil at $2.83–4.59/g** and some algal oils at $2.25–4.53/g — 8–21× the cheapest fish oil for the same nutrient. | Price snapshot |

The full argument is in the
[scientific report](report/fish-oil-scientific-report.md). The one-page decision
guide is [the verdict](docs/12-verdict.md).

---

## What is in this repository

| Path | Contents |
| --- | --- |
| [`report/fish-oil-scientific-report.md`](report/fish-oil-scientific-report.md) | Comprehensive report: biology, formulations, every outcome domain, safety, quality, sourcing, cost, regulation, conclusions. |
| [`docs/01-methodology.md`](docs/01-methodology.md) | Search strategy, inclusion rules, grading, cost model, verification, limitations, AI disclosure. |
| [`docs/02-epa-dha-biology.md`](docs/02-epa-dha-biology.md) | What EPA and DHA do, and why they are not interchangeable. |
| [`docs/03-sources-and-forms.md`](docs/03-sources-and-forms.md) | Fish, krill, algal and cod liver oil; TG vs EE vs rTG; bioavailability; sn-2; enteric coating. |
| [`docs/04-evidence-review.md`](docs/04-evidence-review.md) | Cardiovascular, lipid, cognitive, mental health, joint, pregnancy and other outcomes. |
| [`docs/05-dosage.md`](docs/05-dosage.md) | Dose by purpose, the 600 mg trap, timing, special populations, upper bounds. |
| [`docs/06-oxidation-and-contaminants.md`](docs/06-oxidation-and-contaminants.md) | TOTOX, rancidity surveys, mercury, PCBs, dioxins, distillation, storage. |
| [`docs/07-testing-certifications.md`](docs/07-testing-certifications.md) | What USP, NSF, IFOS, MSC, FOS and GOED actually test. |
| [`docs/08-safety-and-interactions.md`](docs/08-safety-and-interactions.md) | Bleeding, AF, GI effects, LDL, vitamins A/D, warfarin, long-term high dose. |
| [`docs/09-sourcing-and-sustainability.md`](docs/09-sourcing-and-sustainability.md) | Global supply, Peru, krill, fish-in-fish-out, species, certification. |
| [`docs/10-brands-cost.md`](docs/10-brands-cost.md) | Cost per gram, transparency, excluded products, best value by use case. |
| [`docs/11-regulation-recalls-labels.md`](docs/11-regulation-recalls-labels.md) | Drug vs supplement, Epanova, warning letters, litigation, label rules, misleading tactics. |
| [`docs/12-verdict.md`](docs/12-verdict.md) | Who benefits, who does not, who should avoid what, best products, bottom line. |
| [`docs/generated/brand-comparison.md`](docs/generated/brand-comparison.md) | Generated 20-product cost table, transparency counts. |
| [`docs/generated/evidence-tables.md`](docs/generated/evidence-tables.md) | 70 graded evidence rows across ten domains. |
| [`docs/generated/claims-table.md`](docs/generated/claims-table.md) | 35 marketed claims adjudicated as supported, partial, misleading, unsupported or false. |
| [`docs/generated/dosing-table.md`](docs/generated/dosing-table.md) | Dose ranges by purpose. |
| [`docs/generated/quality-standards.md`](docs/generated/quality-standards.md) | Oxidation and contaminant limits. |
| [`docs/generated/quality-surveys.md`](docs/generated/quality-surveys.md) | Market testing results. |
| [`docs/references.md`](docs/references.md) | 125 references with DOI, PMID or stable URL. |
| [`data/products.csv`](data/products.csv) | Product database: label EPA/DHA, form, source, certification, vitamins, price. |
| [`data/evidence.csv`](data/evidence.csv) | Evidence table with effect sizes, CIs, certainty and status. |
| [`data/claims.csv`](data/claims.csv) | Claim adjudication dataset. |
| [`data/dosing.csv`](data/dosing.csv) | Dose guidance with basis. |
| [`data/quality_standards.csv`](data/quality_standards.csv) | Regulatory and voluntary limits. |
| [`data/quality_surveys.csv`](data/quality_surveys.csv) | Published market surveys. |
| [`data/references.csv`](data/references.csv) | Reference metadata. |
| [`data/data-dictionary.md`](data/data-dictionary.md) | Column definitions and grading scheme. |
| [`analysis/build_tables.py`](analysis/build_tables.py) | Validates the datasets, computes cost metrics, regenerates all tables, checks links. |

---

## Reproduce it

Requires Python 3.10+ and no third-party packages.

```bash
python analysis/build_tables.py           # validate + regenerate tables
python analysis/build_tables.py --check   # fail if data or tables are stale
```

The `--check` command runs in CI on every push
([`.github/workflows/validate.yml`](.github/workflows/validate.yml)). It verifies:

- required columns and allowed categorical values;
- unique IDs and resolvable cross-references between evidence, claims, dosing and
  references;
- plausible serving counts, positive prices, and that EPA+DHA never exceeds the
  declared oil mass;
- ISO price dates and non-inverted confidence intervals;
- that generated Markdown is byte-identical to what the data produces;
- that every relative Markdown link resolves.

### Derived cost model

```
EPA+DHA per serving  = (epa_mg + dha_mg) / 1000                  # grams
EPA+DHA per pack     = per serving x servings_per_container
cost per gram        = price_usd / EPA+DHA per pack
cost per 30 days     = cost per gram x 30                        # at 1 g/day
cost per year        = cost per gram x 730                       # at 2 g/day
concentration        = (epa_mg + dha_mg) / oil_mg x 100
```

Total fish oil, "total omega-3", DPA and astaxanthin are **excluded** from the
numerator. This is the single most important methodological choice in the
repository: it is what distinguishes "1,200 mg fish oil" from 180 mg of EPA+DHA.

---

## How the evidence was handled

- **Benefit / No benefit / Harm** describe the direction of the estimate and
  whether the confidence interval excludes no effect.
- **High / Moderate / Low / Very low** describe certainty, using GRADE logic.
- **Established** marks a regulatory or guideline determination rather than a
  trial estimate.
- **Supported / Partially supported / Misleading / Unsupported / False** classify
  marketing claims. "Misleading" means the underlying fact is true but the
  inference is not.

A high-certainty null is a strong finding. A low-certainty positive is a weak
one. Marketing routinely converts the second into the first. Full details:
[`docs/01-methodology.md`](docs/01-methodology.md).

---

## What this review is not

- **Not medical advice.** High triglycerides, cardiovascular disease, bleeding
  disorders, pregnancy, liver disease, anticoagulant use and doses above 3 g/day
  are clinical situations. Talk to a clinician.
- **Not a primary laboratory study.** No product was assayed. Quality conclusions
  come from published independent testing, market surveys and certifier
  documentation, and every row records that its value is a label value.
- **Not exhaustive.** Twenty products are a purposive sample across categories,
  forms, price tiers and certifications — not a census.
- **Not free of uncertainty.** Industry funding is common, null trials are less
  likely to be published, several major trials used non-inert placebo oils, and
  the REDUCE-IT versus STRENGTH contradiction is unresolved.

### AI-assistance disclosure

Assembled with AI assistance under human direction. Every numeric claim was
checked against the cited abstract, table or dataset; the datasets and generated
tables are machine-validated. It has **not** been peer reviewed. Treat it as a
well-documented starting point, not a substitute for the primary literature or
clinical judgement.

Corrections are welcome: open an issue with the claim, the source and the
proposed change. See [`CONTRIBUTING.md`](CONTRIBUTING.md).

---

## Citation and license

Citation metadata is in [`CITATION.cff`](CITATION.cff).

- **Text and data:** CC BY 4.0 — share and adapt with attribution.
- **Code:** MIT.

See [`NOTICE`](NOTICE) for the full content licence and medical disclaimer.
