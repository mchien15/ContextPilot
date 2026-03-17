FROM python:3.12-slim

COPY . /opt/contextpilot
WORKDIR /opt/contextpilot

RUN pip install --no-cache-dir .

ENV CONTEXTPILOT_PORT=8765
EXPOSE 8765

COPY docker/entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh

RUN apt-get update && apt-get install -y --no-install-recommends \
    curl \
    && rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["/entrypoint.sh"]
