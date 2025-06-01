FROM n8nio/n8n:latest

USER root

# Instalar Tesseract y curl
RUN apk add --no-cache tesseract-ocr curl

# Descargar archivos de idioma necesarios
RUN mkdir -p /usr/share/tessdata && \
    cd /usr/share/tessdata && \
    curl -L -O https://github.com/tesseract-ocr/tessdata/raw/main/eng.traineddata && \
    curl -L -O https://github.com/tesseract-ocr/tessdata/raw/main/spa.traineddata && \
    curl -L -O https://github.com/tesseract-ocr/tessdata/raw/main/osd.traineddata

# Configurar la variable de entorno
ENV TESSDATA_PREFIX=/usr/share/tessdata

USER node