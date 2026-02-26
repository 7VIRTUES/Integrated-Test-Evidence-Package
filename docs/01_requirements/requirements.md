# Requirements Specification — Sensor Module ITEP

## Notes
- Units: distance in mm, temperature in °C, timestamp in ms.
- Unless stated otherwise, requirements apply under nominal conditions during a 10-minute run.

## Requirements (System/Subsystem)
**SR-001 (Distance Range):** The sensor module shall report distance values in the range **[100, 5000] mm**.

**SR-002 (Distance Accuracy):** The reported distance shall have an absolute error ≤ **±20 mm** when compared to ground truth.

**SR-003 (Temperature Range):** The sensor module shall report temperature values in the range **[-20, 85] °C**.

**SR-004 (Temperature Accuracy):** The reported temperature shall have an absolute error ≤ **±1.0 °C** when compared to ground truth.

**SR-005 (Sample Rate):** The sensor module shall output samples at **10 Hz ± 0.5 Hz** (measured over any 60-second window).

**SR-006 (Timing Jitter):** The time delta between consecutive samples shall be **100 ms ± 15 ms** for at least **99.0%** of samples in a run.

**SR-007 (Dropout Rate):** The module shall maintain a sample dropout rate ≤ **0.5%** over a 10-minute run.

**SR-008 (Timestamp Monotonicity):** The timestamp shall be strictly monotonic increasing (no repeats, no reversals).

**SR-009 (Data Completeness):** Each sample shall include distance, temperature, timestamp, and status fields (no null/blank fields).

**SR-010 (Status Flags):** The module shall set status to **FAULT** when distance is outside SR-001 range or temperature is outside SR-003 range.

**SR-011 (Drift Bound):** Distance bias drift shall be ≤ **10 mm per 10 minutes** under steady-state conditions.

**SR-012 (Log Format):** The module shall emit logs in a parseable line format defined in the interface spec (CSV or JSONL), with one record per sample.