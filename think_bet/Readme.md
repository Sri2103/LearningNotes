# Probabilistic Decision System

This repository implements a structured protocol for making
and improving decisions under uncertainty.

## Core Principle

Decisions are bets.
Quality is judged by Expected Value, not outcomes.

## Lifecycle

Detect → Frame → Options → Probabilities → Payoffs
→ EV → Execute → Observe → Update → Decide
→ Postmortem → Calibrate → Archive

## Folder Structure

- 00-templates/ → reusable templates
- 01-active-decisions/ → ongoing decisions
- 02-decision-trees/ → complex/high-stakes decisions
- 03-update-log/ → evidence-based updates
- 04-calibration/ → accuracy tracking
- 05-postmortems/ → deep learning
- 06-reference/ → heuristics & rules
- 07-archive/ → closed decisions

## Rules

- Probabilities must be written
- Updates are append-only
- Outcomes do not judge decisions
- Abort is success if EV turns negative

## Review Cadence

- Daily: quick updates
- Weekly: EV review
- Monthly: calibration
