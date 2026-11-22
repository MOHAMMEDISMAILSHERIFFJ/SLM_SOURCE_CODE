# THEIA Python Notebook Exports

This directory contains Python exports generated from the original Jupyter notebooks.

## Export Catalogue

| Python file | Original notebook | Purpose |
|---|---|---|
| `THEIA_APT_Research_FULL_SLM_INTERACTIVE_12HFINAL.py` | Full interactive notebook | Integrated THEIA workflow |
| `THEIA_CODE.py` | THEIA_CODE.ipynb | Original data discovery |
| `THEIA_Qwen3_5_4B_APT_Research_Lab.py` | Qwen research lab | Qwen research and RAG |
| `THEIA_Qwen3_5_4B_APT_Research_Lab_Ollama_RAG.py` | Ollama RAG lab | Local Ollama investigation |
| `cdm_to_slm_dataset.py` | CDM conversion notebook | Grounded instruction-data generation |

## Important Notes

- Original `.ipynb` files remain the primary interactive records.
- Exports may contain notebook-specific paths and environment assumptions.
- A Python export is not automatically a tested standalone package.
- Some exports may use notebook-specific functions such as `get_ipython()`.
- Regenerate exports from their notebooks when synchronized changes are needed.

Review dependencies and paths before running an export as a script.