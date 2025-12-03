# SEIS-631-Final-project- 
## Project Title: US Housing Price Analysis

---

## 1. Research Question
I am interested in understanding the distribution of price-per-bedroom. Specifically, do Colorado and Minnesota have the same avg price per bedroom?

---

## 2. Hypothesis
- **Null Hypothesis (H₀):** Colorado and Minnesota have the same distribution of price-per-bedroom.  
- **Alternative Hypothesis (H₁):** Colorado and Minnesota differ in price-per-bedroom.

---

## 3. Data Description
- **Dataset:** *US_Housing* dataset  
- **Source:** Kaggle.com  
- **Unit of Analysis:** Each observation represents a single housing record.  
- **Key Variables:**  
  - `Price` — Housing price  
  - `Avg. Area Income` — Average income in the surrounding area  
  - (Other variables may include area population, number of rooms, etc.)  
- **Cleaning/Filtering Steps:**  
  - Removed rows with missing values  
  - Verified columns were in correct numeric format  
  - Created indicator for “high-income area” using an income threshold (if applicable)
  - Extract cities and states from the addresses columns 

---

## 4. Methods
### Permutation Test
- **Test Statistic:** The difference in mean housing prices between high-income and non-high-income areas.  
- **Simulation Under the Null:**  
  - Shuffle the income-group labels randomly across all observations.  
  - Recalculate the difference in mean housing prices for each shuffle.  
  - Repeat the shuffle **5,000 times** to form the null distribution.

### Bootstrap Confidence Intervals
- **Metric:** Difference in mean housing price between groups.  
- **Procedure:**  
  - Resample each group *with replacement*.  
  - Compute the difference in group means.  
  - Repeat many times to form a bootstrap distribution and construct a confidence interval.

### Why the CLT Does Not Apply
- The distribution of income or housing price may be skewed or heavy-tailed, making normal-approximation–based inference unreliable.  
- Bootstrapping does not require normality and provides more accurate uncertainty estimates.

---

## 5. Results
(You will insert your results here after running your analysis.)

- Summary statistics and visualizations  
- Observed test statistic  
- Permutation test p-value  
- Bootstrap confidence interval for the difference in means  

---

## 6. Uncertainty Estimation
- Number of resamples used: **5,000 permutation shuffles** and (recommended) **10,000 bootstrap samples**  
- Interpreting the distributions:
  - The permutation distribution represents what differences would look like if income had *no* effect on housing prices.  
  - The bootstrap distribution shows the sampling variability of the observed difference.  
- Interpretation will depend on whether the CI includes zero and how extreme the observed statistic is compared to the null distribution.

---




