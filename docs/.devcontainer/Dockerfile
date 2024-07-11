# Use an official Python runtime as a parent image
ARG VARIANT=slim

FROM python:${VARIANT}

RUN apt-get update && apt-get install -y \
    git \
    && rm -rf /var/lib/apt/lists/*

RUN useradd --create-home mkdocs
USER mkdocs
ENV PATH /home/mkdocsuser/.local/bin:$PATH

WORKDIR /workspace


RUN python -m pip install --upgrade pip \
    && pip install mkdocs

EXPOSE 8000


CMD ["mkdocs", "serve", "-a", "0.0.0.0:8000"]
