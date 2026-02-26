# ITEP — Sensor Module Verification Portfolio

This repo is an Integrated Test Evidence Package (ITEP) demonstrating systems engineering verification:
requirements, traceability, test cases, dataset + pipeline, Python analysis, test reports, RCA, and versioned baselines.

## Scenario
A sensor module outputs distance + temperature + timestamps; we verify performance and investigate injected faults
(dropouts, drift, jitter).

## Repo Map
- docs/ — requirements, traceability, plans, reports
- src/ — simulator / embedded-style producer
- data/ — raw + processed logs
- analysis/ — notebooks/scripts for metrics + plots
- tests/ — automated verification checks