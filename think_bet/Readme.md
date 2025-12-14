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

# 🧠 Probabilistic Thinking Protocol

> A practical system for making, updating, and learning from decisions under uncertainty.  
> Decisions are treated as **bets**, judged by **Expected Value**, not outcomes.

This repository implements a **repeatable protocol** for:

- High-stakes decisions
- Engineering & system design tradeoffs
- Career and learning investments
- Incident response & debugging
- Long-term judgment calibration

---

## Core Principle

> **Good decisions can fail.  
> Bad decisions can succeed.  
> Quality is measured by process, not outcome.**

---

## 🔁 Mental Models (Acronyms You Actually Use)

### **BETS** — Daily Loop

**B**eliefs → **E**vidence → **T**hinking update → **S**take decision

Used for:

- Day-to-day decisions
- Ongoing projects
- Incidents and debugging

---

### **DECIDER** — Full Lifecycle

**D**etect → **E**xpress → **C**hoices → **I**mpact → **D**ecide → **E**vidence → **R**evise

Used for:

- High-stakes decisions
- Career moves
- System design choices

---

### **RUIN** — Safety-Critical Decisions

**R**isk → **U**pdate → **I**rreversibility → **N**o-go

Used for:

- Production deploys
- Infra changes
- High downside / irreversible actions

---

### **UPDATE** — While Executing

**U**npack evidence → **P**robability shift → **D**ownside check  
**A**lternatives → **T**hreshold → **E**xecute

---

### **JUDGE** — Learning & Calibration

**J**ot belief → **U**nderstand why → **D**ecide  
**G**auge outcome → **E**volve priors

---

---

## 🧩 How to Use This Repo

### 1️⃣ Start a Decision

- Copy `00-templates/decision.md`
- Paste into `01-active-decisions/`
- Fill it using **DECIDER**

---

### 2️⃣ Execute & Update

- As evidence arrives, append updates using:
  - `00-templates/update.md`
  - Store in `03-update-log/`
- Use **BETS** and **UPDATE**

---

### 3️⃣ Abort if Needed

- Use `abort-checklist.md`
- Apply **RUIN** and **STOP**
- Abort early = success

---

### 4️⃣ Close & Learn

- Move final decision to `07-archive/`
- Write:
  - `postmortem.md`
  - `calibration.md`
- Use **JUDGE**

---

## 📊 Probability Rules

- Use coarse buckets: **10 / 30 / 50 / 70 / 90**
- Guess > no prior
- Never overwrite old probabilities
- Update directionally first (↑ ↓ ↔)
- Downside updates > upside updates

---

## ⏱ Review Cadence

| Activity         | Frequency     |
| ---------------- | ------------- |
| BETS check       | Daily (2 min) |
| Active decisions | Weekly        |
| Calibration      | Monthly       |
| System cleanup   | Quarterly     |

---

## ❌ What This Is NOT

- Not a task tracker
- Not a productivity system
- Not outcome-based hindsight analysis
- Not emotion-driven journaling

This is a **judgment improvement system**.

---

## 🧠 Why This Works

- Externalizes beliefs
- Forces explicit probabilities
- Separates decision quality from luck
- Turns experience into calibrated judgment
- Scales across domains (engineering, career, life)

---

## 📌 Golden Rules

1. Never judge decisions by outcomes alone
2. Never ignore downside risk
3. Never update beliefs without evidence
4. Abort is success if EV turns negative
5. Written beliefs compound — unwritten ones don’t

---

## 🚀 Getting Started (10 Minutes)

1. Clone the repo
2. Read `06-reference/probabilistic-protocol-onepage.md`
3. Copy one template
4. Track one real decision today

That’s enough.

---

## 📚 Influences

- Annie Duke — _Thinking in Bets_
- Nassim Taleb — _Fooled by Randomness_
- SRE postmortem practices
- Bayesian reasoning & EV thinking

---

> **Life is poker, not chess.  
> This repo helps you bet better.**
