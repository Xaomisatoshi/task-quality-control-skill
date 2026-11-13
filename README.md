# Task Quality Control

A German-language quality-control skill for closing completed tasks with a compact KPI/status matrix, self-assessment, risk check, and transparent handling of missing or non-measurable values.

## What changed in this improved version

- Added valid `SKILL.md` YAML frontmatter.
- Renamed the skill to clean hyphen-case: `task-quality-control`.
- Moved trigger logic into the frontmatter description so the skill can be discovered reliably.
- Added required ChatGPT UI metadata in `agents/openai.yaml`.
- Removed duplicate wording and reduced the core instructions.
- Kept the original principle: no invented KPI values, no simulated measurements, no false certainty.

## Main output

The skill appends:

1. A compact quality matrix.
2. A short self-assessment.
3. A risk/gap note.
4. An honest one-sentence verdict.

## Safety principle

If a KPI cannot be measured from available evidence, the skill must say so instead of inventing a number.
