# AB-Testing-of-Marketing-Campaign

Organizations require rigorous validation that new advertisements outperform baselines and identification of temporal and frequency optimization factors.

## Objectives:

1.	Validate new advertisement effectiveness versus control
2.	Identify optimal days and hours for campaign deployment
3.	Quantify frequency impact on conversion
4.	Establish a reproducible A/B testing framework

## Cleaning Steps:
1.	Verified no duplicate User IDs
2.	Removed non-predictive columns (index, User ID)
3.	Reclassified "Most Ads Hour" as categorical (not numerical)
4.	Validated category completeness; no case-sensitivity issues

## Exploratory Data Analysis:

> ### Univariate Analysis

*	### Test Group: 96% received new ad, 4% received PSA(Public Service Announcement)
  
<img width="588" height="390" alt="image" src="https://github.com/user-attachments/assets/02ee8c7f-7e07-489b-80a9-b0979d74ac70" />

*	### Conversion Rate: Extremely low baseline (2.5% overall) reflects realistic digital advertising performance

<img width="589" height="390" alt="image" src="https://github.com/user-attachments/assets/fe592499-873b-45aa-bf6e-c2e17458a264" />

*	### Temporal Distribution Of Most Ad Day: Peak ad exposure Friday (day)

<img width="591" height="390" alt="image" src="https://github.com/user-attachments/assets/ed335180-36dd-46c0-b33c-2e0cc20254f6" />

* ### Temporal Distribution Of Most Ad Hour:1 PM (hour), minimal overnight exposure

<img width="770" height="390" alt="image" src="https://github.com/user-attachments/assets/cb910ef7-75f8-41d8-9e21-c3f074201d9b" />

* ### Total Ads: Right-skewed distribution; median 10 ads with outliers to 100+; 75th percentile at 27 ads

<img width="589" height="390" alt="image" src="https://github.com/user-attachments/assets/765455d0-fe89-4e36-a337-731998c9d125" />

> #### Bivariate Analysis

* ### Test Group Vs Conversion:

  <img width="547" height="443" alt="image" src="https://github.com/user-attachments/assets/7d9a4106-b85b-4c90-b395-2ef86c6431d3" />

  *AD: 2.5% conversion; PSA: 1.78% (+0.72 pp, 40% relative improvement)*

* ### Most Ads Day Vs Conversion:

<img width="547" height="499" alt="image" src="https://github.com/user-attachments/assets/334fa61a-9a77-470e-967b-5df1fc28ffe8" />

*Monday peak 3.2%; systematic decline to Friday 2.7%*

* ### Most Ads Hours Vs Conversion:

<img width="547" height="436" alt="image" src="https://github.com/user-attachments/assets/497160d4-1107-428a-8a34-dd75f7b48851" />

*4 PM highest; 2-8 PM window concentration; overnight reduced conversion rate*

* ### Total Ads Vs Conversion:

<img width="562" height="432" alt="image" src="https://github.com/user-attachments/assets/4bc3033b-3264-4f28-a5a9-781f30c2bfdb" />

*Converters median 25 ads; non-converters median 10 ads (2.5x difference)*

## Statistical Analysis

> ### Chi-Square Test (Categorical Independence)
  <img width="988" height="816" alt="image" src="https://github.com/user-attachments/assets/6b308ac9-fd07-47b5-90d2-515074404166" />

> ### Shapiro Test, Levene's Test, Mann-Whitney Test:

* Shapiro-Wilk Test: Checked if ad exposure was normally distributed. Both groups failed (p < 0.05) due to right-skewed distribution with outliers.
* Levene's Test: Checked if both groups had equal variance. Failed (p < 0.05) because converters and non-converters had different spreads.
* Since both distributions are not normal and have different variances, a non parametric test is selected.
* Mann-Whitney U test is selected, and the p-value < 0.001 confirms the median difference is statistically real.
 
 <img width="940" height="91" alt="image" src="https://github.com/user-attachments/assets/d1ca2a0a-8fdb-4da6-92e9-a88f4d3a0a61" />

<img width="575" height="50" alt="image" src="https://github.com/user-attachments/assets/96bfb14e-fa91-4405-8f4c-601f631d05b0" />

### Result

All the findings point to the conclusion that the conversion is overwhelmingly dependent on Test Group, Most Ads day, Most Ads hour, Total Ads.
