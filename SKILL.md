---
name: review-blocking-threshold
description: Review code, plans, documents, and other deliverables using a material-impact threshold to distinguish blocking findings from optional refinements.
---

# Review Blocking Threshold

Use this skill when reviewing code, plans, documents, or other deliverables.

This skill targets a single-user AI-agent review workflow.

## Establish the review contract

Read the current deliverable's purpose, scope, and relevant authoritative requirements, design, and decisions before classifying a finding.
When work is governed by an implementation plan, include the plan's purpose, scope, exclusions, completion criteria, and direct dependencies.
Judge each finding against what the current deliverable is responsible for establishing.

## Apply the material-impact threshold

Classify a finding as blocking when the identified problem materially changes, or has a concrete and plausible path to changing, any of the following:

- correctness of the deliverable or its intended outcome;
- runtime behavior or decisions made by users or agents;
- responsibility boundaries or established contracts;
- interpretation of authoritative requirements, rules, or design;
- the decision that the current work is complete; or
- downstream work that relies on the deliverable's meaning or guarantees.

Judge differences in representation or interpretation by whether they materially change effective meaning, required behavior, decisions, or established guarantees.

Before requiring a distinction between cases, identify the governing meaning or use case that requires it and the boundary responsible for preserving it.
Check whether the cases are interchangeable under that contract, whether exposing their differences would violate an established equivalence or information boundary, and whether any required distinction is already available where it is needed.
Differences in internal identifiers, incidental ordering, representations, or hypothetical future uses do not by themselves justify a new distinction.
Require a distinction in the current deliverable when its contract makes the difference material to behavior, decisions, interpretation, or established guarantees.

## Ground blocking findings

For each blocking finding, identify the affected current responsibility or settled contract, the concrete consequence, and the evidence connecting the problem to that consequence.
Relate the consequence to the reviewed change and, where applicable, its governing plan.
For a claimed failure path, identify a feasible sequence with contract-valid inputs or inputs covered by the required defense scope; separate reachable consequences from unsupported hypotheticals.
Classify improvements that do not meet the material-impact threshold as non-blocking suggestions or omit them from the review result.

## Responsibility boundary

This skill decides whether a review finding must block acceptance or completion.
The surrounding review workflow owns the review criteria and whether optional suggestions are reported.
`complete-review-before-reporting` owns review coverage and reporting sequence.
`pr-scope-review` owns whether a required change belongs in the current PR, a separate PR, or follow-up work.
