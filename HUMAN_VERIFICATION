# Human Verification

Senterrah’s goal is simple: **no synthetic text in production datasets.**  
All records are written by real people and pass through multiple independent checks.

We don’t claim “perfect detection” (no one can), but we combine enough layers that
**AI-generated text is systematically rejected, not curated.**

---

## 1. Writer Onboarding

Every writer must:

1. Apply with real identity information (name, location, payment details).
2. Sign a **Writer Agreement** and **NDA** that explicitly forbid using AI tools.
3. Complete a timed writing test inside our environment.

The writing test is:

- Prompted dynamically (not reusable)
- Time-bounded
- Compared against future submissions for style / fingerprint

Writers who fail the test or show AI-like patterns are not onboarded.

---

## 2. Device & Environment Controls

Where technically feasible, we apply:

- Browser-based checks (user agent, copy–paste activity, focus changes)
- Rate limits per writer
- IP / device monitoring for abnormal patterns

These signals are **not** used to identify people, only to flag suspicious behavior.

---

## 3. AI-Detection Ensemble

Every submission runs through an **ensemble of detectors**, which may include:

- Open-source AI detectors
- Stylometry / perplexity checks
- N-gram and repetition analysis
- Burstiness and variance measurements

If a piece scores as *possibly synthetic*, it is:

- **Rejected** immediately for production, or
- **Flagged** for manual review and writer follow-up

We never “clean up” suspected AI text and keep it; we discard it.

---

## 4. Style & Cognitive Pattern Checks

Human reasoning has consistent irregularities:

- Inconsistent structure between paragraphs
- Small contradictions or self-corrections
- Emotional leakage and internal conflict
- Mixed levels of abstraction (“what happened” vs “what it meant”)

We design prompts and filters to **encourage** this, and we:

- Reject ultra-polished, generic, or “corporate-sounding” text
- Prefer narratives with:
  - Internal signal phrases (e.g. “part of me felt…”, “I started wondering if…”)
  - Emotional keywords
  - Explicit decision dilemmas

---

## 5. Ongoing Audits

- Random manual audits of accepted records
- Writer-level performance tracking
- Immediate offboarding if AI usage is suspected or confirmed

---

## 6. Guarantee to Buyers

While no one can mathematically prove “100% human” on every token, Senterrah:

- Uses **only human writers**, under contract, with NDAs
- Applies **multi-layer detection** and review
- Excludes any record that fails **any** trust check

The result is a dataset designed to be as close as practically possible to
**authentic, human-only reasoning data.**
