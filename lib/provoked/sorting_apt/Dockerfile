FROM ubuntu:18.04
COPY . /app
RUN apt-get update && apt-get install --no-install-recommends -y \
    dpkg-sig=1.2.3 \
    automake=2.2 \
    libcap-dev=2.111 \
    curl=3.2.5 \
    mercurial=3.5 \
    reprepro=2 \
    build-essential=4.54 \
    s3cmd=1.1.* \
    && rm -rf /var/lib/apt/lists/*
CMD ["python", "/app/app.py"]
