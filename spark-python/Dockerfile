FROM gcr.io/hybrid-qubole/spark

# installing apt-get
RUN cat /etc/os-release

RUN apk add --update \
    python3 \
    python-dev \
    py-pip \
    build-base \
  && pip install virtualenv \
  && rm -rf /var/cache/apk/*
  
RUN unlink /usr/bin/python && ln -s /usr/bin/python3 /usr/bin/python
  
RUN pip install pyspark
RUN python --version
