###########################################################
# Dockerfile to build star container images
# Based on Ubuntu
############################################################

# Set the base image to Ubuntu
FROM ubuntu:latest

# File Author / Maintainer
MAINTAINER Costas Bouyioukos <costas.bouyioukos@univ-paris-diderot.fr>

# Update the repository sources list
RUN apt-get update
RUN apt-get upgrade

# Install compiler, git etc.
RUN apt-get install --yes \
  build-essential \
  gcc-multilib \
  apt-utils \
  zlib1g-dev \
  git

# Install STAR
WORKDIR /usr/local/STAR/
RUN git clone https://github.com/alexdobin/STAR.git
RUN git checkout 2.5.3a
WORKDIR /usr/local/STAR 
RUN make STAR
ENV PATH /usr/local/STAR/source:$PATH
