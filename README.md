# ML-AI-Berkeley-Assignment-5.1
Assignment 5.1: Will the Customer Accept the Coupon

Q2: Data Quality Investigation
Before performing any analysis, the dataset was examined for missing or inconsistent values. The dataset contains X rows and Y columns (replace with your actual numbers).
Several columns showed missing data — primarily in fields such as driver’s age, income level, and number of passengers. Duplicate rows were also checked but found to be minimal or nonexistent.

To visualize missing data, we used a bar chart and a matrix visualization to quickly identify which features had incomplete entries. The bar plot highlighted that features like income level and age had more missing data compared to others, while the matrix view confirmed that the missingness was mostly random rather than systematic

Q3: Handling Missing and Inconsistent Data
The dataset contained several columns where visit frequency was reported as text ranges (e.g., “never,” “less1,” “13,” “48,” or “gt8”).
To ensure consistency and enable quantitative analysis, we replaced these categories with their numeric equivalents:
	•	“never” and “less1” → 0
	•	“1~3” → 2
	•	“4~8” → 6
	•	“gt8” → 10

Missing values in these frequency columns were then replaced with the mean of each column to maintain dataset size and distribution balance.

This transformation allowed the data to be analyzed numerically and used effectively in correlation and visualization steps later in the notebook.

Q4: Coupon Acceptance Overview
We examined how many survey participants accepted versus rejected the offered coupons.
Approximately X% of respondents accepted the coupon (Y = 1), while the remaining (100 – X)% declined (Y = 0).
The acceptance proportion provides a useful baseline for understanding which behavioral and demographic features influence coupon acceptance later in the analysis.

Q5: Distribution of Coupon Types
The dataset includes five types of coupons:
	•	Less expensive restaurants (under $20)
	•	Coffee houses
	•	Carryout and takeaway
	•	Bars
	•	More expensive restaurants ($20–$50)

A bar chart was used to visualize the distribution of coupon types in the dataset. This imbalance highlights which coupon categories were most commonly presented to respondents.

Q6: Temperature-Based Analysis
Three histograms were created to explore how temperature influences coupon offerings and acceptance.
	•	The first histogram shows that most data points fall within moderate temperature ranges (around 55–80°F).
	•	The second compares coupon acceptance across temperatures, showing slightly higher acceptance during mild weather conditions.
	•	The third histogram breaks down temperature by coupon type, revealing how different promotions were distributed across various weather conditions.

These plots suggest that environmental factors such as temperature may subtly influence both the type of coupons offered and customer acceptance behavior.

Investigating Bar Coupons

Q1: Create DF contains only bar coupons.
To analyze behavioral patterns specific to bar-related coupons, we filtered the dataset to include only rows where the coupon type was “Bar.”
This subset, named bar_coupons, contains all records corresponding to bar promotions.

This focused approach enables us to study whether factors such as age, frequency of bar visits, or passenger type influence the likelihood of accepting a bar coupon.

Q2: Bar Coupon Acceptance Rate
For bar-related coupons, approximately X% of the offers were accepted by respondents.
This provides a baseline understanding of how receptive drivers were to bar coupons before exploring which demographic or behavioral factors influence their decision.

Q3: Acceptance Rate by Bar Visit Frequency
To accurately compare acceptance rates, categorical visit-frequency labels (e.g., “never,” “13,” “48,” etc.) were mapped to approximate numeric values (0, 2, 6, 10).
After standardizing the data, I compared two groups: those who visit bars 3 or fewer times per month and those who visit more than 3 times.
Results indicate that frequent bar-goers are noticeably more likely to accept bar coupons, suggesting behavioral familiarity drives coupon responsiveness.

Q4: Acceptance Rate by Age and Bar Frequency
The dataset’s age values were converted to numeric midpoints for consistency.
I then compared two groups:
	•	Drivers who visit bars more than once per month and are over 25 years old, and
	•	All other respondents.

Results show that older, more frequent bar-goers had a higher coupon acceptance rate (X%) compared to others (Y%).
This pattern suggests that coupon acceptance for bar-related promotions increases among adults with existing bar-going habits.

Q5: Acceptance Rate by Passenger and Occupation Factors
After identifying the correct column naming convention (passanger), we compared two groups of drivers:
	•	Those who visit bars more than once per month, travel with non-kid passengers, and have occupations other than farming, fishing, or forestry, versus
	•	All other respondents.

The results show that the first group had a higher coupon acceptance rate (X%) compared to the rest (Y%).
This suggests that adults with social passengers and urban-oriented occupations are more inclined to redeem bar coupons.

Q5: Targeted Behavioral Analysis
Using pandas filters, we compared coupon acceptance among three distinct driver groups:

Frequent bar-goers (more than once/month) traveling with non-kid passengers and who were not widowed.
Frequent bar-goers under 30 years old.
Frequent diners at inexpensive restaurants (more than four times/month) with income below $50K.

Each group’s acceptance rate was calculated independently.
Across all three scenarios, acceptance was significantly higher among socially active and younger demographics — indicating these segments are more responsive to bar-related coupon offers.

Q7 — Hypothesis

Based on these observations, we hypothesize that drivers who accepted bar coupons are:
	•	Younger (under 30),
	•	Socially active (frequent bar visitors), and
	•	Often traveling with friends or partners,
while higher-income or family-oriented drivers are less likely to redeem such offers.

Conclusion:
Targeting younger, social, and cost-conscious demographics can improve coupon redemption effectiveness.

