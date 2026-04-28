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

2. **Create TPU instance**:
   ```bash
   gcloud alpha compute tpus queued-resources create gemma4-tpu-vllm \
     --zone=southamerica-east1-c \
     --accelerator-type=v6e-8 \
     --runtime-version=v2-alpha-tpuv6e \
     --node-id=gemma4-tpu-vllm \
     --provisioning-model=flex-start \
     --max-run-duration=4h \
     --valid-until-duration=4h \
     --labels=purpose=flex-start
   ```
   
3. **Check TPU status**:

After creating the TPU instance, check the status with the following command:
```bash
gcloud alpha compute tpus queued-resources describe \
  gemma4-tpu-vllm \
  --zone=southamerica-east1-c
```

4. **Run inference**:
Clone the repository on your local machine, and run the frontend server.
- Run `py -m http.server` to start the server.
- Open `localhost:8000` on your web browser and inference Gemma 4 26B-A4B-it model on TPU using vLLM.

## Results

<img src="https://github.com/NSTiwari/Gemma-4-on-TPU/blob/main/tpu_sprint.gif">


## Acknowledgment:
<img src="https://github.com/NSTiwari/Gemma-4-on-TPU/blob/main/google-logo.png">
