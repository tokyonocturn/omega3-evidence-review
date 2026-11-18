# Methodology

## What this review is

An independent, source-linked synthesis of the human evidence on EPA and DHA
supplements, combined with a product database that normalises every product to
**cost per gram of labelled EPA+DHA**. It was built to answer four questions:

1. Which claimed benefits are real, and how large are they?
2. What dose and formulation produce those effects?
3. Which products are fresh, pure, honestly labelled and good value?
4. Who should take omega-3, and who should avoid particular formulations?

## Scope and inclusion rules

**Evidence.** Peer-reviewed randomised trials, systematic reviews, meta-analyses,
large prospective cohorts, and regulatory or guideline documents. Priority was
given to Cochrane reviews, the largest outcome trials, and syntheses that report
confidence intervals and certainty. Observational evidence is included but always
labelled as such, because it cannot establish that supplements cause the outcome.

**Products.** Twenty products selected purposively across four categories (fish
oil concentrate, cod liver oil, krill oil, algal oil), across price tiers, and
across formulation types, so that the comparison tests the claims the market
actually makes. It is not a census of the market.

A product was eligible only if its label declared **separate EPA and DHA
amounts**. Products that declare only "total omega-3" or only total fish oil are
excluded from the scored database, because the central question — what you pay
per gram of EPA+DHA — cannot be answered from their labels. They are discussed in
[the brand chapter](10-brands-cost.md) as a transparency finding rather than
silently dropped.

**Excluded:** animal studies (used only for mechanistic context), in-vitro work,
unpublished manufacturer claims, affiliate or marketplace listings without a
verifiable label, and products whose price could not be attached to a specific
pack size.

## Search strategy

Searches were run in PubMed, the Cochrane Library, journal sites, and regulator
sites (FDA, EFSA, EMA, EU EUR-Lex, Health Canada), using combinations of:
`omega-3`, `EPA`, `DHA`, `fish oil`, `krill oil`, `algal oil`, `cod liver oil`,
`icosapent ethyl`, plus outcome terms (`cardiovascular`, `triglyceride`,
`atrial fibrillation`, `cognition`, `depression`, `osteoarthritis`, `dry eye`,
`preterm birth`) and quality terms (`oxidation`, `TOTOX`, `PCB`, `dioxin`,
`label claim`, `bioavailability`, `ethyl ester`).

Each candidate record was screened at title/abstract level, then the abstract or
full text was read for the numbers used. Where a review and its included trials
disagreed, both are reported rather than averaged.

## Grading scheme

Two independent axes, deliberately separated:

**Status** — what the estimate shows:

| Status | Meaning |
| --- | --- |
| Benefit | Confidence interval excludes no effect in the beneficial direction. |
| No benefit | Confidence interval includes no effect; this is not evidence of harm. |
| Harm | Confidence interval excludes no effect in the harmful direction. |
| Mixed | Direction depends on outcome, dose, or population. |
| Insufficient | Too few events or too much heterogeneity to conclude. |
| Established | A regulatory or guideline determination, not a trial estimate. |

**Certainty** — how much to trust it, following GRADE logic:

| Certainty | Meaning |
| --- | --- |
| High | Further research is very unlikely to change the estimate. |
| Moderate | Further research may change the estimate materially. |
| Low | Further research is likely to change the estimate. |
| Very low | Estimate is fragile, often from few events or high heterogeneity. |
| Not graded | Source did not grade it and this review declined to invent a grade. |

The distinction matters. "Omega-3 does not prevent dementia" is a **high-certainty
null**, which is a strong finding. "Omega-3 may help depression" is a
**low-certainty positive**, which is a weak one. Marketing routinely converts the
second kind into the first.

## Product and cost model

All products are reduced to the same unit: **grams of EPA+DHA actually declared
per container**.

```
EPA+DHA per serving (g) = (EPA mg + DHA mg) / 1000
EPA+DHA per container  = per serving x servings per container
Cost per gram          = price / EPA+DHA per container
Cost per 30 days at 1 g/day = cost per gram x 30
Cost per year at 2 g/day    = cost per gram x 730
Concentration (%)      = (EPA mg + DHA mg) / total oil mg x 100
```

Deliberate exclusions from the numerator:

- **Total fish oil.** A 1,200 mg softgel containing 180 mg EPA+DHA is not
  equivalent to a 1,200 mg softgel containing 900 mg.
- **"Total omega-3".** Includes ALA and DPA, which do not substitute for EPA and
  DHA in the trials that produced the outcomes.
- **Astaxanthin, phospholipids, vitamins.** Real ingredients, but not EPA+DHA.

Prices are **one-time US retail prices observed on 2026-11-18**, excluding tax,
shipping, subscriptions and coupons, except where a promotional price is
explicitly marked as such in `price_channel`. Subscription pricing was not used
because it changes the effective price and is not comparable across brands.

## Verification and limitations

**What was verified.** Every effect estimate, confidence interval and sample size
in `data/evidence.csv` was checked against the abstract, table or full text of the
cited record. Every price and label value was read from a manufacturer page,
authorised retailer, or the NIH Dietary Supplement Label Database. All arithmetic
is computed by `analysis/build_tables.py`; the build fails if a product's
EPA+DHA exceeds its declared oil mass, if a reference is dangling, if an ID is
duplicated, or if a generated table is stale.

**What was not done.**

- **No product was assayed.** This project did not commission laboratory testing.
  `assay_status` records "label value" for every row. Contamination and oxidation
  conclusions come from published surveys and certification programmes, not from
  this project's own measurements.
- **No new meta-analysis.** Pooled estimates are reported as published. Where
  reviews disagree, both are shown.
- **Single price snapshot.** Prices change, and pack-size promotions can move a
  product several tiers.
- **Purposive sample.** Twenty products illustrate the market; they are not a
  random sample, so the median costs describe this sample, not the market.
- **Publication and funding bias.** A large share of omega-3 trials is
  industry-funded. Trials with null results are less likely to be published, and
  several major trials used placebo oils (olive, corn, mineral) that are not
  inert. These are discussed where they affect interpretation.

## Reproducing the build

```bash
python analysis/build_tables.py           # validate + regenerate all tables
python analysis/build_tables.py --check   # fail on stale outputs or broken links
```

The `--check` mode runs in CI on every push. Requirements: Python 3.10+, standard
library only.

## AI-assistance disclosure

This review was assembled with AI assistance under human direction. Numeric
claims were checked against the cited record; the datasets are machine-validated.
It has **not** been peer reviewed. Treat it as a well-documented starting point,
not a substitute for the primary literature or clinical judgement. Corrections are
welcome via the process in [CONTRIBUTING.md](../CONTRIBUTING.md).
