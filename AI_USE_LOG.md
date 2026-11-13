# Generative-AI Use Log

> If no generative AI was used, write `No generative AI used` in the declaration
> and leave the activity tables empty. Never paste personal, confidential, or
> restricted data here.

## Declaration

**Team:** CEBE Raphaël, CHENNOUF Rayan  
**Generative AI used:** yes  
**Declaration:** Claude (Anthropic) was used during TD1 to explain the instructions and concepts, guide the local setup, suggest code for the data invariants and the three baselines, and draft the interpretation. Every retained output was run, checked against the data and understood by the student.

We understand that AI output is neither experimental evidence nor a scientific
source. We verified every retained contribution against submitted code,
configuration, data provenance, primary sources, and result artifacts.

## Material-use record

| ID | Date | Tool/model if visible | Purpose | Input-context description | Output retained or rejected | Verification performed | Affected artifact paths | Student(s) responsible |
|---|---|---|---|---|---|---|---|---|
| AI-01 | 2026-10-22 | Claude Opus 5.5 (Anthropic) | Explanation of TD1, setup guidance, code suggestions (contract, invariants, baselines), interpretation draft | TD1 instructions and public synthetic course data only; no restricted data | Retained after review | Notebook restarted and run top to bottom; invariants and negative tests pass; MAE/sMAPE checked against an independent recomputation | notebooks/td1_support_starter.ipynb, evidence/td1/ | CEBE Raphaël / CHENNOUF Rayan |
| AI-02 | 2026-10-22 | Claude Opus 5.5 (Anthropic) | TD2 explanation, code suggestions (rolling loop, ETS/SARIMA, aggregation, selection rule), interpretation draft | TD2 instructions and public synthetic course data only | Retained after review | Notebook rerun top to bottom; nine fold rows and aggregates matched an independent recomputation; zero convergence warnings | notebooks/td2_support_starter.ipynb, evidence/td2/ | CEBE Raphaël / CHENNOUF Rayan |
| AI-03 | 2026-11-13 | Claude Opus 5.5 (Anthropic) | Repository audit of TD1/TD2 against the README and rubrics; repair of the TD2 portfolio notebook (per-model warning ledger, failed-fit rows, runtimes, information-boundary audit, evidence export) and of the course-root lookup so notebooks run from the portfolio | TD1/TD2 instructions, rubrics, our notebooks and public synthetic course data only | Retained after review | Both notebooks restarted and run top to bottom from `notebooks/` (execution counts 1–9, no errors); all TD1 metrics and TD2 MAE/sMAPE, Ljung–Box and decision identical to the previous evidence | notebooks/td1_support_starter.ipynb, notebooks/td2_support_starter.ipynb, evidence/td2/ | CEBE Raphaël / CHENNOUF Rayan |

## Corrections and rejected suggestions

When material AI assistance was used, record at least one correction or rejected
suggestion. This shows verification; it is not a penalty.

| AI ID | Problem found | How it was detected | Correction or decision |
|---|---|---|---|
| AI-01 | The first "gap" negative test was caught by the row-count check, not by the date-continuity check, so it did not prove the gap check works | Error message read "expected 1433 rows, got 1432" instead of "gap in daily dates" | Added an `expected_rows` parameter so the gap test runs with 1432 rows and only the continuity check can fire |
| AI-03 | The committed TD2 notebook was an older copy (last cells never executed, residual check left as TODO, no decision or interpretation); warnings were counted per origin instead of per model; runtimes required by the rubric were not recorded | Comparing the committed notebook with the working copy in the course bundle and checking each rubric line | Replaced with the complete notebook, made the warning ledger and timer per model and origin, kept failed fits as rows, reran top to bottom and re-exported the evidence |