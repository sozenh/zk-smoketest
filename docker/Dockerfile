FROM python:2.7-slim

RUN sed -i 's|http://deb.debian.org/debian|http://mirrors.aliyun.com/debian|g' /etc/apt/sources.list && \
    apt-get update && \
    apt-get install -y --no-install-recommends build-essential wget unzip libzookeeper-mt-dev gcc && \
    rm -rf /var/lib/apt/lists/*

RUN pip install zkpython

RUN wget https://github.com/phunt/zk-smoketest/archive/master.zip -O zk-smoketest.zip; \
    unzip zk-smoketest.zip; \
    rm zk-smoketest.zip

EXPOSE 2181

ENTRYPOINT ["zk-smoketest-master/zk-latencies.py"]
