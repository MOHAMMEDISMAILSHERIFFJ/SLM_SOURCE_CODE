# THEIA Source Code

This directory organizes Python source components extracted from or associated with the original THEIA research notebooks.

Not every directory currently represents a complete standalone implementation.

## Module Overview

| Directory | Responsibility | Status |
|---|---|---|
| `models/` | THEIA-SLM architecture | Prototype extracted |
| `data/` | Data loading and feature processing | Notebook remains reference |
| `training/` | Model training and checkpoints | Notebook remains reference |
| `evaluation/` | Validation and test evaluation | Notebook remains reference |
| `anomaly_detection/` | Isolation Forest workflow | Notebook remains reference |
| `inference/` | Model inference | Standalone extraction pending |
| `notebook_exports/` | Python notebook exports | Exports available |
| `ollama/` | Ollama integration documentation | Documented |

## Architecture

The custom THEIA-SLM prototype uses RoPE, GQA, RMSNorm, and SwiGLU.

Isolation Forest provides statistical anomaly scores.

Qwen through Ollama provides evidence-grounded natural-language investigation.

These are separate components and must be evaluated independently.

## Development Principles

- Preserve original notebooks.
- Extract modules with validated interfaces.
- Avoid treating placeholders as completed implementations.
- Keep data, training, evaluation, and inference separate.
- Do not commit secrets, raw private data, or local environment files.

See the notebook and extraction documentation for implementation details.