# THEIA Model Architecture

This directory contains the extracted custom THEIA-SLM architecture prototype.

## Architecture Components

The extracted `theia_slm.py` prototype includes:

- Rotary Positional Embeddings (RoPE).
- Grouped Query Attention (GQA).
- RMSNorm.
- SwiGLU feed-forward network.
- Causal self-attention.
- Decoder-only transformer blocks.
- Token embeddings and language-model output head.

## Architecture Purpose

The prototype is intended for compact next-token learning over structured telemetry sequences.

## Checkpoint Compatibility

The extracted architecture has not been verified as the exact architecture used by the final 34,510,699-parameter checkpoint.

Before loading a checkpoint:

1. Inspect its state-dict keys.
2. Inspect its saved configuration.
3. Compare parameter names and tensor dimensions.
4. Verify vocabulary and embedding dimensions.
5. Perform a strict state-dict load.
6. Test a small forward pass.

Do not hide architecture mismatches using non-strict loading.

## Separation from Qwen

The custom PyTorch THEIA-SLM is separate from Qwen3.5-4B.

The Ollama GGUF package is not a GGUF conversion of the custom THEIA PyTorch checkpoint.