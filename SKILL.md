---
name: task-quality-control
description: quality-control workflow for closing completed tasks with a compact kpi/status matrix, self-assessment, risk and gap check, and explicit handling of non-measurable values. use when the user asks for a quality check, self-review, completion review, kpi matrix, risk check, result assessment, or when an assistant needs to close a finished task without inventing metrics.
---

# Task Quality Control

## Purpose

Use this skill to close a completed task with a short, honest quality review. The goal is not to claim perfection, but to make the result usable, transparent, and safe to hand off.

## Core rule

Do not invent KPIs, percentages, validation results, timings, efficiency values, or external impact. If a value was not measured or externally validated, say so directly.

## Closing workflow

1. Check goal fit.
   - Identify what the user wanted.
   - Mark whether the request is fulfilled, partially fulfilled, or still open.
   - Mention any important deviation from the original request.

2. Check usability.
   - Decide whether the result is directly usable, usable as a draft, or not yet usable.
   - Prefer one short reason over a long explanation.

3. Check uncertainty and risk.
   - Mark missing data, unverified assumptions, external validation gaps, technical limits, legal/medical/financial limits, source limits, or incomplete implementation.
   - Separate facts, assumptions, and interpretation when that distinction matters.

4. Add the quality matrix.
   - Use the exact matrix structure below unless the user asks for a different format.
   - Use “Nicht extern validiert”, “Nicht messbar ohne Timer”, or “Nicht belastbar berechenbar” when no reliable measurement exists.

5. Add the short self-assessment.
   - Keep it compact, honest, and understandable.
   - Do not repeat the full answer.

## Standard output

```markdown
## 📊 Qualitätsmatrix

| Kriterium | Status |
|---|---|
| Erfolgs-KPI | Nicht extern validiert |
| Geschwindigkeits-KPI | Nicht messbar ohne Timer |
| Effizienz-KPI | Nicht belastbar berechenbar |
| Bearbeitungsstatus der Nutzeranfrage | Erfüllt / Teilweise erfüllt / Offen |
| Nutzbarkeit des Ergebnisses | Hoch / Mittel / Niedrig: [kurze Begründung] |
| Fehlende Daten transparent markiert | Ja / Nein |
| Simulation vermieden | Ja / Nein |
| Offene Lücken oder nicht messbare Werte | [kurz benennen] |

## ✅ Selbstbewertung

✅ Wie gut ist das Ergebnis?
[Kurze ehrliche Einschätzung]

🎯 Wie gut passt es zum Ziel?
[Kurze Einschätzung zur Zielpassung]

⚠️ Welche Grenze, Schwäche oder welches Risiko bleibt?
[Offene Grenze/Risiko]

🧠 Ehrliches Kurzurteil:
[Ein Satz]
```

## Status wording

Use these status values consistently:

- **Erfüllt**: the user’s concrete request was completed.
- **Teilweise erfüllt**: a useful result exists, but data, confirmation, execution, validation, permissions, or files were missing.
- **Offen**: the user’s request could not be executed or the needed input is absent.
- **Hoch nutzbar**: the result can be used directly or with minimal edits.
- **Mittel nutzbar**: the result is a good draft or working base.
- **Niedrig nutzbar**: the result needs substantial missing input or validation.

## Guardrails

- Never use fake precision.
- Never present assumptions as measured results.
- Never hide missing data behind confident language.
- Never imply external validation when no source, test, timer, or measurement was used.
- For high-stakes domains, state that the result is not a substitute for qualified professional review.
- Keep the closing review brief unless the user explicitly asks for a deep audit.

## Optional closing line

Add one quiet closing line only when it fits the style of the conversation:

> Jede Aufgabe endet mit Klarheit.
