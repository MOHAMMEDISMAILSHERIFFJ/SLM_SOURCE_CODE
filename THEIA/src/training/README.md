# THEIA Training Module

This directory is reserved for standalone model-training and checkpoint-management components.

## Intended Responsibilities

- Training data preparation.
- Model configuration.
- Batch construction.
- Optimization and gradient updates.
- Learning-rate scheduling.
- Checkpoint saving and recovery.
- Training and validation monitoring.

## Current Status

The main training workflow remains in the research notebooks and their Python exports.

## Data Separation

- Training data is used for optimization.
- Validation data is used for model selection.
- Test data remains held out for final evaluation.

The custom THEIA-SLM is designed for next-token learning over structured telemetry sequences. It is not automatically a supervised APT classifier.

## Reproducibility

Record random seeds, model configurations, optimizer settings, data manifests, checkpoint identifiers, and environment details.