###########################################################
# Dockerfile to build star container images
# Based on Ubuntu
############################################################

# Set the base image to Ubuntu
FROM ubuntu:16.04

# File Author / Maintainer
MAINTAINER Costas Bouyioukos <costas,.bouyioukos@univ-paris-diderot.fr>

# Update the repository sources list
RUN apt-get update

# Install compiler and perl stuff
RUN apt-get install --yes \
  build-essential \
  gcc-multilib \
  apt-utils \
  zlib1g-dev \
  vim-common

# Install git
RUN apt-get install -y git

# Install STAR
WORKDIR /usr/local/
RUN pwd
RUN git clone https://github.com/alexdobin/STAR.git
WORKDIR /usr/local/STAR/
RUN pwd
RUN git checkout 2.5.3a 
WORKDIR /usr/local/STAR 
RUN pwd
RUN make STAR
ENV PATH /usr/local/STAR/source:$PATH
