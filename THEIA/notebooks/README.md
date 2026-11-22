# THEIA Research Notebooks

This directory preserves the original interactive Jupyter notebooks used during THEIA research.

## 1. THEIA_APT_Research_FULL_SLM_INTERACTIVE_12HFINAL.ipynb

**Purpose:** Main integrated research workflow.

Covers:

- Dataset discovery and Parquet inspection.
- Data integrity and schema checks.
- Feature engineering and telemetry window creation.
- Isolation Forest baseline.
- Train, validation, and test separation.
- Custom decoder-only THEIA-SLM architecture.
- RoPE, GQA, RMSNorm, and SwiGLU components.
- Sequence-model training and checkpoint handling.
- Evidence preparation and retrieval.
- Qwen3.5 integration through Ollama.
- RAG-based investigation and evidence citations.

**Recommended use:** Primary end-to-end THEIA research notebook.

## 2. THEIA_CODE.ipynb

**Purpose:** Original dataset discovery and preprocessing.

Includes Google Drive mounting, source directory discovery, recursive file inventory, file-size inspection, and processed-directory preparation.

**Recommended use:** Historical data preparation workflow. Review paths before execution.

## 3. THEIA_Qwen3_5_4B_APT_Research_Lab.ipynb

**Purpose:** Qwen3.5 research and telemetry investigation.

Covers dataset discovery, schema inspection, split review, anomaly-score evaluation planning, evidence preparation, retrieval, Qwen investigation, and optional model-adaptation exploration.

**Recommended use:** Qwen-centered research and RAG experimentation.

Retrieval is not equivalent to fine-tuning.

## 4. THEIA_Qwen3_5_4B_APT_Research_Lab_Ollama_RAG.ipynb

**Purpose:** Local Ollama-backed Qwen investigation.

Covers local model configuration, dataset inspection, evidence preparation, retrieval, embeddings, Qwen inference, and evidence-cited responses.

**Requirements:** Ollama service, selected chat model, and embedding model must be available locally.

## 5. cdm_to_slm_dataset.ipynb

**Purpose:** Convert CDM-style telemetry and knowledge documents into grounded instruction examples.

Covers JSON/JSONL inputs, Markdown knowledge documents, positive questions, hard-negative questions, grounding checks, train/validation splitting, and JSONL export.

**Recommended use:** Evidence-grounded instruction dataset preparation.

## Recommended Execution Order

1. Full interactive THEIA notebook.
2. Qwen3.5 research lab.
3. Ollama RAG research lab.

Use the original preprocessing notebook for historical context and the CDM conversion notebook for a separate dataset-generation workflow.

## Execution Guidance

- Review data paths and dependencies.
- Avoid running all notebooks simultaneously.
- Preserve original notebooks.
- Use bounded reads for large Parquet files.
- Verify Ollama model availability.
- Inspect outputs for secrets and local paths before publishing.