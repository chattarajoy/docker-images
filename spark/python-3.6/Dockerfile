FROM gcr.io/hybrid-qubole/spark:minio

ENV PATH /usr/local/bin:$PATH

# http://bugs.python.org/issue19846
# > At the moment, setting "LANG=C" on a Linux system *fundamentally breaks Python 3*, and that's not OK.
ENV LANG C.UTF-8

ENV PYTHON_VERSION 3.6.7

RUN apt-get -y install build-essential checkinstall libssl-dev openssl libreadline-gplv2-dev libncursesw5-dev libssl-dev libsqlite3-dev tk-dev libgdbm-dev libc6-dev libbz2-dev && \ 
	wget https://www.python.org/ftp/python/${PYTHON_VERSION}/Python-${PYTHON_VERSION}.tgz && \
	tar xzvf Python-${PYTHON_VERSION}.tgz && \
	cd Python-${PYTHON_VERSION} &&\
	./configure && \
	make && \
	make install && \
	apt-get install -y python3-pip


RUN ln -s /usr/bin/pip3 /usr/bin/pip
RUN pip install pyspark
