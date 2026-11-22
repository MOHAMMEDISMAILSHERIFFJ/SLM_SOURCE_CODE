# THEIA Evaluation Module

This directory is reserved for validation, test evaluation, and experiment reporting.

## Intended Responsibilities

- Isolation Forest anomaly-score evaluation.
- Validation-based threshold selection.
- Held-out test evaluation.
- Sequence-model loss and next-token evaluation.
- False-positive and false-negative inspection where labels exist.
- Experiment metadata and result reporting.

## Current Status

Evaluation workflows remain primarily in the research notebooks. This directory is an organizational module until standalone extraction is validated.

## Evaluation Principles

- Do not tune on the held-out test set.
- Do not report accuracy without suitable ground-truth labels.
- Do not equate anomaly rates with attack-detection rates.
- Evaluate LLM answer quality separately from detector metrics.
- Preserve evaluation manifests and experiment identifiers.

LLM answers should be assessed for evidence support, citation correctness, numerical consistency, uncertainty handling, and unsupported attribution.