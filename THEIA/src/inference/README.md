# THEIA Inference Module

This directory is reserved for model inference and prediction utilities.

## Intended Responsibilities

- Load a verified architecture and checkpoint.
- Validate model configuration and vocabulary.
- Prepare input telemetry sequences.
- Execute next-token inference.
- Apply decoding settings.
- Return predictions and metadata.

## Current Status

A standalone inference module has not yet been verified against the final THEIA checkpoint.

The extracted prototype in `models/theia_slm.py` must not be assumed to match the final checkpoint without state-dict and configuration validation.

## Qwen Separation

Qwen3.5 inference through Ollama is documented separately in `../ollama/README.md`.

The custom THEIA-SLM and Qwen investigator are separate execution paths.