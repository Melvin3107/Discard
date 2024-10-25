# Dockerfile

# Usar la imagen base de Python
FROM python:3.8-slim

# Establecer el directorio de trabajo
WORKDIR /app

# Instalar las dependencias del sistema necesarias
RUN apt-get update && apt-get install -y \
    python3-dev \
    libjpeg-dev \
    libfreetype6-dev \
    libpq-dev \
    gcc \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Copiar los archivos de requisitos
COPY dependencias.txt .

# Instalar las dependencias de Python
RUN pip install --no-cache-dir -r dependencias.txt

# Copiar el código de la aplicación
COPY . .

# Exponer el puerto
EXPOSE 8032

# Comando para ejecutar el servidor de desarrollo de Django
CMD ["python", "manage.py", "runserver", "0.0.0.0:8032"]
