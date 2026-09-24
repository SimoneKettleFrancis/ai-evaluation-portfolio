---
layout: case
title: "Tool-Use & Workflow Evaluation"
category: "Tool-output and response review"
summary: "Reviewed tool results alongside the conversation and final answer, checking grounding, instruction fulfillment, and unsupported claims."
number: "04"
image: "/assets/tool-use.svg"
image_alt: "Tool-use evaluation: Read the request; Compare tool results; Preserve uncertainty."
---

## My role

I reviewed AI responses that used external tool information, comparing the tool log and returned information with the user’s request and the final answer. The judgment required checking both what the tool supplied and how accurately the response represented it.

### What the task involved

- Read the conversation to recover the user’s requirements and constraints.
- Inspect relevant tool results and links as evidence, separately from the assistant’s wording.
- Check whether the final response fulfilled the request and whether its claims were supported by the returned information.
- Flag missing information, contradictions, or claims that a search or recommendation had completed an action it had not completed.

A useful tool result does not automatically make the final response correct. The response still needs its own review.

## Independent example of the task

> **Real work context; synthetic demonstration.** The role description summarizes my evaluation work. The brief, responses, visuals, and judgments below were independently created to illustrate this type of task. They are not original assignments, client materials, proprietary criteria, or measured production results.

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

## Final answer under review

> Service A meets all your requirements for $34, including your bicycle. Your trip is confirmed.

This authored answer misrepresents the search output. Its time and base fare are supported, but bicycle acceptance and the total cost remain unknown. A search result is also not a booking confirmation. The response fails both evidence grounding and the user’s no-booking constraint by claiming a completed reservation.

## Corrected response

> No result is confirmed to meet all three requirements. Service A arrives before noon and has a $34 base fare, but its bicycle policy and additional fees need verification. B arrives too late, and C costs $50 with the bicycle fee. I have not booked anything.

## Evaluation notes

- Check combined cost rather than base fare alone.
- Keep unknown fields unknown instead of treating them as approval.
- Distinguish information retrieval from a completed transaction.
- Preserve the user's no-booking constraint in later turns.

## Next test

Add stale availability, duplicate services, and conflicting results. Assess whether the assistant identifies the conflict before recommending an option.
