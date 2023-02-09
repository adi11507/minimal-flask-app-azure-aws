FROM python:3.11.2-slim-buster

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install --no-install-recommends -y && apt clean && rm -rf /var/lib/apt/lists/*

# Install python dependencies
COPY requirements.txt .
RUN python3 -m pip install --upgrade pip && pip install --no-cache-dir --upgrade -r requirements.txt

WORKDIR /usr/src/app
COPY . /usr/src/app

ENTRYPOINT python3 server.py
