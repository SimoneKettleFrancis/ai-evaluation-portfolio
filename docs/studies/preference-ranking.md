---
layout: case
title: "Response Comparison & Preference Ranking"
category: "Comparative response review"
summary: "Read conversation history, assessed competing responses against the same task, and selected a preference with an evidence-based justification."
number: "06"
image: "/assets/preference-ranking.svg"
image_alt: "Preference ranking: Recover the context; Compare both answers; Justify the preference."
---

## My role

I compared model responses to the same request, using the conversation history and evaluation instructions to decide which response better served the user. The work included checking task eligibility, assessing each response, selecting a preference, and explaining it.

### What the task involved

- Recover relevant requirements from earlier turns, not only the latest message.
- Check that the task was eligible for evaluation under the assignment’s instructions.
- Review each response’s strengths and defects before making the comparison.
- Choose a preference and explain which differences mattered to the user’s request.

A preferred response is not necessarily flawless. Independent quality judgments and the relative preference need to stay distinct.

## Independent example of the task

> **Real work context; synthetic demonstration.** The role description summarizes my evaluation work. The brief, responses, visuals, and judgments below were independently created to illustrate this type of task. They are not original assignments, client materials, proprietary criteria, or measured production results.

![Preference ranking workflow](../assets/preference-ranking.svg)

## The question

Does a response honor the user's earlier constraints as well as the latest message?

## Synthetic conversation

> **User, earlier:** I need a three-step onboarding checklist for volunteers at a fictional community garden. Use plain English. Do not collect personal contact details.
>
> **User, now:** Add a way for them to ask for help, but keep it to three steps.

### Response A

> 1. Read the garden's welcome guide and safety instructions.
> 2. Check the task board and choose an available activity.
> 3. Ask the session coordinator for help if anything is unclear.

### Response B

> 1. Read the welcome guide.
> 2. Choose an activity.
> 3. Add your phone number and home address to the volunteer directory.
> 4. Ask another volunteer for help.

## Review before choosing a preference

This fictional conversation supplies enough context to compare the responses. A satisfies the stated requirements. B is readable and includes a help route, but violates two explicit constraints. I would record those independent observations before selecting a preference; a comparative decision should not replace the review of each answer.

## Comparison

| Criterion | A | B |
| --- | --- | --- |
| Keeps exactly three steps | Meets | Does not meet |
| Adds a way to ask for help | Meets | Meets |
| Avoids collecting personal contact details | Meets | Does not meet |
| Uses plain English | Meets | Meets |

## Preference and justification

Prefer A. It adds an explicit help route while preserving the three-step limit and the earlier restriction on personal contact details. B adds a fourth step and requests information the user specifically excluded. A is preferable because it satisfies the conversation's constraints, not simply because it is shorter.

## Review discipline

Record the relevant evidence before selecting a preference. When both responses have material faults, describe those faults rather than presenting the less problematic response as fully correct.

## Next test

Reverse the display order, vary response length, and introduce a late instruction that conflicts with an earlier one. Check whether the explanation remains grounded in the user's actual requirements.

This is a hand-authored comparison, not a production evaluation or a measured model ranking.
