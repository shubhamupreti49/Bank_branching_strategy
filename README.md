**The Deposit Magnet: Quantifying the Drivers of Bank Geographic Spread**

**Bank Branching Strategy: Where the Money Is, Not Where the Competition Is**

Author: _Shubham Upreti_ | Date: October 16, 2025

(https://github.com/shubhamupreti49/Bank_branching_strategy)

**🎯 Core Insight: Challenging the Role of Competition**

This project investigates a critical question in financial services: What truly determines a bank's geographic presence (its "lending radius") in a given market?

- Using a robust spatial-econometric approach on extensive U.S. branch data, we tested two competing hypotheses related to market structure: concentration (HHI) versus opportunity (Market Size).

Our Definitive Finding: A bank's spatial strategy is overwhelmingly driven by economic opportunity—the sheer volume of deposits available in a market—and is largely independent of the competitive landscape (HHI). Banks follow the money, not the competitive moves of their rivals.


No systematic influence on branch dispersal.

**🗺️ The Data Science Architecture**

This project integrates abstract economic metrics with concrete spatial data science, providing a powerful, replicable framework for researchers studying firm behavior.

**1. Data Engineering & Cleaning**

i) Started with raw bank branch data, cleaning and filtering for key variables.

ii) The final analysis dataset contains 58,123 branch records across 3,207 unique banks and 393 markets (MSAs).

**2. Feature Creation: The Core Variables**

i) Independent Variable: Market Concentration (HHI)

ii) Calculated the Herfindahl-Hirschman Index (HHI) for each Metropolitan Statistical Area (MSA) based on the sum of squared market shares (total deposits per bank within the MSA).

iii) Dependent Variable: Average Geographic Lending Radius (Miles)

iv) Used the Haversine formula (geosphere package in R) to calculate the mean pairwise distance between all branches of a single bank within an MSA. This provides a robust, market-level proxy for the bank's "geographic spread."

v) Control Variable: Market Size (Log Total Deposits)

vi) The total deposit volume for the entire MSA, log-transformed to normalize the skewed distribution.

**3. Modeling & Falsification**

i) A Robust Linear Model (lm) was constructed to isolate the effects of the core variables, confirming the visual evidence:

**avg_mean_distance ~ deposit_hhi + log_total_deposits**

ii) The key finding from the model output is the highly significant coefficient for log_total_deposits and the insignificant coefficient for deposit_hhi.

**📊 The Visual Narrative: A Tale of Two Variables**

Market Concentration vs. Lending Radius

The lack of a systematic relationship is clear. The average lending radius remains scattered regardless of whether the market is highly concentrated or competitive.


Market Size vs. Lending Radius

In contrast, this plot reveals a powerful, positive linear relationship. As the market's total deposit base increases, the average geographic lending radius systematically increases.


**💡 Significance & Takeaways**

The results of this project have implications across strategy and policy:

1. Business Strategy

For banking executives, the study provides a clear directive: Prioritize branch location decisions based on the sheer volume of deposits available (market size), rather than reacting defensively to the specific competitive structure of rivals.

2. Public Policy

The finding suggests that regulatory efforts to micro-manage branch location based purely on competition (HHI) may be misplaced. Promoting overall economic vitality and deposit growth in a market is the more effective lever for increasing the physical spread and accessibility of banking services.

3. Ethical Consideration

The highly significant market size finding presents a crucial ethical challenge. If misinterpreted, it could be used to justify neglecting low-deposit, often low-income or rural, areas, potentially exacerbating the problem of "banking deserts." This highlights the need for a nuanced policy response that uses economic incentives to address spatial equity, not just efficiency.

**Citations Supporting the Analysis**

Begenau, A., Oberfield, E., Rossi-Hansberg, E., & Wenning, D. (2024). "Banks in Space." National Bureau of Economic Research Working Paper 32262.

Bouakez, H., Côté, J., & D'Souza, C. (2020). "A Spatial Model of Bank Branches in Canada." Bank of Canada Staff Working Paper 2020-4.
