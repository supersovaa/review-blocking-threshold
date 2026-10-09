# review-blocking-threshold

A lightweight review skill for deciding whether a finding should block acceptance or completion of code, plans, documents, or other deliverables.

## When to use

Apply `review-blocking-threshold` when reviewing code, plans, documents, or other deliverables.

## Core principle

A finding is blocking when it exposes a concrete problem that materially changes, or can plausibly change, correctness, behavior, responsibility boundaries, authoritative interpretation, completion judgments, or dependent work.

A clearer phrase with the same effective meaning is a non-blocking refinement. Ambiguous wording is blocking when its competing meanings lead to materially different decisions or results.

## Responsibility

This skill determines the blocking threshold; the surrounding review workflow determines the review criteria and optional reporting.
Use `complete-review-before-reporting` for review coverage and reporting sequence, and `pr-scope-review` to decide which PR or follow-up owns a required fix.

The operational rules are in [SKILL.md](SKILL.md).

## Installation

Place this repository's `SKILL.md` at `review-blocking-threshold/SKILL.md` under a skills directory recognized by your AI agent's skill system. Enable or reference the skill according to that system's configuration.
