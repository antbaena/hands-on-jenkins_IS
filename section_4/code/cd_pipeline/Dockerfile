FROM alpine:3.15

# Instalamos python3 y pip
RUN apk add --update python3 py3-pip

# Copiamos el archivo de requisitos
COPY requirements.txt /usr/src/app/

# --- AÑADE ESTA LÍNEA AQUÍ ---
# Actualizamos pip para evitar el error de "toml decoder"
RUN pip3 install --upgrade pip
# -----------------------------

# Ahora sí instalamos las librerías
RUN pip3 install --no-cache-dir -r /usr/src/app/requirements.txt

COPY app.py /usr/src/app/
COPY templates/index.html /usr/src/app/templates/

EXPOSE 5000

CMD ["python3", "/usr/src/app/app.py"]
