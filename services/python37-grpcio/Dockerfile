FROM python:3.7-slim-buster

WORKDIR /usr/build

RUN sed -i "s#deb http://deb.debian.org/debian buster main#deb http://deb.debian.org/debian buster main contrib non-free#g" /etc/apt/sources.list \
	&& apt-get update && apt-get install -y --no-install-recommends \
	wget git gcc g++ python3-dev \
	&& apt-get clean \
	&& rm -rf /var/lib/apt/lists/*

RUN wget https://www.piwheels.org/simple/grpcio/grpcio-1.32.0-cp37-cp37m-linux_armv7l.whl && pip3 install grpcio-1.32.0-cp37-cp37m-linux_armv7l.whl

RUN pip3 list

#RUN echo '[global]' > /etc/pip.conf \
#    && echo 'extra-index-url=https://www.piwheels.org/simple' >> /etc/pip.conf
#RUN cat /etc/pip.conf
#RUN pip3 install grpcio
#RUN export REPO_ROOT=grpc \
#    && git clone -b v1.32.0 https://github.com/grpc/grpc $REPO_ROOT \
#    && cd $REPO_ROOT \
#    && git submodule update --init \
#    && pip install -r requirements.txt \
#    && GRPC_PYTHON_BUILD_WITH_CYTHON=1 pip install .

#RUN git clone -b v1.32.0 https://github.com/grpc/grpc $REPO_ROOT
#RUN pwd
#RUN ls -l
#RUN cd $REPO_ROOT && pwd
#RUN cd $REPO_ROOT \
#    && git submodule update --init \
#    && pip install -r requirements.txt \
#    && GRPC_PYTHON_BUILD_WITH_CYTHON=1 pip install .

