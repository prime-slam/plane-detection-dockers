FROM ubuntu:18.04

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update
RUN apt-get install -y cmake pkg-config libeigen3-dev libopencv-dev libboost-all-dev


ADD ./CAPE /app/src

WORKDIR /app/build

RUN cmake ../src && make


ENTRYPOINT ["./cape_offline"]