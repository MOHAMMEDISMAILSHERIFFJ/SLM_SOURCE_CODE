# THEIA — APT Research and Raw-Event Small Language Model

THEIA is a cybersecurity research project focused on structured security-event telemetry, anomaly detection, compact language-model experimentation, and evidence-grounded investigation.

The project combines statistical anomaly analysis, custom sequence-model research, and local LLM-assisted investigation.

## Research Components

| Component | Purpose |
|---|---|
| Isolation Forest | Statistical anomaly scoring over engineered telemetry features |
| THEIA-SLM | Compact decoder-only transformer for structured telemetry sequence learning |
| Qwen3.5 through Ollama | Evidence-grounded cybersecurity investigation using RAG |

These components have different responsibilities. RAG does not fine-tune Qwen, and anomaly scores do not independently prove an attack.

## Research Workflow

1. Dataset discovery and inspection.
2. Schema validation and data integrity checks.
3. Raw-event processing and feature engineering.
4. Train, validation, and test separation.
5. Isolation Forest baseline training.
6. Telemetry sequence construction.
7. Custom THEIA-SLM experimentation.
8. Model evaluation and checkpoint management.
9. Evidence indexing and retrieval.
10. Local Qwen inference through Ollama.
11. Citation validation and evidence-grounded investigation.

## Repository Structure

```text
SLM_SOURCE_CODE/
|
|-- README.md
|
`-- THEIA/
    |-- README.md
    |-- notebooks/
    |   `-- README.md
    |-- docs/
    |   `-- README.md
    |-- src/
        |-- README.md
        |-- models/
        |-- data/
        |-- training/
        |-- evaluation/
        |-- anomaly_detection/
        |-- inference/
        |-- notebook_exports/
        `-- ollama/
```

## Research Notebooks

| Notebook | Purpose |
|---|---|
| THEIA_APT_Research_FULL_SLM_INTERACTIVE_12HFINAL.ipynb | Integrated data processing, Isolation Forest, custom SLM research, and RAG investigation |
| THEIA_CODE.ipynb | Original Google Drive data discovery and preprocessing |
| THEIA_Qwen3_5_4B_APT_Research_Lab.ipynb | Qwen3.5 research, dataset inspection, evaluation planning, and RAG |
| THEIA_Qwen3_5_4B_APT_Research_Lab_Ollama_RAG.ipynb | Local Ollama-based Qwen investigation |
| cdm_to_slm_dataset.ipynb | CDM telemetry to grounded instruction dataset conversion |

See [Notebook Documentation](THEIA/notebooks/README.md).

## Source Code

The `THEIA/src/` directory organizes extracted Python source and notebook exports.

- `models/`: Custom THEIA-SLM architecture prototype.
- `data/`: Data processing module organization.
- `training/`: Training workflow organization.
- `evaluation/`: Evaluation workflow organization.
- `anomaly_detection/`: Statistical anomaly detection.
- `inference/`: Inference module organization.
- `notebook_exports/`: Python exports of research notebooks.
- `ollama/`: Ollama integration and deployment documentation.

Some modules are organizational directories whose implementations remain in the original notebooks. Their extraction status is documented separately.

## Custom Model Architecture

The extracted `THEIASLM` prototype includes:

- Rotary Positional Embeddings (RoPE)
- Grouped Query Attention (GQA)
- RMSNorm
- SwiGLU feed-forward blocks
- Causal self-attention
- Decoder-only transformer blocks

**Checkpoint compatibility:** The extracted prototype has not been verified as the exact architecture used by the final 34,510,699-parameter checkpoint. Configuration and state-dict compatibility must be checked before loading.

## Ollama Deployment

The separate Qwen3.5 4B deployment package uses GGUF Q4_K_M quantization.

Verified local Ollama alias:

```bash
theia-gguf-verified
```

Create and run:

```bash
ollama create theia-gguf-verified -f Modelfile
ollama run theia-gguf-verified
```

The GGUF model is a Qwen deployment artifact, not a conversion of the custom THEIA PyTorch checkpoint.

See [Ollama Documentation](THEIA/src/ollama/README.md).

## Dataset

Hugging Face dataset:

https://huggingface.co/datasets/ISMAIL1216/APT-Detection-Qwen-IsolationForest

The dataset repository contains the THEIA data partitions and model artifacts.

## Evidence and Research Integrity

- Anomaly scores are not attack probabilities.
- A flagged event is not proof of compromise.
- Dataset naming does not establish individual APT attribution.
- Threat-actor, malware, CVE, victim, and exfiltration claims require supporting evidence.
- Detection metrics require reliable labels and held-out evaluation.
- Numerical findings should be traceable to the underlying telemetry.

## Environment

The local development environment used Python 3.12, an NVIDIA RTX 4050 GPU with 6 GB VRAM, and 16 GB system RAM.

Use batching or streaming for large datasets. Review each notebook's dependencies and configuration before execution.

## Reproducibility

- Preserve original research notebooks.
- Keep train, validation, and test data separate.
- Record model configurations and random seeds.
- Verify checkpoint compatibility.
- Avoid publishing credentials or private data.
- Report only experimentally supported results.

## Project Links

- [GitHub Source](https://github.com/MOHAMMEDISMAILSHERIFFJ/SLM_SOURCE_CODE)
- [Hugging Face Dataset](https://huggingface.co/datasets/ISMAIL1216/APT-Detection-Qwen-IsolationForest)
- [Qwen3.5 4B Base](https://huggingface.co/Qwen/Qwen3.5-4B-Base)

## License

No single project-wide license is currently declared. Refer to the original dataset, base-model, and third-party component licenses.