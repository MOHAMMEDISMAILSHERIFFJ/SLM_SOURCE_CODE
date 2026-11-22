# THEIA Data Module

This directory is reserved for the data-processing components used by THEIA.

## Intended Responsibilities

- Raw telemetry discovery and loading.
- Schema validation.
- Data integrity checks.
- Train, validation, and test separation.
- Feature engineering.
- Event and window construction.
- Token and sequence preparation.
- Provenance and transformation metadata.

## Current Status

The original data-processing workflow remains primarily in the research notebooks and their Python exports.

This directory should not be treated as a complete standalone pipeline until the implementations have been extracted and tested.

## Data Integrity

- Inspect schemas before processing.
- Preserve source identifiers.
- Avoid train/test leakage.
- Use streaming or bounded reads for large Parquet shards.
- Keep raw data immutable.
- Record transformation parameters.

Dataset:
https://huggingface.co/datasets/ISMAIL1216/APT-Detection-Qwen-IsolationForest