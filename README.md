## Business Problem

The company recently introduced a new onboarding and activation campaign for new users of its subscription-based digital product. Users were randomly assigned to either the existing onboarding experience (Control group) or the new onboarding experience (Treatment group).

The main business decision is whether the new onboarding experience should be launched to all users or whether additional testing is required.

This decision directly impacts business leadership, the product team, the marketing team, and future users of the platform. A successful onboarding experience should improve user activation, increase paid conversions, and generate higher long-term revenue while maintaining a positive user experience.

Although improving conversion is the primary objective, the company must also monitor important guardrail metrics such as refund rate, support ticket rate, engagement score, and the average time taken to convert. An increase in conversions is not beneficial if it also leads to more customer complaints, lower engagement, or poor user retention.

Before recommending a full rollout, the experiment results must demonstrate a meaningful improvement in the primary success metric while ensuring that the guardrail metrics remain stable or improve.
---
## North Star Metric

### Selected North Star Metric

**Paid Conversion Rate**

The Paid Conversion Rate has been selected as the North Star Metric because it directly measures how effectively the new onboarding experience converts users into paying customers. Since the primary objective of the experiment is to improve user activation and increase subscriptions, this metric best reflects the overall success of the campaign.

### Why This Is the Main Success Metric

An increase in paid conversions has a direct impact on business revenue and customer growth. Unlike engagement metrics, which only indicate user activity, paid conversions demonstrate that users found enough value in the product to purchase a subscription. This makes it the most meaningful measure for evaluating the effectiveness of the new onboarding experience.

### Supporting Metrics

While Paid Conversion Rate is the primary success metric, several supporting metrics provide additional context:

* **Landing Page Visit Rate** indicates whether users reached the onboarding experience.
* **Trial Start Rate** measures initial user interest.
* **Onboarding Completion Rate** shows how many users successfully completed the onboarding process.
* **Average Revenue Per User (ARPU)** evaluates the financial impact of the campaign.
* **Engagement Score** measures how actively users interact with the product after onboarding.

These metrics help explain *why* the Paid Conversion Rate increased or decreased but do not directly represent business success.

### Connection to Business Growth

A higher Paid Conversion Rate increases the number of paying customers, leading to higher subscription revenue, improved customer acquisition efficiency, and stronger long-term business growth. Improving this metric also increases the return on investment for marketing and product development efforts.

### Risk of Optimizing Only This Metric

Focusing only on Paid Conversion Rate could lead to poor business decisions. For example, a campaign might increase conversions by using aggressive promotions or misleading messaging, but this could also increase refund requests, customer complaints, or reduce long-term engagement. For this reason, Paid Conversion Rate should always be evaluated alongside guardrail metrics such as Refund Rate, Support Ticket Rate, Engagement Score, and Days to Convert.
---
## KPI Tree Summary

The KPI Tree was created to show how the selected North Star Metric, **Paid Conversion Rate**, is influenced by different stages of the customer journey.

Three primary drivers were identified:

- User Acquisition
- User Activation
- User Engagement

Each driver contains supporting KPIs that help explain changes in the North Star Metric. In addition, guardrail metrics such as Refund Rate, Support Ticket Rate, and Average revenue per user were included to ensure that improvements in conversions do not negatively affect customer satisfaction or business performance.

This structure provides a balanced framework for evaluating the success of the onboarding experiment and supports data-driven decision-making.
---
## Experiment Data Preparation

Before analysing the experiment results, the dataset was reviewed to ensure it was suitable for comparison between the Control and Treatment groups. Several data quality checks were performed before any calculations or summaries were created.

### Missing Values

The dataset was checked for missing values across all columns. The following missing values were identified:

| Column           | Missing Values |
| ---------------- | -------------: |
| Region           |             18 |
| Device Type      |             24 |
| Refund Requested |           1336 |
| Days to Convert  |             14 |

The missing values were documented for analysis. No values were modified unless required by the assignment, ensuring the original experiment data remained unchanged.

### Experiment Group Distribution

The number of users assigned to each experiment group was verified to confirm that both groups were reasonably balanced.

| Experiment Group | User Count |
| ---------------- | ---------: |
| Control          |        693 |
| Treatment        |        715 |
| **Total**        |   **1408** |

The small difference in group size is acceptable and allows for a fair comparison of experiment outcomes.

### Duplicate User IDs

The dataset was checked for duplicate User IDs.

* Duplicate User IDs identified: **8**
* Total duplicate records involved: **16**

These records were retained and documented because the assignment required duplicate User IDs to be identified rather than removed automatically.

### Binary Value Validation

The following binary columns were validated:

* Visited Landing Page
* Started Trial
* Completed Onboarding
* Converted to Paid
* Refund Requested

All binary fields contained valid values (0 or 1), and no invalid entries were found.

### Revenue Outlier Check

The **Revenue (30 Days)** column was analysed using the Interquartile Range (IQR) method to detect unusually high or low values.

No revenue outliers were identified, indicating that the revenue values fall within the expected range for this experiment.

### Segment Distribution

To ensure that the experiment groups were comparable, the distribution of users across key segments was reviewed using Pivot Tables.

**Region Distribution**

* East: 158 Control, 172 Treatment
* North: 203 Control, 180 Treatment
* South: 184 Control, 184 Treatment
* West: 148 Control, 179 Treatment

The regional distribution is reasonably balanced, with only minor differences between the two groups.

**Device Type Distribution**

* Desktop: 200 Control, 214 Treatment
* Mobile: 428 Control, 436 Treatment
* Tablet: 56 Control, 56 Treatment
* A small number of records contained missing device information (9 users in each group).

The device distribution is consistent across both experiment groups.

**Traffic Source Distribution**

The majority of users came from Organic Search, followed by Paid Search, Social, Referral, and Email. A small number of records contained missing traffic source information (6 in the Control group and 18 in the Treatment group). Overall, the traffic source distribution is sufficiently balanced to support a fair comparison between the Control and Treatment groups.

### Conclusion

The dataset was successfully prepared for analysis. Although a small number of missing values and duplicate User IDs were identified, the Control and Treatment groups remain well balanced across the major user segments. No invalid binary values or revenue outliers were found, making the dataset suitable for the experiment analysis and hypothesis testing performed in the following tasks.
