FROM python:3.12-slim

ENV NORMALIZER_URL=http://title-normalizer:5001

WORKDIR /app

COPY requirements.txt .

RUN pip install -r requirements.txt

COPY . .

EXPOSE 5000

CMD ["flask", "--app", "app:create_app", "run", "--host", "0.0.0.0", "--port", "5000"]