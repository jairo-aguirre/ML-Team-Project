# Use a modern slim Python image
FROM python:3.11-slim-bookworm

# Install system packages needed by psycopg2
RUN apt-get update \
    && apt-get install -y gcc libpq-dev \
    && rm -rf /var/lib/apt/lists/*

# Copy Python dependencies and install
COPY requirements.txt /tmp/
RUN pip install --no-cache-dir -r /tmp/requirements.txt

# Set the working directory inside the container
WORKDIR /app

# Default command (can still be overridden in docker-compose)
CMD ["mlflow", "server"]

