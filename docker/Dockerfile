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

RUN pip3 install torch==1.3.0 torchvision

RUN update-alternatives --install /usr/bin/python python /usr/bin/python3 1
RUN update-alternatives --install /usr/bin/pip pip /usr/bin/pip3 1

RUN cd /

RUN apt install libssl-dev -y
RUN apt remove cmake cmake-data -y
RUN git clone https://github.com/Kitware/CMake.git && cd CMake && git checkout v3.16.3 && \
 chmod +x bootstrap && ./bootstrap --prefix=/usr && make && make install

Run cd /

RUN git clone https://github.com/NVIDIA/apex && cd apex && pip install -v --no-cache-dir --global-option="--cpp_ext" --global-option="--cuda_ext" ./

RUN cd /

RUN apt-get install -y libboost-all-dev
RUN git clone https://github.com/traveller59/spconv.git --recursive && cd spconv && git checkout 7342772 && python setup.py bdist_wheel && cd ./dist && pip install *

RUN cd /

RUN apt-get install -y python-setuptools
RUN pip install pytest && pip install flake8 && pip install pygments && git clone https://github.com/poodarchu/nuscenes.git && cd nuscenes && python setup.py install

RUN cd /

RUN pip install Cython && pip install pyyaml
RUN git clone https://github.com/poodarchu/Det3D.git && cd Det3D && python setup.py build develop

RUN cd /





