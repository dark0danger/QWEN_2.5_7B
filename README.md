# Codeforces Tutor AI Engine

This repository contains the artificial intelligence subsystem for the Codeforces Tutor project. It includes the fine-tuning configurations and local hosting scripts for a custom Large Language Model optimized to assist with competitive programming.

The core engine is powered by a fine-tuned Qwen2.5-Coder-7B architecture. It leverages Low-Rank Adaptation (LoRA) via the Unsloth framework to enable high-speed, 4-bit quantized inference for algorithmic problem-solving and hint generation.

## Repository Structure

* `fine-tuning/final-qwen-2-5-7b.ipynb`: The primary notebook containing the LoRA training pipeline, dataset preparation, and Hugging Face upload logic.
* `hosting/hosting.ipynb`: The inference server script. It dynamically attaches the custom LoRA adapter to the base model and serves it via a Flask web application and Ngrok tunnel.
* `docs/api-reference.md`: Technical documentation outlining the endpoint structures, request payloads, and response formats for the frontend integration.
* `requirements.txt`: Python package dependencies required for training and hosting.
* `.gitignore`: Excludes virtual environments, caches, and heavy checkpoints from version control.

## Hardware Requirements

To run the local hosting setup, the host machine must meet the following criteria:
* **GPU:** NVIDIA GPU with a minimum of 8GB to 12GB VRAM (e.g., Tesla T4, RTX 2070, or higher).
* **System:** Linux or Windows Subsystem for Linux (WSL).

## Installation

1. Clone the repository and navigate into the root directory:
   ```bash
   git clone <repository-url>
   cd AI-Model
   
2.Create and activate a Python virtual environment:
   ```bash
   python3 -m venv venv
   source venv/bin/activate
