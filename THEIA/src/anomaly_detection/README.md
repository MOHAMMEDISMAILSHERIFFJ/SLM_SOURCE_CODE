# THEIA Anomaly Detection

This directory is reserved for statistical anomaly-scoring components.

## Isolation Forest

Isolation Forest is used as a statistical baseline over engineered telemetry features.

Its output indicates unusual patterns relative to the fitted data distribution. It does not independently prove malicious activity, compromise, or APT attribution.

## Intended Responsibilities

- Consume validated telemetry features.
- Fit anomaly-detection baselines.
- Generate anomaly scores.
- Select thresholds using validation data.
- Apply selected thresholds to held-out test data.
- Record flagged windows and supporting metadata.

## Current Status

The primary anomaly-scoring workflow remains in the research notebooks.

## Reporting

Clearly distinguish anomaly scores, selected thresholds, flagged events, and independently confirmed malicious activity.

Do not describe anomaly scores as attack probabilities without calibration evidence.