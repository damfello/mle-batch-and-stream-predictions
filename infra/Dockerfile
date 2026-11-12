FROM ghcr.io/astral-sh/uv:0.13.5 AS uv
FROM python:3.13.17-slim-bookworm

ARG PACKAGES="mlflow==3.17.2 psycopg2-binary==2.9.13"

COPY --from=uv /uv /bin/uv
RUN apt-get update \
    && apt-get install -y --no-install-recommends ca-certificates \
    && rm -rf /var/lib/apt/lists/*
RUN uv pip install --system --upgrade "pip>=26.2.2" "certifi>=2026.10.19" ${PACKAGES}
