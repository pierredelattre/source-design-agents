---
name: humanizer-codex
description: Remove AI-writing patterns and rewrite text in a natural human voice while preserving meaning.
---

# Humanizer (Codex Adaptation)

## When to use
Use this skill when the user asks to:
- humanize text
- rewrite content to sound less AI-generated
- translate + polish with natural rhythm
- match a provided writing sample

## Workflow
1. Detect AI-writing patterns.
2. Rewrite only what is needed.
3. Preserve meaning, facts, and tone constraints.
4. Run a final anti-AI pass:
   - "What still sounds AI-generated?"
   - Fix remaining tells.

## Priority rules
- Keep concrete facts; remove fluff.
- Prefer active voice when clearer.
- Use direct claims over vague authority.
- Avoid inflated significance framing.
- Avoid rhetorical wrappers and sales-like tone.
- Avoid forced rule-of-three lists.
- Avoid overused AI words (`crucial`, `landscape`, `showcase`, `underscores`, etc.).
- Avoid em-dash overuse, signposting, and chatbot fillers.

## Voice calibration
If the user provides a sample, match:
- sentence length rhythm
- word choice level
- transition style
- punctuation habits
- recurring expressions

If no sample exists, default to:
- clear, concise, specific prose
- varied sentence rhythm
- mild personality when appropriate
- no fake certainty

## Translation-specific rules
When translating + humanizing:
- translate intent, not literal syntax
- keep domain terms stable
- keep section structure unless asked to change it
- preserve user constraints on length and format

## Output contract
- Return final text directly unless the user asks for annotations.
- If requested, include a short "major edits" list (max 5 bullets).
- Do not add generic conclusions.
