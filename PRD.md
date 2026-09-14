# SmartPlan — Product Requirements Document

## 1. Product Overview

**Product:** SmartPlan
**Platform:** Zepto
**Project Type:** Product Management Self Project
**Status:** Concept / MVP Definition

### Product Vision

Enable users to conveniently plan non-urgent grocery purchases through intelligent scheduled-delivery recommendations while helping improve delivery efficiency.

---

# 2. Problem Statement

Users may select instant delivery even when their purchases are not time-sensitive. Scheduled delivery can provide an alternative for planned purchases, but users may not clearly understand its value or which available slot is most suitable.

### Problem

**How might Zepto make scheduled delivery convenient and valuable enough for users to choose it for suitable non-urgent purchases?**

---

# 3. Product Objective

Increase scheduled-order adoption while maintaining customer convenience, delivery reliability and product freshness.

### Business Objectives

* Increase scheduled-order share among eligible orders
* Improve delivery capacity utilization
* Reduce delivery cost per order
* Improve predictability of delivery operations

### Customer Objectives

* Reduce delivery-selection effort
* Provide convenient delivery windows
* Communicate potential savings clearly
* Maintain reliable delivery expectations

---

# 4. Target Users

## Primary User

Frequent quick-commerce users purchasing non-urgent grocery and household products.

### Example Use Cases

* Weekly grocery purchases
* Household supplies
* Packaged food
* Cleaning products
* Planned recurring purchases

## Excluded Use Cases

SmartPlan should not aggressively recommend scheduled delivery when:

* The user indicates urgency
* Products have strict freshness requirements
* No suitable scheduled slot exists
* Delivery timing is critical to the order

---

# 5. User Stories

### US-01 — Smart Recommendation

> As a user placing a non-urgent order, I want Zepto to recommend a suitable delivery slot so that I don't have to compare multiple options.

### US-02 — Savings

> As a price-conscious user, I want to see how much I can save by scheduling my order so that I can make an informed delivery decision.

### US-03 — Flexibility

> As a user, I want to change the recommended delivery slot so that I can select a time that fits my schedule.

### US-04 — Instant Delivery

> As a user who needs my order urgently, I want to continue with instant delivery without additional friction.

### US-05 — Repeat Purchases

> As a repeat customer, I want reminders for frequently purchased items so that I can plan future orders conveniently.

---

# 6. User Flow

```text
User opens Zepto
       ↓
Browses / searches products
       ↓
Adds products to cart
       ↓
Moves to checkout
       ↓
System checks order eligibility
       ↓
Eligible for SmartPlan?
       ↓
     YES
       ↓
SmartPlan recommendation displayed
       ↓
Recommended slot + savings shown
       ↓
User selects SmartPlan
       ↓
Scheduled order confirmed
```

### Alternative Flow

```text
SmartPlan unavailable
       ↓
Show available delivery options
       ↓
User selects instant delivery
```

---

# 7. Functional Requirements

## FR-01 — Eligibility Detection

The system should determine whether an order is suitable for scheduled delivery.

### Inputs

* Product type
* Order contents
* Delivery location
* Available capacity
* Available delivery slots
* User-selected urgency

---

## FR-02 — Slot Recommendation

The system should recommend an available scheduled-delivery slot.

### Recommendation factors

* User convenience
* Delivery availability
* Expected delivery reliability
* Potential savings
* Operational capacity

---

## FR-03 — Savings Display

The system should clearly communicate the expected savings associated with the recommended scheduled slot.

### Example

> **SmartPlan: Tomorrow · 7–9 AM**
> ₹0 delivery
> **Save ₹39**

---

## FR-04 — Slot Selection

Users should be able to:

* Accept the recommended slot
* Select another available slot
* Return to instant delivery

---

## FR-05 — Checkout Nudge

For eligible orders, SmartPlan should be displayed during delivery selection.

Example:

> **Save ₹39 by scheduling this order for tomorrow.**

---

## FR-06 — Confirmation

After selecting a scheduled slot, the system should display:

* Selected delivery window
* Expected delivery date
* Order details
* Cancellation/change option
* Delivery status

---

## FR-07 — Smart Reminder

For users with recurring purchasing behavior, the system may display a reminder.

Example:

> **You usually purchase these items every Monday. Schedule your next order?**

---

# 8. Non-Functional Requirements

### Reliability

Scheduled delivery recommendations should only be shown when the system has sufficient delivery capacity.

### Performance

The SmartPlan recommendation should load without creating noticeable checkout delay.

### Transparency

Users should clearly understand that the recommendation is optional.

### Flexibility

Users should always be able to select instant delivery when available.

### Trust

The recommended delivery window should represent a realistic expected delivery period.

---

# 9. Edge Cases

| Scenario                             | Expected Behavior                                |
| ------------------------------------ | ------------------------------------------------ |
| No scheduled slots                   | Show instant delivery and available alternatives |
| User needs order urgently            | Prioritize instant delivery                      |
| Recommended slot becomes unavailable | Refresh available slots                          |
| Product becomes unavailable          | Update order and recommendation                  |
| Delivery capacity changes            | Recalculate recommendation                       |
| User cancels scheduled order         | Record cancellation event                        |
| Fresh products have restrictions     | Restrict scheduling where required               |
| User changes delivery preference     | Update recommendation                            |

---

# 10. Analytics Requirements

The product should track key events across the delivery-selection funnel.

### Events

```text
delivery_option_viewed
scheduled_slot_viewed
smartplan_recommendation_shown
smartplan_selected
alternative_slot_selected
instant_delivery_selected
scheduled_order_confirmed
scheduled_order_cancelled
scheduled_order_delivered
```

---

# 11. Success Metrics

## North-Star Metric

### Scheduled Order Share

Percentage of eligible orders completed using scheduled delivery.

### Supporting Metrics

| Metric                    |                  Target |
| ------------------------- | ----------------------: |
| Scheduled-order share     |                6% → 15% |
| Delivery cost / order     |                    -15% |
| Scheduled delivery SLA    |                    ≥97% |
| Scheduled-slot conversion |                    +20% |
| Cancellation rate         | No significant increase |

### Guardrail Metrics

The product should not significantly increase:

* Order cancellation
* Delivery complaints
* Checkout abandonment
* Late deliveries
* Customer support contacts

> **Note:** All targets are proposed project targets and are not actual Zepto performance data.

---

# 12. MVP Scope

## P0 — Must Have

* Smart slot recommendation
* Savings visibility
* Checkout placement
* Slot selection
* Event tracking

## P1 — Should Have

* Smart reminders
* Personalized recommendations
* Dynamic incentives

## P2 — Future

* Advanced personalization
* Predictive demand-based scheduling
* Recurring order intelligence

---

# 13. Impact-Effort Prioritization

| Feature                   | Impact | Effort | Priority |
| ------------------------- | ------ | ------ | -------- |
| Smart slot recommendation | High   | Medium | P0       |
| Savings visibility        | High   | Low    | P0       |
| Checkout placement        | High   | Low    | P0       |
| Smart reminders           | Medium | Medium | P1       |
| Recurring orders          | High   | High   | P1       |
| Advanced personalization  | Medium | High   | P2       |

### Prioritization Principle

MVP features prioritize high customer value and measurable business impact while keeping implementation complexity manageable.

---

# 14. Experimentation Plan

### Experiment 1

**Hypothesis:** Smart slot recommendations increase scheduled-delivery selection.

**Primary Metric:** Scheduled-slot conversion

### Experiment 2

**Hypothesis:** Explicit savings messaging increases scheduled-order adoption.

**Primary Metric:** Scheduled-order share

### Experiment 3

**Hypothesis:** Prominent SmartPlan placement at checkout increases scheduled-delivery selection.

**Primary Metric:** Scheduled-delivery selection rate

Detailed experimentation is documented in `EXPERIMENTATION.md`.

---

# 15. Product Roadmap

## Phase 1 — MVP

**Weeks 1–2**

* Smart slot recommendation
* Savings messaging
* Checkout integration
* Basic analytics

## Phase 2 — Optimization

**Weeks 3–5**

* Personalized recommendations
* Smart reminders
* Incentive experimentation
* A/B testing

## Phase 3 — Scale

**Weeks 6–8**

* Capacity-aware recommendations
* Predictive demand signals
* Advanced personalization
* Recurring purchase recommendations

---

# 16. Risks & Mitigation

| Risk                                              | Mitigation                          |
| ------------------------------------------------- | ----------------------------------- |
| Users perceive scheduled delivery as inconvenient | Recommend convenient slots          |
| Low adoption                                      | Test messaging and placement        |
| Late deliveries reduce trust                      | Use reliability thresholds          |
| Excessive incentives hurt margins                 | A/B test incentive levels           |
| Users select scheduled delivery for urgent orders | Use eligibility and urgency signals |

---

# 17. Product Success Definition

SmartPlan will be considered successful if it:

1. Increases scheduled-order adoption among eligible orders
2. Reduces delivery cost per order
3. Maintains high delivery reliability
4. Does not materially increase cancellations
5. Improves the user experience of delivery-slot selection

---

## Product Manager Takeaway

The product strategy focuses on **behavior change through convenience and transparency**, rather than forcing users away from instant delivery.

The MVP therefore combines:

**Smart recommendation + clear savings + low-friction checkout + measurable experimentation.**
