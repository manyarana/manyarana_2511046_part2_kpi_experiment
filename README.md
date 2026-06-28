# KPI Framework, Business Experiment Analysis & Decision Recommendation

## Business Context

This project analyzes an A/B experiment conducted by a subscription-based digital product company. The company introduced a new onboarding experience with the goal of improving user activation and increasing the number of users who convert to paid subscriptions.

Users were randomly assigned to one of two groups:

* **Control Group:** Existing onboarding experience
* **Treatment Group:** New onboarding experience

The objective of this project is to determine whether the new onboarding experience performs better than the existing one while ensuring that it does not negatively affect other important business metrics.

---

# Dataset Description

The dataset contains user-level experiment data for **1,408 users** and includes information such as:

* User ID
* Signup Date
* Experiment Group
* Region
* Device Type
* Traffic Source
* Plan Type
* Landing Page Visit
* Trial Start
* Onboarding Completion
* Paid Conversion
* Revenue (30 Days)
* Support Tickets
* Refund Requests
* Days to Convert
* Engagement Score

The dataset was used to compare the performance of the Control and Treatment groups across several business and product metrics.

---

# Business Problem

The company must decide whether the new onboarding campaign should replace the existing onboarding experience.

The decision should not be based only on whether more users convert to paid subscriptions. It should also consider whether the new onboarding experience introduces any negative effects, such as increased customer support requests, higher refund rates, or lower revenue quality.

---

# North Star Metric

The North Star Metric selected for this experiment is **Paid Conversion Rate**.

**Paid Conversion Rate = Number of Paid Users ÷ Total Users**

This metric was chosen because it directly measures the primary business objective of increasing subscription growth. While other metrics provide useful insights into user behaviour, Paid Conversion Rate has the greatest impact on long-term business revenue and customer acquisition.

---

# KPI Tree Summary

The KPI Tree was designed around the Paid Conversion Rate.

### Primary KPI Drivers

* Landing Page Visit Rate
* Trial Start Rate
* Onboarding Completion Rate

### Supporting Business Metrics

* Average Revenue Per User
* Average Engagement Score
* Average Days to Convert

### Guardrail Metrics

* Refund Rate
* Support Ticket Rate
* Average Revenue Per Converted User

These guardrail metrics ensure that improvements in conversions are not achieved at the cost of customer experience or business quality.

---

# Experiment Data Preparation

Before beginning the analysis, several data quality checks were performed.

### Missing Values

The following missing values were identified:

| Column           | Missing Values |
| ---------------- | -------------: |
| Region           |             18 |
| Device Type      |             24 |
| Refund Requested |           1336 |
| Days to Convert  |             14 |

### Experiment Groups

| Group     | Users |
| --------- | ----: |
| Control   |   693 |
| Treatment |   715 |

The groups were reasonably balanced and suitable for comparison.

### Duplicate User IDs

* Duplicate User IDs: **8**
* Duplicate Records: **16**

These records were documented and retained for review instead of being removed automatically.

### Binary Value Validation

All binary fields contained valid values (0 or 1). No invalid binary values were found.

### Revenue Outlier Check

Revenue values were checked using the Interquartile Range (IQR) method. No revenue outliers were identified.

### Segment Distribution

The distribution of users across Region, Device Type, and Traffic Source was reviewed using Pivot Tables. The Control and Treatment groups were reasonably balanced across these segments, allowing for a fair comparison during the experiment analysis.

---

# Experiment Analysis Approach

The experiment was evaluated by comparing the Control and Treatment groups across key performance metrics.

The following metrics were calculated:

* User Count
* Landing Page Visit Rate
* Trial Start Rate
* Onboarding Completion Rate
* Paid Conversion Rate
* Average Revenue Per User
* Average Revenue Per Converted User
* Refund Rate
* Support Ticket Rate
* Average Engagement Score
* Average Days to Convert

Additional segment-level analysis was performed using Pivot Tables for:

* Region
* Device Type
* Traffic Source

---

# Hypothesis Test Summary

A one-tailed two-proportion Z-test was performed to determine whether the Treatment group achieved a statistically significant improvement in Paid Conversion Rate.

### Test Results

| Metric             | Value           |
| ------------------ | --------------- |
| Standard Error     | 0.011742174     |
| Z-Score            | 3.251871262     |
| P-Value            | 0.0005732396869 |
| Significance Level | 0.05            |

Since the p-value is significantly lower than 0.05, the Null Hypothesis was rejected.

This provides strong statistical evidence that the new onboarding experience improved the Paid Conversion Rate compared with the existing onboarding process.

---

# Guardrail Metrics Considered

Although the Treatment group showed a significant improvement in Paid Conversion Rate, additional business metrics were evaluated before making a recommendation.

### Positive Outcomes

* Landing Page Visit Rate increased from **63.64%** to **72.59%**.
* Trial Start Rate increased from **25.11%** to **29.09%**.
* Onboarding Completion Rate increased from **15.58%** to **21.26%**.
* Paid Conversion Rate improved from **3.17%** to **6.99%**.
* Average Engagement Score increased from **57.03** to **62.93**.
* Average Days to Convert decreased from **8.86 days** to **6.40 days**.
* Average Revenue Per User increased slightly from **51.75** to **53.88**.

### Risks Identified

* Support Ticket Rate increased from **14.72%** to **24.76%**.
* Refund Rate increased slightly from **0.00%** to **0.42%**.
* Average Revenue Per Converted User decreased from **1630.10** to **770.41**.

These findings indicate that while the new onboarding experience improved conversions and engagement, it also introduced some operational risks that should be monitored.

---

# Final Recommendation

Based on the experiment results and guardrail analysis, the recommended decision is:

## **Launch only for selected segments**

The Treatment group delivered a statistically significant improvement in Paid Conversion Rate and showed positive improvements in engagement, onboarding completion, and overall revenue per user.

However, the increase in customer support requests and the decline in Average Revenue Per Converted User suggest that a full rollout should be approached cautiously. A phased rollout will allow the company to continue monitoring these guardrail metrics while benefiting from the improved conversion performance.

---

# Assumptions and Limitations

### Assumptions

* The experiment groups were randomly assigned.
* All recorded user events accurately represent user behaviour.
* Revenue values reflect the first 30 days after signup.
* The experiment period is representative of normal user activity.

### Limitations

* Some missing values were present in the Region, Device Type, Refund Requested, and Days to Convert columns.
* Duplicate User IDs were identified but retained for review.
* The analysis is based on a single experimental dataset and does not measure long-term customer retention or lifetime value.
* External business factors that may influence user behaviour were not included in the dataset.

---

# Repository Structure

```text
part2_kpi_experiment/
├── data/
│   └── campaign_experiment_data.xlsx
├── analysis/
│   ├── experiment_analysis.xlsx
│   └── hypothesis_test_notes.md
├── outputs/
│   ├── experiment_summary.xlsx
│   ├── kpi_tree.png
│   └── recommendation_memo.md
├── screenshots/
│   ├── summary_metrics.png
│   ├── hypothesis_test_output.png
│   └── kpi_tree_preview.png
└── README.md
```

---

# Screenshots Included

The repository contains the following screenshots as required:

* **summary_metrics.png** – Overall comparison of the Control and Treatment groups.
* **hypothesis_test_output.png** – Evidence of the hypothesis test calculations and results.
* **kpi_tree_preview.png** – Preview of the KPI Tree used in the analysis.

---

# Conclusion

The analysis demonstrates that the new onboarding experience has a positive impact on user conversion and engagement. Statistical testing confirms that the improvement in Paid Conversion Rate is significant, making the Treatment onboarding experience a promising alternative to the existing process.

At the same time, the increase in Support Ticket Rate and the reduction in Average Revenue Per Converted User highlight the importance of monitoring customer experience and revenue quality during deployment. A phased rollout with continued monitoring is therefore the most balanced and data-driven recommendation.

