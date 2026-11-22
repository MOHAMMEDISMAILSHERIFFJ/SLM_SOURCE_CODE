# THEIA Research Workspace

THEIA is the main research workspace for APT-related security-event telemetry analysis, anomaly detection, compact sequence-model experimentation, and evidence-grounded language-model investigation.

## Directory Structure

| Directory | Description |
|---|---|
| `notebooks/` | Original interactive Jupyter research notebooks |
| `src/` | Organized Python source and notebook exports |
| `docs/` | Research documentation and extraction status |

## Main Components

### Isolation Forest
A statistical baseline for identifying unusual patterns in engineered telemetry features.

### THEIA-SLM
A compact decoder-only transformer prototype designed for next-token learning over structured telemetry sequences.

### Qwen Investigator
Qwen3.5-4B through Ollama provides natural-language investigation using retrieved evidence.

RAG supplies evidence context but does not modify Qwen model weights.

## Recommended Reading

1. Read the full interactive research notebook.
2. Review the Qwen3.5 research lab.
3. Review the Ollama RAG notebook.
4. Inspect the extracted source modules.
5. Read `docs/EXTRACTION_STATUS.md`.

## Dataset

https://huggingface.co/datasets/ISMAIL1216/APT-Detection-Qwen-IsolationForest

## Important Limitations

Anomaly indicators are not confirmed intrusions. The available evidence must independently support any claims about malware, threat actors, victims, CVEs, or successful exfiltration.

The extracted custom model prototype is not yet verified as the exact architecture of the final checkpoint.