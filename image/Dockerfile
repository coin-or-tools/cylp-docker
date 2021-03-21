FROM ubuntu:latest
ARG DEBIAN_FRONTEND="noninteractive"
ENV TZ="America/New_York"
RUN apt-get -y install unzip git gcc g++ gfortran make wget file pkg-config
RUN apt-get -y install python3 python3-pip 
RUN apt-get -y install libblas-dev liblapack-dev
RUN git clone https://github.com/coin-or/coinbrew /var/cbc
WORKDIR /var/cbc
RUN ./coinbrew fetch Cbc@stable/2.10 --no-prompt --no-third-party
RUN ./coinbrew build Cbc --no-prompt --no-third-party --prefix=/usr
ENV COIN_INSTALL_DIR /usr
RUN pip3 install numpy
RUN git clone https://github.com/coin-or/CyLP
WORKDIR CyLP
RUN pip3 install .
