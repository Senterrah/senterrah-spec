<p align="center">
  <img src="senterrahbanner.png" alt="Senterrah Banner" width="100%">
</p>



# Senterrah Data Specification

Senterrah provides premium, human-written datasets for training advanced AI systems.

This repository documents:

- Public schema definitions
- Human-verification and quality controls
- Metadata fields and reasoning structure
- Links to small redacted samples and loaders

If you want to see example records and loader code, see the companion repo:
➡️ https://github.com/Senterrah/senterrah-samples

---

## What Senterrah Data Is

Senterrah focuses on **high-fidelity human reasoning data**, including:

- Decision-making under uncertainty
- Non-linear / “messy” human thought patterns
- Emotional and interpersonal reasoning
- Explanations at multiple cognitive levels
- Human error → reflection → correction sequences

All production datasets are:

- Written exclusively by **verified human writers**
- Screened to **exclude synthetic / AI-generated text**
- Passed through a **multi-layer quality review pipeline**

Details:
- [Human Verification](./HUMAN_VERIFICATION.md)
- [Quality & Review Pipeline](./QUALITY_PIPELINE.md)
- [Metadata & Schema](./METADATA_SCHEMA.md)

---

## High-Level Schema

A typical **decision record** contains:

- `id` – unique record ID
- `title` – short natural-language summary
- `body` – original human-written narrative
- `category` – decision / interaction type
- `word_count`, `paragraph_count`
- `language`
- `emotions`, `emotion_intensity`
- `conflict_type`
- `options`, `criteria`
- `reasoning_structure`, `reasoning_steps`
- `emotional_weight`, `logical_weight`
- `certainty`

For full field definitions and types, see:
- [Metadata & Schema](./METADATA_SCHEMA.md)
