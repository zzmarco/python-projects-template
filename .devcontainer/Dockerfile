ARG PYTHON_VERSION=3.13
FROM python:${PYTHON_VERSION}

COPY requirements.txt /tmp/requirements.txt
COPY requirements-dev.txt /tmp/requirements-dev.txt

RUN pip install -U pip && \
    if [ -s /tmp/requirements.txt ]; then pip install --no-cache-dir -r /tmp/requirements.txt; fi && \
    if [ -s /tmp/requirements-dev.txt ]; then pip install --no-cache-dir -r /tmp/requirements-dev.txt; fi