# Oxidation, rancidity and contaminants

Fish oil is a highly unsaturated fat, and highly unsaturated fats go rancid.
That single fact drives most of the quality variation in the market — and most of
the misleading reassurance.

## How oxidation is measured

| Marker | What it measures | Limit (GOED / Codex) |
| --- | --- | ---: |
| Peroxide value (PV) | Primary oxidation products (hydroperoxides) | ≤5 meq O₂/kg |
| p-Anisidine value (pAV) | Secondary oxidation products (aldehydes, ketones) | ≤20 |
| TOTOX | Composite: (2 × PV) + pAV | ≤26 |
| Acid value | Free fatty acids from hydrolysis | ≤3 mg KOH/g |

These limits are codified in the GOED voluntary monograph and in Codex
CXS 329-2017 ([R23](references.md), [R24](references.md)), and in Health Canada's
fish oil monograph. **In the United States they are not law.** There is no FDA
limit for oxidation in fish oil supplements, which is why "TOTOX above 26 is
illegal" is false and why products above the limit are sold freely.

Two technical caveats that explain why surveys disagree so much:

1. **The p-anisidine assay is invalid for flavoured or coloured oils.** Citrus,
   mint and other flavourings interfere, producing false positives. Studies that
   do not separate flavoured from unflavoured products therefore overstate the
   problem in flavoured products and understate the comparison.
2. **TOTOX is a convenience metric, not a toxicological threshold.** It has no
   scientific basis as a safety limit; it is a reproducible way to rank oils
   ([R120](references.md)).

## What market surveys find

The generated table is
[`generated/quality-surveys.md`](generated/quality-surveys.md). The pattern:

| Market | Sample | Finding |
| --- | ---: | --- |
| New Zealand, 2014 | 32 | **50%** exceeded TOTOX 26; 83% exceeded PV; only 3 met labelled EPA+DHA |
| Canada, 2013 | 171 | **50%** exceeded at least one limit; 39% exceeded TOTOX |
| United States, 2018 | 48 | 87% of unflavoured products complied; mean TOTOX 19.2 |
| United States, 2014-2020 | 72 | **68% of flavoured** vs **13% of unflavoured** exceeded TOTOX |
| UAE, 2019 | 44 | 41% exceeded PV; mean TOTOX 23.8 |
| Australia, 2018 | 26 | 33% exceeded TOTOX |
| GOED members, 2023 | 20 | All met label; 20% exceeded PV; one exceeded pAV |

The honest reading: **oxidation is common but not universal, and it is worst in
flavoured liquids and bulk oils.** Unflavoured softgels from established brands
usually comply. The New Zealand study's headline finding — only 3 of 32 products
met their labelled EPA+DHA — is an outlier; US testing found a mean of 102% of
label ([R27](references.md)). Both can be true: quality varies by market and by
supplier, and a single study is not a census.

## Does oxidised fish oil harm humans?

This is where honesty is required in both directions.

**What has been shown in humans: essentially nothing at supplement doses.**
A randomised trial gave healthy volunteers **8 g/day of deliberately oxidised
fish oil** (PV 18 meq/kg, well above the limit) for 3-7 weeks and found **no
change** in urinary 8-iso-PGF2α, plasma 4-HHE or 4-HNE, hs-CRP, or erythrocyte
antioxidant enzymes ([R121](references.md)). A transcriptomic study also found no
differentially expressed genes.

**What has been shown in animals:** severe over-oxidation (30 days of oxygen and
light) caused harm in rats at high doses — but that is a different exposure from
a retail capsule.

**Why the uncertainty persists:** trials rarely report the oxidative status of
the oil they used, so efficacy and harm cannot be cleanly attributed. EFSA
concluded in 2010 that information on oxidation levels and toxicological effects
in humans was lacking, and that no acceptable PV/AV limit could be derived from
human data ([R32](references.md)).

**Practical position:** oxidised oil is not a proven poison at retail doses, but
it smells bad, may reduce the effective dose of EPA+DHA, and is a marker of poor
manufacturing. Avoid it where you can, but do not panic about a single fishy
capsule.

## Contaminants

### Mercury

Methylmercury binds protein, so it partitions into fish **flesh**, not oil.
Refined fish oils are consistently low: a GOED/Nutrasource dataset of 792 samples
found a mean of 0.0005 mg/kg against a 0.1 mg/kg specification
([R35](references.md)). EU law caps mercury in food supplements at **0.10 mg/kg**
([R33](references.md)). Mercury is the contaminant least likely to be a problem
in a capsule — and the one marketers most often invoke.

### PCBs, dioxins and POPs

These are **lipophilic**, so they concentrate in the oil fraction during
rendering. This is the contaminant class that actually matters.

EU maximum levels for marine oils sold to the final consumer:

| Contaminant | Limit |
| --- | ---: |
| Dioxins (PCDD/F) | 1.75 pg WHO-TEQ/g fat |
| Dioxins + dioxin-like PCBs | 6.0 pg WHO-TEQ/g fat |
| Non-dioxin-like PCBs (ICES-6) | 200 ng/g fat |

A UK survey of 33 products (2000-2002) found PCDD/F 0.18-8.4 ng/kg WHO-TEQ, with
**12 of 33 exceeding the then-current 2 ng/kg limit** ([R34](references.md)).
Japanese and Canadian studies found **shark liver oil** to be a recurring
outlier, with dioxin and PCB levels far above fish body oils
([R35](references.md)). Modern molecular distillation removes **76-99%** of
dioxins, dioxin-like PCBs and non-dioxin-like PCBs, with minimal loss of EPA+DHA
but some loss of vitamins ([R36](references.md), [R37](references.md)).

**Practical position:** refined fish body oils from major suppliers are low in
contaminants and usually compliant. Shark liver oil, some cod liver oils, and
unrefined "traditional" oils are higher-risk. Distillation is the control that
makes the difference.

## Manufacturing: what the processes do

| Step | Purpose | Effect on quality |
| --- | --- | --- |
| Rendering | Extract oil from fish or by-products | Raw-material freshness determines the starting PV |
| Winterisation / degumming | Remove solids and phospholipids | Improves clarity and stability |
| Transesterification + distillation | Concentrate EPA/DHA | Creates ethyl esters; removes short-chain fatty acids |
| Molecular (short-path) distillation | Strip POPs, pesticides, odour volatiles | Removes 76-99% of POPs; can strip vitamins; excessive heat can isomerise PUFAs |
| Re-esterification | Convert EE back to triglyceride | Improves bioavailability at extra cost |
| Antioxidant addition | Tocopherol, rosemary extract | Slows further oxidation; does not reverse existing oxidation |
| Nitrogen flush / opaque bottle | Exclude oxygen and light | Meaningful shelf-life protection |

A crucial point: **distillation does not un-oxidise oil.** If the raw material
arrived rancid, the finished product may be contaminant-free and still oxidised.
This is why GOED recommends a bulk-oil PV below 3 meq/kg to survive shelf life,
stricter than the 5 meq/kg finished-product limit.

## Storage and freshness at home

- Keep capsules in a closed, dark container; heat and light accelerate oxidation.
- Refrigerate liquid oils after opening if the label recommends it.
- Do not use past the expiry date, especially for liquids.
- A strong fishy smell, burping that tastes of fish, or a changed capsule colour
  are reasons to discard — but they are not a laboratory test.
- Do not decant into an open container or store above a stove.

## What to look for

1. A **lot-level certificate of analysis** or IFOS report, not just a brand claim.
2. **Unflavoured** softgels if you care about measurable oxidation; flavoured
   liquids are harder to assess.
3. **Fish body oil** rather than shark or generic "liver oil" unless the brand
   publishes contaminant data.
4. A **recent expiry date** and a supplier that turns stock over.
5. **Nitrogen-flushed, opaque** packaging for liquids.

See [testing and certifications](07-testing-certifications.md) for what each seal
actually verifies.
