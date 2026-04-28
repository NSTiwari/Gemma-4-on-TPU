# Gemma 4 on TPU
This repository is a step-by-step tutorial on serving and inferencing Gemma 4 26B-4B-it model on Google Cloud TPU for tasks like advanced reasoning, zero-shot object detection, OCR, and visual question-answering with seconds to sub-second response time.

## Prerequisites

Before starting, make sure you have the following:

- A Google Cloud Platform account and a linked billing account.
- GCP Project with a quota for TPU instances.
- A Hugging Face (HF) token for model access.

## Setup Instructions

1. **Set up environment variables**:

   Replace `YOUR_GCP_PROJECT_NAME` and `YOUR_HF_TOKEN` with your actual GCP project name and Hugging Face token.

   ```bash
   export PROJECT=YOUR_GCP_PROJECT_NAME
   export HF_TOKEN=YOUR_HF_TOKEN
   export ZONE=southamerica-east1-c
   export TPU_NAME=gemma4-tpu-vllm
   ```
