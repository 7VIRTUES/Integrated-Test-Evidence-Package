# Integrated Test Evidence Package (ITEP) — Project Overview

## Purpose
Build a portfolio-quality ITEP that demonstrates end-to-end Systems Engineering skills:
requirements → verification planning → test execution → data pipeline → analysis → reporting → RCA → controlled baselines.

## Scenario (Assumption)
A **sensor module** reports:
- Distance (mm)
- Temperature (°C)
- Timestamp (ms)
- Status flags (OK / WARN / FAULT)

Injected failure modes to investigate:
- **Dropouts** (missing samples)
- **Drift** (bias slowly grows over time)
- **Timing jitter** (irregular sample intervals)

## Primary Deliverables (Evidence Chain)
1. Requirements spec (10–15 “shall” statements)
2. Traceability matrix (Req → verification → test case → evidence)
3. Test plan + test cases (8–12)
4. Dataset + pipeline (raw logs → processed tables)
5. Python analysis (metrics, plots, pass/fail evaluation)
6. Test report (results, conclusions, risks, next actions)
7. ≥2 RCA reports (defect evidence + corrective actions)
8. Versioned baselines (tags/releases + changelog)
9. One-page briefing (summary for interview)

## Workflow (How Evidence Is Produced)
- Define requirements and acceptance criteria
- Plan tests and data collection
- Generate/collect raw logs from a simulator or harness
- Process logs into analysis-ready datasets
- Evaluate each requirement via automated checks + plots
- Record results in a test report
- Perform RCA for injected failures and track corrective actions
- Cut a tagged baseline release with release notes

## Toolchain (What We Use and Why)
| Tool | What it accomplishes | Where it shows up in this project | Evidence produced |
|---|---|---|---|
| Git | Change control, baselines, traceability of edits | Tags/releases, commit history | Reproducible baselines + change log |
| Markdown (docs) | Clear technical documentation | Requirements, test plan, reports | Reviewable specs + reports |
| Python (pandas/matplotlib) | Data pipeline + analysis + automated pass/fail | `scripts/`, `analysis/`, `tests/` | Metrics, plots, evaluated thresholds |
| Pytest | Automated verification checks | `tests/` | Pass/fail logs in CI + local runs |
| C/C++ (simulated embedded) | Realistic producer of sensor messages/logs | `src/` | Raw logs + defect injection hooks |
| CMake (optional) | Repeatable builds for C/C++ | root build config | Deterministic builds |
| GitHub Actions (optional) | CI for reproducibility | `.github/workflows/` | “green” verification runs |

## Definition of Done (Project-Level)
- Every requirement is measurable and mapped to a verification method.
- Every test case has objective pass/fail criteria and captured data.
- Analysis can reproduce results from raw logs quickly (target: <5 minutes).
- At least two RCA reports exist with evidence-backed corrective actions.
- At least one tagged baseline release exists with release notes.