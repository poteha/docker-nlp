FROM nvidia/cuda:10.0-cudnn7-devel-ubuntu16.04

ENV LANG=C.UTF-8

RUN apt-get update -y && apt-get install -y \
    git \
    wget \
    curl \
    cmake \
    unzip \
    software-properties-common \
    unixodbc-dev \
    gcc \
    g++

# Install python
RUN add-apt-repository -y ppa:jonathonf/python-3.6 \
    && apt-get update -y \
    && apt-get install -y python3.6 python3.6-dev \
    && ln -sfn /usr/bin/python3.6 /usr/local/bin/python \
    && ln -sfn /usr/bin/python3.6 /usr/bin/python3 \
    && curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py \
    && python get-pip.py \
    && rm get-pip.py \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN pip install torch==0.4.1
RUN pip install flair==0.3.2
RUN pip install spacy==2.0.11

RUN pip install \
    dateparser==0.7.0 \
    pymorphy2==0.8 \
    yargy==0.11.0 \
    natasha==0.10.0 \
    nltk==3.2.1 \
    yake==0.3.7 \
    python-dateutil==2.7.5

RUN python -m nltk.downloader stopwords && python -m nltk.downloader punkt  && \
    python -m nltk.downloader averaged_perceptron_tagger

RUN python -c 'import flair; _ = flair.models.SequenceTagger.load("ner-fast")'

CMD mkdir src
WORKDIR src