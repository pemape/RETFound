# Fundus Inference Server - Flask API Docker Image
FROM python:3.11-slim-bookworm

# Install system dependencies for image processing
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    curl \
    libgl1

# Copy requirements and install dependencies
COPY requirements.txt .
RUN pip install --upgrade pip setuptools wheel && \
    pip install --no-cache-dir torch==2.5.1 torchvision==0.20.1 --index-url https://download.pytorch.org/whl/cu124 && \
    pip install --no-cache-dir -r requirements.txt && \
    pip install ipykernel && \
    python -m ipykernel install --user --name retfound --display-name "Python (retfound)"

COPY . .