#######################################################################
# Dockerfile to build the latest MultiQC container images
# Based on Ubuntu
# Installation instructions from 
# http://multiqc.info/docs/#installing-multiqc
#######################################################################

# Set the base image to Ubuntu
FROM ubuntu:latest

# File Author / Maintainer
MAINTAINER Costas Bouyioukos <costas.bouyioukos@univ-paris-diderot.fr>

# Update the repository sources list
RUN apt-get update
RUN apt-get upgrade --yes

# Install pip and required libraries
RUN apt-get install --yes \
  python-pip \
  build-essential \
  python-dev

# Install cutadapt
RUN pip install multiqc

# Clean
RUN apt-get remove --yes --purge build-essential ; apt-get autoclean; apt-get autoremove --yes

