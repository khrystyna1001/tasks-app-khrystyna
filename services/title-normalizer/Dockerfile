FROM python:3.12-slim@sha256:4840d514c583a4d3d8cad3940e68dee6f0f6f3635c12fcd0a3d74c21a5b93a54
RUN apt-get update && apt-get upgrade -y && rm -rf /var/lib/apt/lists/*
RUN groupadd -g 1234 customgroup; \
    useradd -m -u 1234 -g customgroup user

WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY . .
USER user
EXPOSE 5001
CMD ["flask", "--app", "app:create_app", "run", "--host", "0.0.0.0", "--port", "5001"]
