FROM python:3.12-slim

WORKDIR /app

COPY mem0ai-0.1.111-py3-none-any.whl .
COPY main.py .

RUN pip install mem0ai-0.1.111-py3-none-any.whl

COPY requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 8000

ENV PYTHONUNBUFFERED=1

CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000", "--reload"]
