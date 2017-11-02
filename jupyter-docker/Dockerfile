FROM ubuntu:16.04
MAINTAINER tudor.lapusan@gmail.com

RUN apt-get clean && apt-get update
RUN apt-get -y install python-dev \
	python-pip \
	wget \
	default-jdk
RUN pip install --upgrade pip
RUN pip install jupyter \
	findspark
RUN mkdir /jupyter
WORKDIR /jupyter
RUN mkdir spark && mkdir notebooks
WORKDIR /jupyter/spark

RUN wget http://mirror.evowise.com/apache/spark/spark-2.2.0/spark-2.2.0-bin-hadoop2.7.tgz
RUN tar -xvf spark-2.2.0-bin-hadoop2.7.tgz && rm spark-2.2.0-bin-hadoop2.7.tgz
ENV SPARK_HOME /jupyter/spark/spark-2.2.0-bin-hadoop2.7/

WORKDIR /jupyter/notebooks

CMD jupyter notebook --ip 0.0.0.0 --allow-root
