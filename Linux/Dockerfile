# Use uma imagem base oficial do Python
FROM python:3.11-slim

# Defina variáveis de ambiente para o Python
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# Crie e defina o diretório de trabalho
WORKDIR /app

# Copie o arquivo requirements.txt
#COPY requirements.txt /app/

# Instale dependências do sistema operacional necessárias
RUN apt-get update && apt-get install -y \
    build-essential \
    libssl-dev \
    libffi-dev \
    python3-dev \
    curl \
    git \
    vim \
    nano \
    && rm -rf /var/lib/apt/lists/*

# Instale as dependências do Python
RUN pip install --upgrade pip && pip install -r requirements.txt

# Copie o restante do código do projeto
COPY . /app

# Exponha a porta que seu aplicativo vai rodar
EXPOSE 8000

# Comando padrão para rodar o container
CMD ["python", "main.py"]


