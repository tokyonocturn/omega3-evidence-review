# Data dictionary

All datasets are UTF-8 CSV with a single header row and one record per row. Empty
cells mean "not reported by the source" and are never silently imputed.

## `data/products.csv`

One row per product. Values come from the manufacturer label, the NIH Dietary
Supplement Label Database, or an authorised retailer's published Supplement Facts.
**No product was assayed by this project.** `assay_status` records that limitation
for every row.

| Column | Type | Meaning |
| --- | --- | --- |
| `id` | slug | Unique stable identifier. |
| `brand` | text | Brand name. |
| `product` | text | Product line as sold. |
| `category` | enum | `Fish oil concentrate`, `Cod liver oil`, `Krill oil`, `Algal oil`. |
| `form` | enum | `TG` (natural triglyceride), `rTG` (re-esterified triglyceride), `EE` (ethyl ester), `Phospholipid`, `Algal`, `Unstated`. |
| `source` | text | Declared fish species or algal source. `not stated` where the label is silent. |
| `serving_softgels` | number | Capsules or teaspoons per labelled serving. |
| `servings_per_container` | number | Labelled servings in the pack. |
| `oil_mg` | number | Total oil or omega-3 concentrate per serving, where declared. |
| `epa_mg` | number | Labelled EPA per serving. |
| `dha_mg` | number | Labelled DHA per serving. |
| `other_omega3_mg` | number | DPA or other declared omega-3, where stated. |
| `certification` | text | Named third-party programme, or `None stated`. A certification is not an assay of this specific pack. |
| `added_vitamins` | text | Declared vitamins, including naturally occurring vitamins in cod liver oil. |
| `price_usd` | number | One-time retail price in US dollars, excluding tax and shipping. |
| `price_date` | ISO date | Date the price was observed. |
| `price_channel` | text | Where and in what pack size the price was observed. |
| `price_url` | URL | Page used for the price. |
| `label_url` | URL | Page used for the Supplement Facts panel. |
| `assay_status` | text | Independent assay status. Currently always label-only. |
| `notes` | text | Pack, formulation, or verification caveats. |

### Derived fields (computed, never stored)

```
epa_dha_g_per_serving = (epa_mg + dha_mg) / 1000
total_epa_dha_g       = epa_dha_g_per_serving x servings_per_container
cost_per_g_epa_dha    = price_usd / total_epa_dha_g
cost_per_30d_at_1g    = cost_per_g_epa_dha x 30
cost_per_year_at_2g   = cost_per_g_epa_dha x 730
concentration_pct     = (epa_mg + dha_mg) / oil_mg x 100     # only when oil_mg is declared
```

`other_omega3_mg` is excluded from every cost calculation. Paying for DPA,
astaxanthin, or "total omega-3" is not the same as paying for EPA+DHA.

## `data/evidence.csv`

| Column | Type | Meaning |
| --- | --- | --- |
| `id` | slug | Unique identifier, prefixed by domain (`CV`, `LIP`, `NEU`, ...). |
| `domain` | enum | `Cardiovascular`, `Lipids`, `Neurology`, `Mental health`, `Musculoskeletal`, `Ophthalmology`, `Obstetrics`, `Oncology`, `Other`, `Safety`. |
| `question` | text | One question, one outcome. |
| `population` | text | Who was studied. |
| `design` | enum | `RCT`, `RCT crossover`, `RCT follow-up`, `RCT (2x2 factorial)`, `Meta-analysis`, `Meta-analysis of N RCTs`, `Cochrane review`, `Cohort meta-analysis`, `Scientific advisory`, `Regulatory determination`, `Case report`. |
| `n` | integer | Participants, where reported. |
| `dose_mg` | number | EPA+DHA mg/day. Blank for observational work, guidelines and regulatory rows. |
| `duration` | text | Follow-up or treatment duration. |
| `metric` | text | `HR`, `RR`, `OR`, `SMD`, `Hedges g`, `MD (units)`, `percent change`, `mmHg (systolic)`, `mg/dL (LDL)`, `kg (muscle mass)`, `beta per mg EPA`. |
| `estimate` | number | Point estimate, signed where the metric is directional. |
| `ci_low`, `ci_high` | number | 95% confidence interval bounds, where reported. |
| `status` | enum | `Benefit`, `No benefit`, `Harm`, `Mixed`, `Insufficient`, `Established`. `No benefit` means the estimate is compatible with no effect; it does not mean harm. |
| `certainty` | enum | `High`, `Moderate`, `Low`, `Very low`, `Not graded`. GRADE-style. |
| `reference_id` | ref | One `references.csv` ID. Semicolon-separated only where a row synthesises two sources. |
| `notes` | text | Caveats that change interpretation. |

## `data/claims.csv`

| Column | Type | Meaning |
| --- | --- | --- |
| `id` | slug | Unique identifier. |
| `claim` | text | The claim as it circulates, paraphrased. |
| `verdict` | enum | `Supported`, `Partially supported`, `Unsupported`, `False`, `Misleading`. |
| `explanation` | text | What the evidence actually shows, with the decisive number. |
| `evidence_ids` | refs | Semicolon-separated `evidence.csv` IDs. |
| `reference_ids` | refs | Semicolon-separated `references.csv` IDs. |

`Misleading` is used when the underlying fact is true but the inference drawn from
it is not. `False` is reserved for claims contradicted by the primary evidence.

## `data/dosing.csv`

| Column | Type | Meaning |
| --- | --- | --- |
| `purpose` | text | Indication or goal. |
| `target_low_mg`, `target_high_mg` | number | EPA+DHA mg/day range. `0` where no supplement dose is justified. |
| `basis` | text | Guideline, trial, or advisory the range comes from. |
| `notes` | text | What the dose does and does not achieve. |
| `reference_ids` | refs | Semicolon-separated reference IDs. |

## `data/quality_standards.csv`

| Column | Type | Meaning |
| --- | --- | --- |
| `id` | slug | Unique identifier. |
| `parameter` | text | Measured quantity. |
| `limit_value` | number | Maximum permitted or specified value. |
| `unit` | text | Unit of the limit. |
| `applies_to` | text | Scope of the standard. |
| `source_id` | ref | `references.csv` ID, or `GOED`/`Codex` where the standard is the source. |
| `notes` | text | Formula or applicability caveat. |

## `data/quality_surveys.csv`

| Column | Type | Meaning |
| --- | --- | --- |
| `id` | slug | Unique identifier. |
| `study` | text | Short study descriptor. |
| `market` | text | Country or region sampled. |
| `year_sampled` | text | Sampling year or range. |
| `n_products` | integer | Products tested. |
| `parameter` | text | What was measured. |
| `result` | number | Percentage or count reported. |
| `unit` | text | Unit of `result`. |
| `source_id` | ref | `references.csv` ID. |
| `notes` | text | Interpretation caveat, especially assay interference by flavouring. |

## `data/references.csv`

| Column | Type | Meaning |
| --- | --- | --- |
| `id` | ref | `R01`-style identifier. |
| `citation` | text | Vancouver-style citation. |
| `type` | enum | `rct`, `meta-analysis`, `systematic review`, `cohort`, `guideline`, `regulatory`, `standard`, `market survey`, `review`, `report`, `database`, `case report`, `news`. |
| `doi` | text | DOI where verified. Blank where only a stable URL was confirmed. |
| `pmid` | integer | PubMed ID where verified. |
| `url` | URL | Stable publisher, agency, or record URL. |

Every reference has a DOI, a PMID, or a resolving URL; the build fails otherwise.
Where a title could not be confirmed character-for-character, the citation uses a
descriptive title rather than an invented one.
