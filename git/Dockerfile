# Define the base image
FROM ubuntu:13.04

# Update package lists
RUN apt-get update && apt-get upgrade -y

# Install dependencies for compiling git
RUN apt-get install -y curl wget build-essential libssl-dev libcurl4-openssl-dev zlib1g-dev perl git-core

# Download a recent git version (e.g., 2.39.0)
RUN wget https://mirrors.edge.kernel.org/pub/software/scm/git/git-1.8.3.1.tar.xz

# Extract the archive
RUN tar -xvf git-1.8.3.1.tar.xz

# Compile and install git
RUN cd git-1.8.3.1 && ./configure --prefix=/usr/local && make && make install

# Set git version (optional, but recommended)
RUN echo 'export PATH=/usr/local/bin:$PATH' >> ~/.bashrc

# Download Cribl LogStream 4.5.1
RUN wget https://downloads.cribl.io/cribl-logstream/4.5.1/cribl-logstream-4.5.1-linux.x86_64.deb

# Install Cribl LogStream
RUN dpkg -i cribl-logstream-4.5.1-linux.x86_64.deb

# Start Cribl LogStream as master
RUN cribl master &

# Keep the container running
CMD tail -f /dev/null
