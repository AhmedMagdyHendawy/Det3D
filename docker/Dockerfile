FROM nvidia/cuda:10.1-cudnn7-devel-ubuntu18.04
ARG PYTHON_VERSION=3.6
RUN apt-get update && apt-get install -y --no-install-recommends \
         build-essential \
         cmake \
         git \
         curl \
         vim \
         ca-certificates \
         libjpeg-dev \
         libpng-dev &&\
     rm -rf /var/lib/apt/lists/*

RUN apt-get update && apt-get install -y python3.6 && apt install -y python3-pip

RUN pip3 install ninja

RUN pip3 install torch torchvision

RUN echo 'alias python=python3' >> ~/.bashrc && echo 'alias pip=pip3' >> ~/.bashrc 

RUN /bin/bash -c "source ~/.bashrc"









