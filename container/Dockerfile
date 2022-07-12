FROM ubuntu:16.04

MAINTAINER vitordgfreitas

RUN apt-get -y update && apt-get install -y --no-install-recommends \
         wget \
         python3 \
         nginx \
         ca-certificates \
    && rm -rf /var/lib/apt/lists/*

RUN wget https://bootstrap.pypa.io/get-pip.py && python3 get-pip.py && \
    pip install numpy scipy==1.1.0 scikit-learn==0.19.1 pandas nltk xlrd flask gevent gunicorn && \
        rm -rf /root/.cache

ENV PYTHONUNBUFFERED=TRUE
ENV PYTHONDONTWRITEBYTECODE=TRUE
ENV PATH="/opt/program:${PATH}"

COPY iris_model /opt/program
WORKDIR /opt/program
