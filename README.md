# Project 2: Bone & Triathlon Data Analysis

This project analyzes **bone mineral content** and **triathlon performance** using multivariate statistical techniques in R.

---

## Analysis A: Bone Data

**Goal:** Compare mineral content between dominant and non-dominant bones (radius, humerus, ulna).

**Multivariate Normality:**
- Dominant bones: Royston p = 0.0636 ✅  
- Non-Dominant bones: Royston p = 0.5277 ✅  

**Hotelling’s T² Test:**
- T² = 0.295, df1 = 3, df2 = 46, p = 0.8286  
- Chi-square test p = 0.8196  

**Confidence Intervals:**  
- All CIs for radius, humerus, and ulna include 0.

**Conclusion:** No significant differences in mineral content between dominant and non-dominant bones.

---

## Analysis B1: Triathlon Data (Two Age Categories)

**Goal:** Compare swim, bike, and run performance between two age groups.

**Multivariate Normality:**  
- Cat1: Royston p = 0.254 ✅  
- Cat2: Royston p = 0.066 ✅  

**Hotelling’s T² Test:**  
- T² = 17.81, df1 = 3, df2 = 36, p = 2.96e-07  
- Chi-square test p = 3.45e-12  

**Confidence Intervals:**  
- Swim: significant difference  
- Bike & Run: not significant

**Conclusion:** Age groups differ significantly overall, mainly due to swim performance.

---

## Analysis B2: Triathlon Data (Three Age Categories)

**Goal:** Compare performance across three age groups.

**Multivariate Normality:** All categories satisfy MVN assumption.  

**MANOVA Results:**

| Comparison | Wilks’ Lambda | F | p-value |
|------------|---------------|---|---------|
| CAT1 vs CAT2 | 0.46279 | 21.281 | 8.41e-09 |
| CAT1 vs CAT3 | 0.18891 | 78.713 | < 2.2e-16 |
| CAT2 vs CAT3 | 0.48994 | 19.086 | 3.93e-08 |

**Confidence Intervals:** Significant differences in swim, bike, and run across categories.

**Conclusion:** Age strongly influences overall performance in the triathlon dataset.

---

## Visualizations

- Chi-square Q-Q plots for multivariate normality  
- 3D scatterplots for triathlon performance  
- Scatterplot matrices for pairwise relationships  

---

## R Scripts & Libraries

**Libraries used:** `MVN`, `DescTools`, `heplots`, `car`, `scatterplot3d`  

**Key Scripts:**
- `HotellingsT2Test()` – Hotelling’s T² and Chi-square tests  
- `cqplot()` – Chi-square Q-Q plots  
- `mvn()` – Multivariate normality tests  
- `scatterplot3d()` – 3D scatterplots  
- MANOVA with `car` package  

---

**Key Skills Demonstrated:**  
- Multivariate analysis (MVN testing, Hotelling’s T², MANOVA)  
- Statistical modeling and hypothesis testing  
- Data visualization (2D and 3D plots)  
- Reproducible research and reporting
