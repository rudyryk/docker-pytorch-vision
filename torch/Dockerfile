FROM python:3.8.7-slim

ENV PATH=/opt/conda/bin:$PATH \
    DEBIAN_FRONTEND=noninteractive

ADD pyproject.toml poetry.toml poetry.lock /opt/

RUN cd /opt && \
    pip install poetry && \
    poetry install && \
    pip install \
        torch==1.7.1+cu110 \
        torchvision==0.8.2+cu110 \
        -f https://download.pytorch.org/whl/torch_stable.html && \
    rm -rf ~/.cache
