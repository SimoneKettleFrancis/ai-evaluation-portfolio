---
layout: case
title: "Image-Based Task Review & Response Correction"
category: "Multimodal evaluation"
summary: "Reviewed image-based tasks for validity and capability, checked visual evidence, and corrected responses while explaining the changes."
number: "05"
image: "/assets/image-understanding.svg"
image_alt: "Image understanding: Extract the values; Check the calculation; Limit the conclusion."
---

## My role

My image-based evaluation work involved more than reading a chart. Tasks included reviewing whether an image-and-prompt pair could be evaluated, classifying the kind of image or capability involved, checking the response, and rewriting it when needed.

### What the task involved

- Check that the image and prompt provided a valid, answerable task.
- Identify the relevant capability, such as reading text, interpreting a chart or document, or reasoning about a diagram.
- Make limited prompt repairs where appropriate while preserving the intended task.
- Correct the response, identify the quality problems fixed, and explain the revision.
- Assess task difficulty using the instructions provided for the assignment.

The example below illustrates one slice of that workflow: visual extraction, reasoning, and a justified response correction.

## Independent example of the task

> **Real work context; synthetic demonstration.** The role description summarizes my evaluation work. The brief, responses, visuals, and judgments below were independently created to illustrate this type of task. They are not original assignments, client materials, proprietary criteria, or measured production results.

![Image understanding workflow](../assets/image-understanding.svg)

## The question

Can an assistant read a chart accurately without claiming more than the image shows?

## Original synthetic visual

![Fictional workshop registrations: Drawing 18, Photography 12, Ceramics 9.](../assets/workshop-chart.svg)

The chart and its values were created specifically for this demonstration. They do not describe an actual organization, audience, or outcome.

## Task intake and classification

For this synthetic task, the chart is legible and supports identifying and comparing values. I would classify it as chart interpretation with numerical comparison. The question about why registrations differ is answerable only as a statement about missing evidence; it does not justify inventing a cause. No prompt repair is needed because that limitation can be explained directly. The task combines straightforward extraction and subtraction with a check on unsupported inference; no client difficulty label is reproduced.

## Prompt

> Which workshop has the most registrations, and how many more does it have than the least popular workshop? Can we tell why it is more popular?

### Illustrative answer with an error

> Drawing has 18 registrations, which is 9 more than Ceramics. Drawing is more popular because it is cheaper and easier for beginners.

## Evaluation

| Claim | Assessment | Reason |
| --- | --- | --- |
| Drawing has the most registrations | Supported | The chart shows 18, the highest value. |
| The difference is 9 | Supported | 18 minus 9 equals 9. |
| Lower price explains the difference | Unsupported | No prices appear in the chart. |
| Beginner accessibility explains it | Unsupported | The chart contains no experience-level data. |

## Revised answer

> Drawing has the most registrations, with 18—9 more than Ceramics, which has 9. The chart does not explain the difference; we would need additional information to identify a reason.

## Correction rationale

Keep the correct values and subtraction. Remove the invented claims about price and beginner accessibility, and state the evidence limit. The correction changes the unsupported interpretation while preserving the user’s intended comparison.

## What this demonstrates

Visual extraction, arithmetic, and interpretation are separate checks. A response can read every number correctly while still inventing a causal explanation.

## Next test

Use a low-resolution chart, remove a label, or change the scale. A reliable answer should express uncertainty when the image is not legible rather than guessing a value.
