# Recommendation Memo

## Executive Summary

This report evaluates the effectiveness of a new onboarding campaign through an A/B experiment comparing a Control group (existing onboarding experience) with a Treatment group (new onboarding experience). The objective was to determine whether the new onboarding flow should be rolled out more broadly by measuring its impact on user conversion while also monitoring key business guardrail metrics.

The analysis shows that the Treatment group achieved a significantly higher Paid Conversion Rate than the Control group. However, some guardrail metrics indicate potential risks that should be addressed before a full rollout.

---

# North Star Metric

The North Star Metric for this experiment is **Paid Conversion Rate**, defined as the percentage of users who converted from free users to paid subscribers.

This metric was selected because it directly reflects the primary business objective of increasing subscription growth and has the strongest impact on long-term revenue.

---

# KPI Tree Summary

The KPI framework was designed around Paid Conversion Rate.

The primary drivers include:

* Landing Page Visit Rate
* Trial Start Rate
* Onboarding Completion Rate

Supporting business outcomes include:

* Average Revenue Per User
* Average Engagement Score
* Average Days to Convert

The following guardrail metrics were monitored to ensure that higher conversions did not negatively impact the overall user experience:

* Refund Rate
* Support Ticket Rate
* Average Revenue Per Converted User

---

# Experiment Results

The comparison between the Control and Treatment groups produced the following results:

| Metric                     |   Control | Treatment |
| -------------------------- | --------: | --------: |
| User Count                 |       693 |       715 |
| Landing Page Visit Rate    |    63.64% |    72.59% |
| Trial Start Rate           |    25.11% |    29.09% |
| Onboarding Completion Rate |    15.58% |    21.26% |
| Paid Conversion Rate       | **3.17%** | **6.99%** |
| Average Revenue Per User   |     51.75 |     53.88 |
| Average Engagement Score   |     57.03 |     62.93 |
| Average Days to Convert    |      8.86 |      6.40 |

The Treatment group outperformed the Control group across all key funnel metrics. More users visited the landing page, started a trial, completed onboarding, and ultimately converted into paying customers. Engagement also increased, and users reached conversion more quickly.

---

# Hypothesis Test Interpretation

A one-tailed two-proportion z-test was performed to determine whether the improvement in Paid Conversion Rate was statistically significant.

**Results**

* Standard Error: 0.011742174
* Z-Score: 3.251871262
* P-Value: 0.0005732396869
* Significance Level (α): 0.05

Since the p-value is much smaller than 0.05, the Null Hypothesis is rejected.

This indicates that the improvement in Paid Conversion Rate is statistically significant and is unlikely to have occurred by random chance.

---

# Guardrail Analysis

Although the primary metric improved significantly, additional guardrail metrics were evaluated before making a business recommendation.

### Positive Findings

* Average Engagement Score increased from **57.03** to **62.93**, indicating stronger user engagement.
* Average Days to Convert decreased from **8.86 days** to **6.40 days**, meaning users subscribed more quickly.
* Average Revenue Per User increased slightly from **51.75** to **53.88**, suggesting a modest improvement in overall revenue.

### Risks Identified

* Support Ticket Rate increased from **14.72%** to **24.76%**, indicating that more users required assistance after experiencing the new onboarding flow.
* Refund Rate increased slightly from **0.00%** to **0.42%**. Although still low, this should continue to be monitored.
* Average Revenue Per Converted User decreased from **1630.10** to **770.41**, indicating that converted users generated less revenue on average.

These findings suggest that while the campaign successfully increased conversions, there may be usability or pricing-related issues that should be investigated further.

---

# Segment-Level Insights

The experiment groups were reviewed across Region, Device Type, and Traffic Source to confirm that the Control and Treatment groups were reasonably balanced before analysis.

Segment-level summaries showed that the Treatment group generally maintained stronger performance across different user segments, indicating that the improvement in Paid Conversion Rate was not limited to a single customer group.

---

# Final Recommendation

**Recommendation: Launch only for selected segments while closely monitoring guardrail metrics.**

The Treatment onboarding experience delivered a statistically significant improvement in the Paid Conversion Rate and also increased engagement while reducing the average time required for users to convert.

However, the increase in Support Ticket Rate and the decline in Average Revenue Per Converted User suggest that a full rollout may introduce additional operational costs or reduce revenue quality.

A phased rollout allows the business to continue benefiting from the improved conversion performance while monitoring customer support demand, refund behaviour, and revenue quality before expanding the onboarding experience to all users.

---

# Risks and Limitations

* Some columns contained missing values, including Region, Device Type, Refund Requested, and Days to Convert.
* Eight duplicate User IDs (16 records) were identified and retained for review.
* The analysis is based on a single experimental dataset and does not capture long-term customer behaviour.
* External factors influencing user behaviour were not included in the analysis.

---

# Next Steps

* Roll out the new onboarding experience to selected user segments.
* Investigate why Support Ticket Rate increased in the Treatment group.
* Analyse the decline in Average Revenue Per Converted User to determine whether pricing or plan selection contributed to the decrease.
* Continue monitoring Refund Rate and customer engagement after deployment.
* Conduct follow-up A/B tests after onboarding improvements are implemented to validate long-term performance.
