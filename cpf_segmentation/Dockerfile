FROM ubuntu:18.04

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y python3-pip git

RUN python3 -m pip install --user git+https://github.com/DanielPollithy/pypcd.git

RUN apt-get update && apt-get install -y cmake pkg-config libeigen3-dev libopencv-dev libpcl-dev

ADD ./src /app/src/src

ADD ./gco-v3.0 /app/src/gco-v3.0

ADD ./include /app/src/include

ADD CMakeLists.txt /app/src

WORKDIR /app/build

RUN cmake ../src && make && make install

ADD scripts/ .

ENTRYPOINT ["bash", "run.sh"]