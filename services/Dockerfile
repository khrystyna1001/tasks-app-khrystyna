FROM python:13.2-slim

WORKDIR /app

RUN pip -r install /tasks-api/requirements.txt && \
    pip -r install /title-normalizer/requirements.txt

RUN flask --app tasks-api/app:create_app run --port 5001