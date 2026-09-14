# SmartPlan — Experimentation & Prioritization

## 1. Experimentation Objective

Validate whether SmartPlan can increase scheduled-delivery adoption among eligible non-urgent orders without negatively impacting checkout conversion, delivery reliability or customer experience.

The experimentation strategy focuses on three key levers:

1. Smart slot recommendations
2. Savings communication
3. Checkout placement

---

# 2. Experimentation Framework

Each experiment follows:

**Hypothesis → Control → Variant → Primary Metric → Guardrail Metrics → Decision**

The goal is to validate user behavior before scaling the product.

---

# 3. Experiment 1 — Smart Slot Recommendation

## Hypothesis

> Showing users a personalized recommended delivery slot will increase scheduled-delivery selection compared with asking users to manually choose a slot.

### Control — A

```text
Choose a delivery slot

Instant Delivery
10–15 min

Scheduled Delivery
Choose a time
```

### Variant — B

```text
SmartPlan — Recommended

Tomorrow · 7–9 AM
₹0 delivery
Save ₹39

[Schedule with SmartPlan]
```

### Primary Metric

**Scheduled-slot conversion rate**

Percentage of eligible checkout users selecting a scheduled slot.

### Secondary Metrics

* Checkout conversion
* Slot selection rate
* Order completion rate
* Delivery cancellation rate

### Guardrail Metrics

* Checkout abandonment
* Customer complaints
* Late delivery rate

### Expected Outcome

The recommendation should reduce decision effort and increase scheduled-delivery selection.

---

# 4. Experiment 2 — Savings Messaging

## Hypothesis

> Clearly communicating the monetary benefit of scheduled delivery will increase scheduled-order adoption.

### Control — A

```text
Scheduled Delivery

Tomorrow · 7–9 AM
```

### Variant — B

```text
Save ₹39 with Scheduled Delivery

Tomorrow · 7–9 AM
```

### Primary Metric

**Scheduled-order share**

### Secondary Metrics

* Delivery option selection
* Checkout conversion
* Average order value

### Guardrail Metrics

* Cancellation rate
* Customer complaints
* Checkout abandonment

### Expected Outcome

Showing an explicit financial benefit should improve users' perceived value of waiting.

---

# 5. Experiment 3 — Checkout Placement

## Hypothesis

> Making SmartPlan more prominent during checkout will increase scheduled-delivery selection.

### Control — A

Instant delivery is displayed first.

```text
Deliver Now
10–15 min

Scheduled Delivery
Tomorrow
```

### Variant — B

SmartPlan is highlighted as the recommended option.

```text
⭐ Recommended for your order

SmartPlan
Tomorrow · 7–9 AM
Save ₹39

Deliver Now
10–15 min
```

### Primary Metric

**Scheduled-delivery selection rate**

### Secondary Metrics

* Checkout conversion
* SmartPlan engagement
* Order completion rate

### Guardrail Metrics

* Instant-delivery conversion
* Checkout abandonment
* Customer complaints

---

# 6. Experiment Summary

| Experiment                | Hypothesis                                   | Primary Metric            |
| ------------------------- | -------------------------------------------- | ------------------------- |
| Smart Slot Recommendation | Recommendations increase scheduled selection | Scheduled-slot conversion |
| Savings Messaging         | Savings communication increases adoption     | Scheduled-order share     |
| Checkout Placement        | Higher visibility increases adoption         | Scheduled-selection rate  |

---

# 7. Decision Framework

Experiments should be evaluated using both **growth and customer-experience metrics**.

### Scale

Scale the variant when:

* Primary metric shows meaningful improvement
* Checkout conversion does not deteriorate
* Guardrail metrics remain within acceptable limits
* Delivery reliability is maintained

### Iterate

Iterate when:

* Adoption improves but customer experience declines
* Results are inconclusive
* Impact differs significantly across user segments

### Stop

Stop the experiment when:

* Scheduled adoption decreases
* Checkout abandonment materially increases
* Delivery reliability deteriorates
* Customer complaints increase significantly

---

# 8. User Segmentation

Experiment results should be analyzed across relevant user segments rather than relying only on aggregate performance.

### Segments

* Frequent vs occasional users
* New vs returning users
* Small vs large baskets
* Planned vs potentially urgent purchases
* High vs low order frequency

This helps identify where SmartPlan creates the highest value.

---

# 9. Impact-Effort Prioritization

Before experimentation, proposed features were evaluated using an **Impact-Effort framework**.

| Feature                   | Customer Impact | Business Impact | Effort | Priority |
| ------------------------- | --------------- | --------------- | ------ | -------- |
| Smart slot recommendation | High            | High            | Medium | P0       |
| Savings visibility        | High            | High            | Low    | P0       |
| Checkout placement        | High            | High            | Low    | P0       |
| Smart reminders           | Medium          | Medium          | Medium | P1       |
| Recurring orders          | High            | High            | High   | P1       |
| Advanced personalization  | Medium          | Medium          | High   | P2       |

---

# 10. Prioritization Logic

### P0 — Build First

Features that have:

* High customer impact
* High business impact
* Manageable implementation effort
* Strong measurement potential

### P1 — Build Next

Features with meaningful potential but requiring additional product or technical complexity.

### P2 — Explore Later

Features requiring stronger evidence, infrastructure or personalization capabilities.

---

# 11. Prioritization Matrix

```text
                         IMPACT
                           ↑
                           │
        HIGH IMPACT       │
                           │
       Smart Slots        │       Savings Visibility
       Smart Reminders    │       Checkout Placement
                           │
                           │
        LOW IMPACT        │       Advanced Personalization
                           │       Recurring Orders
                           │
                           └────────────────────────→
                              LOW EFFORT       HIGH EFFORT
```

---

# 12. Measurement Plan

## North-Star Metric

### Scheduled Order Share

```text
Scheduled Orders
──────────────────────── × 100
Eligible Orders
```

This measures whether eligible users are actually shifting toward scheduled delivery.

---

## Supporting Metrics

### Scheduled Conversion

```text
Scheduled Orders
──────────────────────── × 100
Users Viewing Delivery Options
```

### Delivery Cost per Order

```text
Total Delivery Cost
────────────────────
Completed Orders
```

### SLA Compliance

```text
Orders Delivered Within Promised Window
──────────────────────────────────────── × 100
Total Scheduled Orders
```

---

# 13. Target Metrics

| Metric                    | Baseline* | Target |
| ------------------------- | --------: | -----: |
| Scheduled-order share     |        6% |    15% |
| Delivery cost/order       |      100% |   -15% |
| Scheduled delivery SLA    |       95% |   ≥97% |
| Scheduled-slot conversion |      100% |   +20% |

*Baseline values are illustrative assumptions for this case study and are not actual Zepto data.

---

# 14. Analytics Funnel

```text
Checkout Users
      │
      ↓
Delivery Options Viewed
      │
      ↓
SmartPlan Recommendation Shown
      │
      ↓
Scheduled Slot Selected
      │
      ↓
Scheduled Order Confirmed
      │
      ↓
Order Delivered
```

### Key Drop-off Points

The product team should monitor:

**1. Delivery options → SmartPlan viewed**

Indicates visibility of the recommendation.

**2. SmartPlan viewed → Scheduled slot selected**

Indicates perceived value and usability.

**3. Scheduled selected → Order confirmed**

Indicates checkout friction.

**4. Order confirmed → Order delivered**

Measures operational reliability.

---

# 15. Instrumentation

The following events should be tracked:

```text
delivery_option_viewed
smartplan_shown
smartplan_clicked
scheduled_slot_viewed
scheduled_slot_selected
instant_delivery_selected
scheduled_order_confirmed
scheduled_order_cancelled
scheduled_order_delivered
```

### Example Event

```text
Event: smartplan_clicked

Properties:
- user_id
- order_id
- recommended_slot
- delivery_fee
- estimated_savings
- basket_value
- user_segment
```

---

# 16. Experimentation Roadmap

### Phase 1

Test:

* Savings messaging
* SmartPlan visibility

### Phase 2

Test:

* Slot recommendation logic
* Personalized recommendations

### Phase 3

Test:

* Dynamic incentives
* Capacity-aware recommendations
* Recurring-order recommendations

---

# 17. Expected Product Impact

If validated successfully, SmartPlan could create value across three dimensions:

### Customer

**Convenient planning + transparent savings**

### Business

**Higher scheduled-order adoption + lower delivery cost**

### Operations

**More predictable demand + improved delivery capacity utilization**

---

## Key Product Principle

> **Don't force users to wait. Give them a better reason to choose when they don't need to rush.**

This principle guides the SmartPlan product strategy.
