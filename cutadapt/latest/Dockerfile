#######################################################################
# Dockerfile to build the latest Cutadapt container images
# Based on Ubuntu
# Installation instructions from 
# https://cutadapt.readthedocs.io/en/stable/installation.html
#######################################################################

# Set the base image to Ubuntu
FROM ubuntu:latest

# File Author / Maintainer
MAINTAINER Costas Bouyioukos <costas.bouyioukos@univ-paris-diderot.fr>

# Update the repository sources list
RUN apt-get update
RUN apt-get upgrade --yes

# Install pip and cutadapt required libraries
RUN apt-get install --yes \
  python3-pip \
  build-essential \
  python-dev

# Install cutadapt
RUN pip3 install cutadapt
RUN cp .local/bin/cutadapt /usr/local/sbin/

# Clean
RUN apt-get remove --yes --purge build-essential ; apt-get autoclean; apt-get autoremove --yes

