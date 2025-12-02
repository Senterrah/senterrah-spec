# Metadata Schema

This document describes common fields used across Senterrah decision / reasoning datasets.

---

## Core Fields

| Field              | Type      | Description |
|--------------------|-----------|-------------|
| `id`               | string    | Unique record ID. Stable across releases. |
| `category`         | string    | High-level type (e.g. `high_intent_decision`, `relationship_conflict`). |
| `title`            | string    | Short human-readable summary of the situation. |
| `body`             | string    | Full human-written narrative text. |
| `word_count`       | integer   | Tokenized by whitespace. |
| `paragraph_count`  | integer   | Number of paragraphs in `body`. |
| `language`         | string    | ISO 639-1 code (e.g. `"en"`). |

---

## Emotional & Cognitive Fields

| Field               | Type        | Description |
|---------------------|------------|-------------|
| `emotions`          | string[]   | List of primary emotions expressed (e.g. `["anger", "hurt"]`). |
| `emotion_intensity` | float      | Rough intensity score 0.0–1.0. |
| `conflict_type`     | string     | Type of conflict (e.g. `interpersonal`, `internal`, `family`). |
| `emotional_weight`  | string     | Qualitative label: `Low`, `Medium`, `High`. |
| `logical_weight`    | string     | Strength of explicit reasoning: `Low`, `Medium`, `High`. |

---

## Decision & Reasoning Fields

| Field               | Type        | Description |
|---------------------|------------|-------------|
| `decision_type`     | string     | E.g. `Reactive`, `Deliberative`, `Punitive`, etc. |
| `final_decision_present` | boolean | Whether the record contains an explicit outcome. |
| `options_count`     | integer    | Number of explicit options considered. |
| `options`           | string[]   | Natural-language descriptions of each option. |
| `criteria`          | string[]   | Factors used to evaluate options (e.g. respect, safety, fairness). |
| `reasoning_structure` | string   | Short description of the reasoning pattern. |
| `reasoning_steps`   | string[]   | Ordered steps capturing how the person arrived at the outcome. |
| `certainty`         | string     | `Low`, `Medium`, or `High` confidence in the chosen action. |

---

## Context Fields

| Field        | Type        | Description |
|-------------|------------|-------------|
| `context`   | string      | One-paragraph summary of the situation, written for models. |
| `source`    | string      | High-level origin (e.g. `commissioned_writer`). |
| `created_at`| string      | ISO 8601 timestamp for record creation (optional in samples). |

The sample files in [`senterrah-samples`](https://github.com/Senterrah/senterrah-samples)
demonstrate these fields in practice.
