# Beyond the ICER: A Distributional Cost-Effectiveness Analysis of Semaglutide in England
Does a cost-effective obesity drug reduce or widen health inequality? A full distributional cost-effectiveness analysis (DCEA) built in Excel following Dr Asaria's experimental framework.

Methods: DCEA · Atkinson equally-distributed equivalent (EDE) · one-way sensitivity analysis
Tools: Microsoft Excel
Socioeconomic variable: Index of Multiple Deprivation (IMD) quintiles (England 20222 - 2024)


**Background:** This project tries to apply distributional cost-effectiveness analysis (DCEA) to semaglutide (2.4 mg) for obesity in England, extending standard cost-effectiveness analysis (CEA) to ask whether, incorporating health inequality in the model, changes the way we assess an intervention and identify how its health effects are distributed across socioeconomic groups.

**So why Semaglutide?**
I chose Semaglutide (2.4 mg) to apply my newfound knowledge from Dr Miqdad Asaria's short interactive exercise in DCEA using fictional data "Slimstatin for Obesity. I used his framework to create a complex, empirical evaluation using real-world data derived across multiple distinct clinical and socioeconomic sources. For verification purposes and to eliminate confirmation bias during model design, this analysis was developed independently prior to reviewing existing literature on the subject, establishing a blinded baseline to later compare against external evaluations (such as the ISPOR Semaglutide DCEA case study).

Before I lay out the framework and results, I would like to quickly lay out the new parameters and abbreviations used throughout the project. Please refer to the Glossary mentioned below.

**Methods:** Socioeconomic status was defined by Index of Multiple Deprivation (IMD) quintiles. Net health benefits (NHB) were estimated using the socioeconomic distribution of health opportunity costs and collapsed into an equity-adjusted social welfare value using the Atkinson equally-distributed equivalent (EDE) function.
**Results:** On a pure efficiency basis ($\alpha = 0.00$), semaglutide expands overall population health, yielding a positive net benefit of $+273.57$ QALYs. However, this gain is entirely driven by the wealthiest quintiles (Q4 and Q5), while the poorest quintiles (Q1–Q3) experience a net health loss. This regressive result is driven by a steep uptake gradient (ranging from $0.04\%$ in Q1 to $1.10\%$ in Q5) and a regressive opportunity cost structure where NHS health displacement falls disproportionately on poorer groups. Because individual per-capita losses among the poor are small relative to baseline life expectancy, a decision-maker with mild-to-moderate inequality aversion ($\alpha \le 3.00$) would still prefer semaglutide. However, under a stronger commitment to equity ($\alpha \ge 5.00$), the social welfare penalty for compounding inequality outweighs the aggregate gains, making the baseline non-intervention strategy preferred. Crucially, the drug's overall value is highly threshold-dependent: it is net-beneficial at the conventional £20,000 NICE threshold ($+273.6$ QALYs) but net-harmful at the £12,936 empirical threshold ($-392.7$ QALYs).
**Conclusion:** These findings demonstrate that standard cost-effectiveness and equity metrics can point in opposite directions. An intervention that satisfies standard efficiency criteria may still widen health inequalities, underscoring that how a treatment is implemented and accessed across socioeconomic gradients matters as much as whether it is funded.



<!-- Two short paragraphs. -->
The problem. <!-- CEA maximises total health but is blind to its distribution. NICE is actively exploring DCEA. Obesity is deprivation-linked, GLP-1 drugs are costly, and real-world uptake skews affluent — making semaglutide a natural equity case study. Write 3–4 sentences in your voice. -->

This project. <!-- What you built and why. e.g. "This repository presents a complete aggregate DCEA built from public and illustrative data, replicating the Asaria framework and extending it with a full one-way sensitivity analysis across cost, opportunity-cost distribution, and threshold." State what the reader will find. -->


2. Background

<!-- One short paragraph + the anchor list. Do NOT write a full literature review. -->
Distributional cost-effectiveness analysis quantifies the trade-off between maximising total health and reducing health inequality. This project builds directly on the following:


Cookson, Griffin, Norheim & Culyer — the DCEA conceptual framework: net health benefit distributed across equity-relevant subgroups, combined with a social welfare function.
Asaria, Griffin & Cookson (2016), Medical Decision Making — the aggregate DCEA tutorial whose modular structure this project follows.
Love-Koh et al. (2020, 2023) — quality-adjusted life expectancy (QALE) by IMD quintile, and the socioeconomic distribution of health opportunity costs.
Claxton et al. (2015) — the empirical NHS cost-effectiveness threshold (~£12,936/QALY), used here as an alternative to NICE's £20,000 convention.

<img src="Images/img_1.png" alt="Alt text" width="500">

**DCEA parameter glossary**
I have defined the key variables by module

**1 · Core model & population**
IMD quintile: Five population segments by Index of Multiple Deprivation, from Q1 (poorest) to Q5 (richest).
Baseline QALE:	Quality-adjusted life expectancy for a typical person in each quintile, before the drug.
Total net benefit (+273.6 QALYs):	Sum of net benefit across all quintiles at the £20,000 threshold — gains after subtracting displaced health.

**2 · Intervention (semaglutide 2.4 mg)**
Uptake gradient (0.04% → 1.10%):	Rate at which patients access the drug, rising from the poorest to the richest quintile.
Gross health gain:	Total QALYs generated by semaglutide for patients who access it, before opportunity cost.
Financial cost:	Total budget impact of funding the drug. Acquisition plus clinical delivery.

**3 · Opportunity cost & displacement**
NICE threshold (£20,000):	Conventional funding benchmark for judging whether health gains outweigh costs.
Empirical threshold (£12,936):	Claxton's measured estimate of what the NHS actually gives up per QALY when funds are diverted.
Regressive opportunity cost:	Disproportionate share of displaced health borne by poorer quintiles, who use more NHS care.
Net health benefit by quintile:	Gross gain minus displaced health, calculated separately for each IMD group.

**4 · Social welfare function**
Inequality aversion (ε):	Weighting for how much a decision-maker will trade total health to achieve a fairer distribution.
Pure efficiency (ε = 0):	Every QALY counts equally regardless of who gains or loses — equivalent to standard CEA.
Atkinson EDE:	Summary metric discounting total health for how unequally it is spread across quintiles.
No welfare reversal (ε = 0–1):	Across all tested aversion levels the drug stays weakly preferred — one intervention shifts lifetime QALE too little to flip the welfare verdict.

