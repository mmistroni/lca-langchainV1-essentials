FROM mcr.microsoft.com/devcontainers/python:3.11-bookworm

ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

WORKDIR /workspace

# Copy the requirements file from the python directory
COPY python/requirements.txt ./python/

# Create the virtual environment, upgrade pip/jupyter, and install requirements
RUN python -m venv /opt/venv && \
    . /opt/venv/bin/activate && \
    pip install --no-cache-dir --upgrade pip jupyter ipykernel && \
    if [ -f python/requirements.txt ]; then pip install --no-cache-dir -r python/requirements.txt; fi

ENV PATH="/opt/venv/bin:$PATH"