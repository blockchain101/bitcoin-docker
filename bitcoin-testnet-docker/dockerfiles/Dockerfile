# bitcoin-testnet docker image

# Ubuntu 16.04 LTS (xenial)
FROM ubuntu:16.04
MAINTAINER Peng Zhuang <zhuangpeng0514@sina.com>

# add bitcoind from the official PPA
RUN apt-get update
RUN apt-get install --yes software-properties-common
RUN add-apt-repository --yes ppa:bitcoin/bitcoin
RUN apt-get update

# install bitcoind (from PPA)
RUN apt-get install --yes bitcoind

# install ping, netstat tools
RUN apt-get install --yes iputils-ping net-tools

# install make
RUN apt-get install --yes make

# copy the bitcoin-testnet resource files into the image
ADD bitcoin-testnet.tar /bitcoin-testnet

# change to work directory
WORKDIR /bitcoin-testnet/init-network

# initialize bitcoin config peer num=4 00~03 00 as bootnode
RUN bash ./init-bitcoin-testnet.bash ./bitcoindata 4 Y Y 127.0.0.1

# change to work directory
WORKDIR /bitcoin-testnet










