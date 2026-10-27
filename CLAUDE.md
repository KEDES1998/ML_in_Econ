# CLAUDE.md — Homework: Machine Learning in Economics (UZH, HS 2026)

## Context
- Course: Machine Learning in Economics, University of Zurich, Fall 2026
- Instructor: Damian Kozbur · TA: Paul Stephan (paul.stephan@econ.uzh.ch)
- Three assignments, each a prepared Python notebook with embedded questions:
  - HW1 due **Nov 3, 2026** · HW2 due **Nov 17, 2026** · HW3 due **Dec 8, 2026**
- Topics: the two basic learning paradigms covered in class (supervised: setup, validation, train/validate/test, K-fold CV, tuning, lasso/ridge, trees; unsupervised: density estimation, clustering, dimension reduction).
- Submission: notebook by e-mail to the TA. Groups of 1–4; one submission per group with **all names clearly at the top**.
- Grading: bonus +0.5 on the final grade for ≥2 of 3 assignments completed in good faith. → **Every question must be answered.** No blanks, no "TODO".

## Project structure
```
ML_in_Econ/
    CLAUDE.md
    HW1/
    HW2/
    MainProject/
```
- `HW1/`, `HW2/`: one folder per assignment. Notebook, data and any outputs for that assignment stay in its folder.
- `MainProject/`: final course project. Do not read from or modify it while working on homework unless explicitly asked.
- Work only inside the folder of the assignment at hand. Use relative paths from the notebook's folder. Do not copy files between assignment folders.

## Goal
Answers that are **correct, unambiguous and short**. Correctness first, brevity second, nothing else matters.

## Workflow
1. Read the whole notebook before writing anything. Note every question and every task cell.
2. Work top to bottom. Answer each question **in place**, directly below it (code cell for code tasks, markdown cell for written answers).
3. Do not modify, delete or reorder provided cells, data loading, or function signatures unless the question asks for it.
4. Use the methods, libraries, parameters and variable names the notebook specifies. If none are specified, use what the notebook already imports (e.g. numpy, pandas, scikit-learn, matplotlib). Do not add new dependencies.
5. Set random seeds wherever randomness enters (splits, CV folds, initialisations, clustering).
6. At the end: **Restart kernel & Run All**. The notebook must run cleanly from scratch with all outputs visible.

## Correctness rules (non-negotiable)
- Every number in a written answer must come from an output actually produced in the notebook. Never estimate, round loosely, or invent results.
- Interpretations must match the output (sign, magnitude, which model wins, direction of a trade-off).
- Use the course's definitions and notation (lecture notes in this project), e.g. CV-MSE = $\frac{1}{n}\sum_{i=1}^n (y_i-\hat y_i)^2$, penalised estimation $\hat\theta=\arg\min_\theta \frac1n\sum_i L(y_i,f(x_i,\theta))+\lambda p(\theta)$, lasso $p(\theta)=\sum_k|\theta_k|$, ridge $p(\theta)=\sum_k\theta_k^2$.
- Respect the train/validation/test logic: tune on training/validation (or CV), report final performance on test data only. No leakage (fit scalers/imputers/feature selection on training data only).
- If a question is ambiguous, pick the most standard reading and state the assumption in **one line**.
- If something cannot be done (missing data, broken cell), say so explicitly instead of guessing.

## Answer style
- Lead with the direct answer. Then at most 1–3 sentences of justification.
- Typical length: **1–4 sentences** per written question. Longer only if the question explicitly asks for a discussion.
- Quote the relevant number(s) with sensible precision (e.g. 3–4 significant digits) and name the model/setting they belong to.
- No restating the question, no introductions, no summaries, no generic ML explanations, no hedging filler.
- Math in LaTeX within markdown (`$...$`), never as plain-text formulas.
- Language: English (same as the notebooks).

### Template for a written answer
> **Answer:** Lasso with $\lambda$ chosen by 5-fold CV has the lowest test MSE (0.0412 vs. 0.0437 for ridge). The penalty sets 31 of 120 coefficients to zero, which reduces variance more than it increases bias here.

## Code style
- Minimal and readable; only what the task needs.
- Short comments only where a step is not obvious.
- Plots: title, axis labels, legend where needed. One plot per question unless asked otherwise.
- Print the quantities the written answer refers to, so the link between code and answer is visible.

## Final check before handing over
- [ ] Every question answered (search for empty answer cells / TODO / placeholder text)
- [ ] Restart & Run All succeeds without errors
- [ ] Every number in the text matches the printed output
- [ ] Seeds set; results reproducible
- [ ] No test-set use during tuning; no leakage
- [ ] Answers short, direct, in English, math rendered in LaTeX
- [ ] Group member names at the top of the notebook

## Note
The student reviews and approves every answer before submission (honor system for group work). Flag anything uncertain clearly so it can be checked.