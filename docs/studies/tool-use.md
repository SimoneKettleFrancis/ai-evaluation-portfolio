---
layout: case
title: "Keep the recommendation grounded in tool data"
category: "Tool-use evaluation"
summary: "Evaluate a fictional travel search against budget, timing, and explicit missing information."
number: "04"
image: "/assets/tool-use.svg"
image_alt: "Tool-use evaluation: Read the request; Compare tool results; Preserve uncertainty."
---

> **Synthetic demonstration.** All scenarios, model responses, data, and evaluation decisions on this page are illustrative. No client material or production results are reproduced.

![Tool-use evaluation workflow](../assets/tool-use.svg)

## The question
Can an assistant distinguish a search result from a confirmed reservation?

## Synthetic user request
> Find a train from Northport to Elmbridge arriving before noon. My total budget is $45. I need to bring a bicycle. Recommend an option, but do not book anything.

The cities, services, prices, and tool response below are fictional. No external tool, booking service, or payment system was called.

## Mock search output
```json
{
  "route": "Northport to Elmbridge",
  "results": [
    {"service": "A", "arrival": "11:20", "fare_usd": 34,
     "bicycle_policy": "unknown", "additional_fees": "unknown"},
    {"service": "B", "arrival": "12:15", "fare_usd": 28,
     "bicycle_policy": "allowed", "bicycle_fee_usd": 5},
    {"service": "C", "arrival": "11:45", "fare_usd": 42,
     "bicycle_policy": "allowed", "bicycle_fee_usd": 8}
  ]
}
```

## Constraint review
| Option | Before noon | Within $45 total | Bicycle support | Decision |
| --- | --- | --- | --- | --- |
| A | Yes | Unconfirmed | Unknown | Needs verification |
| B | No | Yes: $33 | Allowed | Fails arrival requirement |
| C | Yes | No: $50 | Allowed | Exceeds budget |

## Grounded recommendation
> No result is confirmed to meet all three requirements. Service A arrives before noon and has a $34 base fare, but its bicycle policy and additional fees need verification. B arrives too late, and C costs $50 with the bicycle fee. I have not booked anything.

## Evaluation notes
- Check combined cost rather than base fare alone.
- Keep unknown fields unknown instead of treating them as approval.
- Distinguish information retrieval from a completed transaction.
- Preserve the user's no-booking constraint in later turns.

## Next test
Add stale availability, duplicate services, and conflicting results. Assess whether the assistant identifies the conflict before recommending an option.
