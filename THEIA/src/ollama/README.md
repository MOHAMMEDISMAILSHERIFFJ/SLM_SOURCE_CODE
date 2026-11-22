# THEIA Ollama Integration and GGUF Deployment

This directory documents the Ollama-based local inference workflow used by THEIA.

## 1. Purpose

Ollama provides local inference for the Qwen-based cybersecurity investigation assistant.

It supports natural-language interpretation of retrieved telemetry evidence, evidence summarization, uncertainty handling, and analyst questions.

It is separate from the custom PyTorch THEIA-SLM and Isolation Forest detector.

## 2. GGUF Package

The prepared package contains:

| File | Description |
|---|---|
| `theia-qwen35-4b-Q4_K_M.gguf` | Qwen3.5 4B Base model in Q4_K_M GGUF format |
| `theia-qwen35-vision-projector.gguf` | Separate vision projector artifact |
| `Modelfile` | Ollama model configuration |
| `README.md` | Deployment documentation |

The main GGUF was extracted from an existing Ollama model storage and checked against its source blob.

This was extraction and repackaging, not a fresh Safetensors-to-GGUF conversion.

## 3. Model Details

- Base model: Qwen3.5 4B Base
- Architecture: Qwen3.5
- Parameters: approximately 4.2 billion
- Quantization: Q4_K_M
- Format: GGUF
- Runtime: Ollama
- Configured context: 8192 tokens
- Temperature: 0.1
- Top-k: 20
- Top-p: 0.95
- Repeat penalty: 1.12

Original model:

https://huggingface.co/Qwen/Qwen3.5-4B-Base

## 4. Modelfile Configuration

The verified Modelfile uses the main GGUF file:

```text
FROM ./theia-qwen35-4b-Q4_K_M.gguf

PARAMETER num_ctx 8192
PARAMETER temperature 0.1
PARAMETER top_p 0.95
PARAMETER top_k 20
PARAMETER repeat_penalty 1.12

SYSTEM """
You are THEIA, an evidence-grounded cybersecurity investigation assistant.
Use only supplied evidence for dataset-specific claims.
Do not invent APT attribution, malware families, CVEs, successful exfiltration,
victims, credentials, or compromise.
Clearly distinguish observed evidence, inference, and unknowns.
"""
```

## 5. Installation

Install Ollama:

https://ollama.com/download

Open a terminal in the directory containing the GGUF and Modelfile.

Create the model:

```powershell
ollama create theia-gguf-verified -f Modelfile
```

Inspect it:

```powershell
ollama show theia-gguf-verified
```

Run it:

```powershell
ollama run theia-gguf-verified
```

List installed models:

```powershell
ollama list
```

## 6. THEIA Application Integration

The separate THEIA browser application uses FastAPI and the local Ollama service.

Select the model:

```powershell
$env:THEIA_LLM_MODEL = "theia-gguf-verified"
```

Launch the application from its project environment:

```powershell
python -m theia_app.launcher
```

Local application address:

```text
http://127.0.0.1:8765
```

Status endpoint:

```text
http://127.0.0.1:8765/api/status
```

Restart the application after changing its model environment variable.

## 7. Retrieval-Augmented Generation

The documented THEIA investigation pipeline includes:

1. Evidence preparation.
2. Semantic retrieval.
3. BM25 lexical retrieval.
4. Reciprocal Rank Fusion.
5. Candidate reranking.
6. Evidence-context selection.
7. Ollama chat generation.
8. Citation validation and numerical audit checks.

The configured embedding model is:

```text
nomic-embed-text
```

This is a separate Ollama model, not part of the Qwen GGUF package.

RAG supplies retrieved evidence to Qwen. It does not modify the model weights.

## 8. Evidence Grounding

The investigator should:

- Cite supplied evidence identifiers.
- Separate observations from interpretations.
- Identify missing information.
- Return UNKNOWN when attribution is unsupported.
- Avoid inventing malware, CVEs, threat actors, victims, or exfiltration.
- Avoid treating anomaly scores as proof of compromise.

## 9. Vision Projector

The vision projector is preserved as a separate artifact.

Its presence does not prove that the current Modelfile has configured multimodal inference. The verified Modelfile references the main GGUF only.

Treat vision support as unverified until compatible projector integration is separately configured and tested.

## 10. Hugging Face Package

Intended package location:

https://huggingface.co/datasets/ISMAIL1216/APT-Detection-Qwen-IsolationForest/tree/main/OLLAMA

Expected files:

```text
OLLAMA/
|-- README.md
|-- Modelfile
|-- theia-qwen35-4b-Q4_K_M.gguf
`-- theia-qwen35-vision-projector.gguf
```

Verify the remote files before claiming the package has been published.

## 11. Troubleshooting

Check the Ollama installation:

```powershell
ollama list
```

Inspect the model:

```powershell
ollama show theia-gguf-verified
```

Pull the embedding model if needed:

```powershell
ollama pull nomic-embed-text
```

The actual memory requirement depends on context length, KV cache, concurrent processes, and runtime overhead.

## 12. Model Distinction

The Qwen3.5 GGUF is a deployment artifact for the Ollama investigator.

It is not a GGUF conversion of the custom THEIA PyTorch checkpoint.