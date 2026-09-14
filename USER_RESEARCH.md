# Zepto Scheduled Delivery Optimization — User Research

## 1. Research Objective

Understand why users may prefer instant delivery over scheduled delivery and identify opportunities to improve scheduled-delivery adoption for non-urgent grocery purchases.

### Key Research Question

> **What prevents users from choosing scheduled delivery when their purchase does not require immediate delivery?**

---

# 2. Research Approach

This project follows a **hypothesis-driven product research approach** combining:

### Secondary Research

Reviewed publicly available information related to:

* Quick-commerce customer experience
* Instant vs scheduled delivery models
* Delivery-slot selection
* Grocery purchase behavior
* Competitor delivery experiences

### User Journey Analysis

Mapped the delivery journey from product discovery to order completion to identify potential friction points.

### Competitive Experience Analysis

Compared common delivery-selection patterns across quick-commerce and e-commerce experiences to identify potential UX opportunities.

### Hypothesis Development

Converted observed patterns into testable product hypotheses rather than treating assumptions as confirmed user behavior.

> **Research note:** This is an independent case study. It does not use proprietary Zepto customer data. Findings are hypotheses based on secondary research, journey analysis and product assumptions.

---

# 3. Target User

## Primary Segment

**Frequent quick-commerce users**

### Characteristics

* Regularly purchase groceries and household products
* Value convenience and predictable delivery
* Frequently use instant delivery
* May have both urgent and planned purchases
* Are sensitive to delivery time and cost

---

# 4. User Jobs-to-be-Done

### Functional Job

> Get groceries and household products delivered when needed with minimum effort.

### Emotional Job

> Feel confident that the order will arrive when expected.

### Economic Job

> Avoid unnecessary delivery costs when immediate delivery is not required.

---

# 5. User Journey

```text
Need arises
     ↓
Open Zepto
     ↓
Search / browse products
     ↓
Add products to cart
     ↓
Review cart
     ↓
Proceed to checkout
     ↓
Select delivery option
     ↓
Instant / Scheduled
     ↓
Confirm order
     ↓
Track delivery
     ↓
Receive order
```

---

# 6. Journey Pain-Point Analysis

| Stage             | Potential Pain Point                      | User Need   | Product Opportunity                   |
| ----------------- | ----------------------------------------- | ----------- | ------------------------------------- |
| Need recognition  | User may not plan delivery timing         | Convenience | Introduce planning cues               |
| Product discovery | Delivery timing is not top-of-mind        | Simplicity  | Surface scheduled option contextually |
| Cart              | No clear reason to wait                   | Value       | Communicate savings                   |
| Checkout          | Instant delivery may dominate attention   | Choice      | Improve scheduled-delivery visibility |
| Slot selection    | Multiple slots may create decision effort | Guidance    | Recommend suitable slot               |
| Confirmation      | Reliability may be uncertain              | Confidence  | Show delivery commitment              |
| Repeat purchase   | Users may repeatedly order same items     | Convenience | Smart reminders                       |

---

# 7. Key Hypotheses

## H1 — Visibility

> Users are more likely to consider scheduled delivery when it is prominently presented during checkout.

### Validation

A/B test scheduled-delivery placement.

---

## H2 — Value

> Explicitly communicating savings will increase users' willingness to choose scheduled delivery.

### Validation

Compare generic scheduled-delivery messaging with explicit savings messaging.

---

## H3 — Decision Effort

> Recommending an appropriate delivery slot will increase scheduled-slot selection compared with manual slot selection.

### Validation

Compare SmartPlan recommendation against standard slot selection.

---

## H4 — Habit

> Reminding users about recurring purchases can increase planned-order behavior.

### Validation

Measure engagement and conversion from personalized scheduled-order reminders.

---

# 8. Research Insights

## Insight 1 — Urgency is not universal

Quick-commerce purchases can range from urgent needs to planned household purchases.

### Implication

Scheduled delivery should primarily target **eligible non-urgent purchases** rather than replacing instant delivery.

---

## Insight 2 — Convenience drives the default

Instant delivery communicates an immediate and simple value proposition:

> **Get it now.**

Scheduled delivery requires the user to understand why waiting provides additional value.

### Implication

SmartPlan needs a strong value proposition rather than simply adding another delivery option.

---

## Insight 3 — Savings can change perceived value

A scheduled option becomes more attractive when users can immediately understand the trade-off.

### Example

```text
Deliver Now
₹39

SmartPlan
Tomorrow · 7–9 AM
₹0

You save ₹39
```

---

## Insight 4 — Choice overload can create friction

Showing multiple delivery slots without guidance can make users evaluate unnecessary options.

### Implication

Recommend one suitable slot while preserving user control.

---

## Insight 5 — Reliability is a prerequisite

Users may accept a slower delivery window only when the promised delivery time is credible.

### Implication

SmartPlan should use reliability and capacity thresholds before recommending a slot.

---

# 9. Opportunity Areas

Based on the journey and hypothesis analysis, four opportunity areas were identified.

### Opportunity 1 — Make scheduled delivery visible

Surface SmartPlan during relevant checkout moments.

### Opportunity 2 — Communicate the benefit

Show potential savings and convenience.

### Opportunity 3 — Reduce decision effort

Recommend the most suitable delivery window.

### Opportunity 4 — Build repeat behavior

Use purchase patterns to remind users about planned orders.

---

# 10. Opportunity Prioritization

| Opportunity               | User Impact | Business Impact | Effort | Priority |
| ------------------------- | ----------- | --------------- | ------ | -------- |
| Smart slot recommendation | High        | High            | Medium | P0       |
| Savings communication     | High        | High            | Low    | P0       |
| Checkout visibility       | High        | High            | Low    | P0       |
| Smart reminders           | Medium      | Medium          | Medium | P1       |

---

# 11. Research → Product Decisions

| Research Finding                              | Product Decision                  |
| --------------------------------------------- | --------------------------------- |
| Users may not actively consider scheduling    | Surface SmartPlan during checkout |
| Waiting needs a clear benefit                 | Show explicit savings             |
| Slot selection can require decision effort    | Recommend a smart slot            |
| Reliability affects willingness to wait       | Use SLA/capacity thresholds       |
| Repeat purchases offer planning opportunities | Introduce smart reminders         |

---

# 12. Validation Plan

The research hypotheses should be validated through controlled product experiments.

### Phase 1 — Validate Value

Test savings messaging.

### Phase 2 — Validate UX

Test SmartPlan recommendation and checkout placement.

### Phase 3 — Validate Retention

Test smart reminders for repeat purchases.

### Phase 4 — Validate Operations

Measure whether increased scheduled-order adoption improves delivery efficiency without degrading SLA.

---

# 13. Research Limitations

This case study has several limitations:

* No access to proprietary Zepto customer data
* No production experiment results
* User behavior assumptions require primary validation
* Proposed baseline and target metrics are illustrative
* Product feasibility would require access to operational and delivery-capacity data

These limitations would be addressed during a real product discovery process through user interviews, surveys, behavioral analytics and controlled experiments.

---

# 14. Next Research Steps

Before production development, the following research would be conducted:

### Qualitative

* 10–15 user interviews
* Usability testing of SmartPlan
* Checkout preference interviews

### Quantitative

* Survey of delivery preferences
* Analysis of instant vs scheduled order behavior
* Funnel analysis
* Segmentation by order frequency and basket type

### Product Validation

* Prototype testing
* A/B testing
* Cohort analysis
* Delivery reliability analysis

---

# 15. Research Summary

The research indicates four key product opportunities:

```text
Visibility
    +
Value
    +
Decision Support
    +
Reliability
    ↓
SmartPlan
```

SmartPlan therefore focuses on making scheduled delivery:

**More visible → More valuable → Easier to choose → More reliable**

---

## Final Product Insight

> **The opportunity is not to replace instant delivery, but to make scheduled delivery the smarter choice when users don't need to rush.**

---

## Research Disclaimer

This is an independent Product Management case study created for learning and portfolio purposes. The research approach uses publicly available information, product journey analysis and clearly stated hypotheses. No proprietary Zepto data or confidential information was used.
