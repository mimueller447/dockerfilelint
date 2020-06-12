FROM ubuntu:18.04
COPY . /app
RUN apt-get update && apt-get install --no-install-recommends -y \
    dpkg-sig=1.2.3 \
    automake=2.2 \
    s3cmd=1.1.* \
    && rm -rf /var/lib/apt/lists/*
CMD ["python", "/app/app.py"]
HEALTHCHECK CMD curl -f http://localhost --interval=5m --timeout=3s 
