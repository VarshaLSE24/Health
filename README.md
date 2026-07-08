# Beyond the ICER: A Distributional Cost-Effectiveness Analysis of Semaglutide in England
Does a cost-effective obesity drug reduce or widen health inequality? A full distributional cost-effectiveness analysis (DCEA) built in Excel following Dr Asaria's experimental framework.

Methods: DCEA · Atkinson equally-distributed equivalent (EDE) · one-way sensitivity analysis
Tools: Microsoft Excel
Socioeconomic variable: Index of Multiple Deprivation (IMD) quintiles (England 20222 - 2024)


**Background:** This project tries to apply distributional cost-effectiveness analysis (DCEA) to semaglutide (2.4 mg) for obesity in England, extending standard cost-effectiveness analysis (CEA) to ask whether, incorporating health inequality in the model, changes the way we assess an intervention and identify how its health effects are distributed across socioeconomic groups.

**So why Semaglutide?**
I chose Semaglutide (2.4 mg) to apply my newfound knowledge from Dr Miqdad Asaria's short interactive exercise in DCEA using fictional data "Slimstatin for Obesity. I used his framework to create a complex, empirical evaluation using real-world data derived across multiple distinct clinical and socioeconomic sources. For verification purposes and to eliminate confirmation bias during model design, this analysis was developed independently prior to reviewing existing literature on the subject, establishing a blinded baseline to later compare against external evaluations (such as the ISPOR Semaglutide DCEA case study).

Before I lay out the framework and results, I would like to quickly lay out the parameter definitions and abbreviations used throughout the project in the Glossary mentioned below.

I broke down the data extraction and modelling into 4 modules.
 
**Module 1: Cost-Effectiveness Analysis (CEA) Constants & Parameter Derivation**
For the baseline economic evaluation, a lifetime net health opportunity cost framework was constructed utilizing primary clinical and independent economic data from the National Institute for Health and Care Excellence (NICE) Technology Appraisal 875 (TA875). Due to commercial confidentiality restrictions surrounding the UK-specific net health utility data for Semaglutide 2.4 mg, an incremental Quality-Adjusted Life Year (QALY) proxy of $0.098$ per patient was transparently adapted from a methodologically aligned Core Obesity Model (COM) over an identical 40-year discounted horizon. This was paired with the independent Evidence Review Group (ERG) base-case Incremental Cost-Effectiveness Ratio (ICER) of £16,337 per QALY to algebraically isolate a lifetime net incremental cost of £1,601 per patient. Decision-making trade-offs were then benchmarked using the standard NICE willingness-to-pay acceptability threshold of £20,000 per QALY against an empirical NHS marginal opportunity cost threshold of £12,936 per QALY. This structural comparison establishes the central analytical tension of the Distributional Cost-Effectiveness Analysis (DCEA): while the intervention yields a positive Net Health Benefit ($+0.018$) under conventional reimbursement guidelines, it simultaneously generates a net health loss ($-0.026$) at the system level by displacing more health from the broader NHS budget than it creates.

**Module 2: Opportunity Cost & Population Distribution Derivation**
To model how the financial burden of funding the intervention impacts health across the socioeconomic spectrum, a population denominator framework was constructed using the 2020 ONS mid-year deprivation decile area estimates, aggregating adults aged 16 and over into five unified Index of Multiple Deprivation (IMD) quintiles. Total gross QALYs gained per quintile were modeled by applying a constant clinical efficacy multiplier ($0.098$ QALYs) to the treated patient volume, which was uniquely derived by overlaying Health Survey for England obesity prevalence trends against regional Tier 3 commissioning uptake data. To quantify health displacement at the system level, health opportunity costs were modeled across four scenario combinations using both standard willingness-to-pay (£20,000) and empirical (£12,936) thresholds. In the reference base case, opportunity costs were distributed equally ($20\%$ per quintile) following conventional NICE reference case assumptions. This was stress-tested against an empirical, deprivation-weighted distribution ($27\%$ in Q1 graduating down to $13\%$ in Q5) adapted from the University of York Centre for Health Economics Prototype Equity Tool. By subtracting these localized displaced QALYs from the gross QALY gains, the framework isolates Net Health Benefit (NHB) per quintile, serving as the central metric of the DCEA; a persistent negative NHB in the most deprived quintiles mathematically demonstrates that the intervention inflicts net health harm on vulnerable populations by displacing vital baseline NHS services.

**Module 3: Social Welfare Function & Equity Integration**
To evaluate the policy trade-offs under varying degrees of societal inequality aversion, Module 3 implements an Atkinson Social Welfare Function structured on baseline Quality-Adjusted Life Expectancy (QALE) by income quintile. While adopting the three-part QALE spine from the foundational Asaria et al. template, this module corrects a vital mathematical discrepancy by cleanly reconciling per-capita life expectancy scales with population-wide total net benefits. Crucially, the net benefit calculation was re-engineered to explicitly subtract the distributed NHS health opportunity costs derived in Module 2, rather than omitting them. The final analysis surfaces an important methodological insight: because a single pharmaceutical intervention yields infinitesimally small shifts in a nation's lifetime per-capita health distribution, the global Atkinson decision remains stably with the intervention across all inequality aversion parameters ($\alpha$). Instead, the true equity narrative and regressive distribution pattern are explicitly captured and interpreted through the disaggregated net benefit rows, which cleanly highlight that the poorest quintiles structurally absorb net health harms while wealthier quintiles capture the gains.

**Module 4: Comprehensive Sensitivity Analysis Breakdown**

Each panel isolates a core assumption of the framework to test whether alternative policy settings or pricing shifts could reverse the regressive nature of the intervention.

**SA1 — Intervention Acquisition Cost (Drug Cost)**
The Mechanism: This panel varies the annual cost of Semaglutide from an ultra-low £1,400 up to £20,000.
The Finding: Lowering the price does not fix the equity gap; the optimal decision remains firmly with the baseline across all evaluated price points. Because of the regressive uptake gradient, the poorest population (Q1) simply does not get sufficient access to the drug. Consequently, even at £1,400/year, the health displaced from Q1's local health budget to fund the wider program outweighs their clinical gains, leaving them at a net deficit ($-179.92$ QALYs).

**SA2 — Health Opportunity Cost Distribution (Displacement Burden)**
The Mechanism: This panel moves away from the uniform reference case ($20\%$ displacement per quintile) to evaluate four distinct ways the NHS budget might absorb the intervention's cost, ranging from pro-poor to pro-rich displacement distributions.
The Finding: Altering how service cuts are distributed across the NHS fails to protect the vulnerable. Even under a highly optimistic "Concentrated Richest" scenario—where the wealthiest areas bear $50\%$ of the budget displacement and the poorest bear only $3\%$—Q1 still incurs a net health loss ($-36.60$ QALYs). The systemic access barriers are so entrenched that Q1 loses under every conceivable displacement architecture.

**SA3 — Opportunity Cost Threshold**
The Mechanism: This panel contrasts the optimistic, policy-driven NICE reimbursement threshold (£20,000) against the realistic, empirical NHS marginal cost per QALY (£12,936).
The Finding: When evaluated against what the NHS actually spends to generate health historically, the intervention suffers a massive systemic sign-flip. Total population Net Health Benefit collapses from a positive $+273.58$ QALYs down to a net societal deficit of $-392.66$ QALYs. This intensification of opportunity cost deepens the health deficit for the poor, accelerating Q1's net losses to an extreme $-343.80$ QALYs.

**Results:** On a pure efficiency basis ($\alpha = 0.00$), semaglutide expands overall population health, yielding a positive net benefit of $+273.57$ QALYs. However, this gain is entirely driven by the wealthiest quintiles (Q4 and Q5), while the poorest quintiles (Q1–Q3) experience a net health loss. This regressive result is driven by a steep uptake gradient (ranging from $0.04\%$ in Q1 to $1.10\%$ in Q5) and a regressive opportunity cost structure where NHS health displacement falls disproportionately on poorer groups. Because individual per-capita losses among the poor are small relative to baseline life expectancy, a decision-maker with mild-to-moderate inequality aversion ($\alpha \le 3.00$) would still prefer semaglutide. However, under a stronger commitment to equity ($\alpha \ge 5.00$), the social welfare penalty for compounding inequality outweighs the aggregate gains, making the baseline non-intervention strategy preferred. Crucially, the drug's overall value is highly threshold-dependent: it is net-beneficial at the conventional £20,000 NICE threshold ($+273.6$ QALYs) but net-harmful at the £12,936 empirical threshold ($-392.7$ QALYs). 

**Conclusion:** These findings demonstrate that standard cost-effectiveness and equity metrics can point in opposite directions. An intervention that satisfies standard efficiency criteria may still widen health inequalities, underscoring that how a treatment is implemented and accessed across socioeconomic gradients matters as much as whether it is funded.

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

