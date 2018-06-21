#######################################################################
# Dockerfile to build the FastQC 0.11.7 image
# Based on Ubuntu
# Installation instructions from 
# http://www.bioinformatics.babraham.ac.uk/projects/download.html#fastqc
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
  openjdk-7-jre \
  perl \
  unzip

# Download FastQC
ADD http://www.bioinformatics.babraham.ac.uk/projects/fastqc/fastqc_v0.11.7.zip /tmp/

# Install FastQC
RUN cd /usr/local && \
    unzip /tmp/fastqc_*.zip && \
    chmod 755 /usr/local/FastQC/fastqc && \
    ln -s /usr/local/FastQC/fastqc /usr/local/bin/fastqc && \
    rm -rf /tmp/fastqc_*.zip

ENTRYPOINT ["fastqc"]
