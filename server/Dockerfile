FROM python:3.12-slim

WORKDIR /app

RUN mkdir -p /app/log

# 设置 pip 国内源（清华源）
RUN pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple

COPY mem0ai-0.1.111-py3-none-any.whl .
COPY main.py .

# 安装本地 whl 文件
RUN pip install --no-cache-dir mem0ai-0.1.111-py3-none-any.whl

COPY requirements.txt .

# 安装依赖
RUN pip install --no-cache-dir -r requirements.txt

COPY . .


EXPOSE 8000

ENV PYTHONUNBUFFERED=1

CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000", "--reload"]