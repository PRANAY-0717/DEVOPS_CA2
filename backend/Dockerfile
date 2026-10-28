FROM python:3.11-slim

RUN groupadd -r appuser && useradd -r -g appuser appuser

WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY app.py .
RUN chown -R appuser:appuser /app

ARG APP_VERSION=dev
ENV APP_VERSION=${APP_VERSION}

USER appuser
CMD ["python", "app.py"]