# Quality & Review Pipeline

This document describes how raw writing becomes production-ready Senterrah data.

We focus on three goals:

1. **Human-only**: no synthetic text
2. **High-fidelity reasoning**: rich, non-trivial cognitive structure
3. **Consistent metadata**: machine-usable fields for training and evaluation

---

## Step 1 – Collection

Writers receive prompts designed to elicit:

- A specific situation or conflict
- A genuine decision dilemma or emotional tension
- Internal reasoning (“part of me wanted X, another part wanted Y”)

All writing is:

- Submitted in our environment
- Associated with a writer ID
- Time-stamped and length-checked

---

## Step 2 – Automatic Pre-Filter

Scripts automatically reject or flag records that:

- Are too short (e.g. `< 120` words)
- Contain no emotional or internal-reasoning signals (regex filters)
- Look like summaries / advice instead of **first-person experience**
- Fail AI-detection / stylometry checks

Only records that pass these filters move to metadata generation.

---

## Step 3 – Metadata & Structuring

For each accepted record we generate structured fields, including:

- Word / paragraph counts
- Emotion labels and rough intensity
- Conflict type
- Decision options and criteria
- Reasoning structure and steps

This is done with a combination of:

- Internal tools
- LLM-assisted annotation
- Human QA for spot checks

(See [METADATA_SCHEMA.md](./METADATA_SCHEMA.md) for field-level details.)

---

## Step 4 – Human Review

A separate reviewer (not the original writer) checks that:

- The narrative is coherent and self-consistent
- There is a clear conflict or decision point
- Emotions and internal states are evident
- Metadata matches the story (no hallucinated options / emotions)
- No personal identifiers or unsafe content remain

Records are marked:

- `Approved`
- `Needs revision` (sent back to writer)
- `Rejected` (permanently removed from training pool)

---

## Step 5 – Redaction & Compliance

Before any record can leave Senterrah:

- Personal names, addresses, and other PII are removed or generalized
- Overly specific workplace / school details are blurred
- Sensitive attributes are handled according to policy

We aim to preserve **cognitive structure**, not raw biography.

---

## Step 6 – Packaging

Approved data is:

- Stored in partitioned JSONL files (by type, difficulty, emotion, etc.)
- Versioned with dataset IDs and checksums
- Delivered to clients with:
  - Schema documentation
  - Sampling notes
  - Any relevant filtering parameters

The sample records in `senterrah-samples` are created using the exact same pipeline,
then heavily redacted for safety.
