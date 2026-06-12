# QWEN_2.5_7B
Fine-tuning pipeline, hosting server, and API docs for the Qwen model

# SigmaLoop AI Model

Fine-tuned Qwen2.5-Coder-7B on 30,000 Codeforces Python submissions.

## Model
- Base: Qwen2.5-Coder-7B
- Fine-tuned on: MatrixStudio/Codeforces-Python-Submissions
- Hosted on: HuggingFace → David0dods/Qwen2.5-7B-Codeforces

## Structure
- `fine-tuning/` — Kaggle training notebook
- `hosting/` — Flask + ngrok API server
- `docs/` — API endpoint reference

## API
See [docs/api-reference.md](docs/api-reference.md)
