# Protocol - probabilistic thinking

End-to-end PROTOCOL — not advice, not philosophy — but a repeatable operating procedure for probabilistic decision-making, from creation → update → review → learning → archive.

```code

Detect → Frame → Estimate → Decide → Observe → Update → Review → Learn → Archive

```

## PHASE 1 - Detect phase (When to Start the Process)

Trigger Conditions (Any ONE is enough)

- Start the protocol if:

- Stakes are non-trivial

- Outcome is uncertain

- Decision is irreversible or costly

- You feel confused or conflicted

- Decision repeats over time

- If none apply → don’t overthink.

## PHASE 2 — FRAMING (Decision Definition)

Action Checklist

- Write the decision in one sentence

- Define what you control

- Define time horizon

Output Artifact

- 📄 01-active-decisions/<decision>.md

- Mandatory Format
- Decision:
  Time Horizon:
  Why this matters:

⚠️ Rule

If you can’t write it clearly, you don’t understand it.

## PHASE 3 — OPTION ENUMERATION (Choice Space)

Actions

List all reasonable options

Include “do nothing”

Include “delay”

Rule

Fewer options = clearer thinking
2–4 options is ideal

## PHASE 4 — PROBABILITY ASSIGNMENT (Belief Encoding)

Actions

Assign coarse probabilities (10 / 30 / 50 / 70 / 90)

Ensure probabilities sum to 100% per option

Write reasoning in one line

Rules

No decimals initially

No emotion-based probabilities

Guess > no prior

Output
Option A:
Probability:
Reason:

## PHASE 5 — PAYOFF MODELING (Impact Encoding)

Actions

Define payoff scale before assigning values

Use relative values (+10, –50 etc.)

Consider worst case explicitly

Rule

High downside dominates EV more than upside boosts it.

## PHASE 6 — EXPECTED VALUE COMPUTATION (Decision Gate)

Action

Compute EV for each option:

EV = Σ (Probability × Payoff)

Decision Rule

Highest EV wins

If EV ≈ equal → reduce downside

If EV < 0 → stop or redesign

Output

Decision chosen + next review date

## PHASE 7 — EXECUTION WITH CHECKPOINTS

Actions

Execute chosen option

Define review checkpoints

Define abort conditions

Mandatory
Review Date:
Abort Condition:

⚠️ Rule

Abort is a valid success outcome.

## PHASE 8 — EVIDENCE INTAKE (Observation)

What Counts as Evidence

Metrics

Repeated signals

External validation

Failures & anomalies

What Does NOT Count

Feelings

One-off opinions

Hope

Fear

## PHASE 9 — UPDATE PROTOCOL (Core Skill)

Update Decision

Ask:

Did likelihood change? → update probability

Did impact change? → update payoff

Did new option appear? → add branch

Update Strength Rules
Evidence Update Size
Weak Small
Repeated Medium
Measured Large
Output Artifact

📄 03-update-log/<date>-<decision>.md

## PHASE 10 — CONTINUE / STOP GATE

Decision Rules

EV ↑ → continue

EV ↓ but positive → monitor

EV < 0 → stop or pivot

⚠️ Rule

Never “wait and see” without updating EV.

## PHASE 11 — OUTCOME RESOLUTION

Triggered when:

Decision ends

Outcome is known

You exit voluntarily

Actions

Freeze final probabilities

Record outcome

Move file to archive

📁 07-archive/

## PHASE 12 — POSTMORTEM (Learning Extraction)

Mandatory Questions

What did I predict?

What happened?

Where was I wrong?

Which signal did I miss?

What rule do I add?

📄 05-postmortems/<decision>.md

⚠️ Rule

Outcome ≠ decision quality

## PHASE 13 — CALIBRATION (Judgment Training)

Actions

Compare predicted vs actual

Identify bias type

Adjust future priors

📄 04-calibration/

This is how judgment compounds.

## PHASE 14 — PERIODIC REVIEW (Meta-Learning)

Frequency

Weekly: active decisions

Monthly: calibration

Quarterly: system cleanup

Questions

Where am I consistently overconfident?

Where am I too conservative?

Which domains have best EV?

🧠 FAILURE SAFETY RULES (MEMORIZE)

Never overwrite old beliefs

Never judge by outcome

Never ignore downside

Never update from emotion

Never stop recording

## checklists

### ☀️ Daily (2 minutes)

```code
□ Any active decision today?
□ New evidence arrived?
□ Probability ↑ ↓ ↔ ?
□ Record one sentence update

```

### 📅 Weekly (15 minutes)

```code
□ Review all active decisions
□ Recalculate EV where needed
□ Check abort conditions
□ Move resolved decisions to archive

```

### Monthly (30 minutes – optional but powerful)

```code
□ Review calibration log
□ Where was I overconfident?
□ Where was I too conservative?
□ Adjust future priors

```
