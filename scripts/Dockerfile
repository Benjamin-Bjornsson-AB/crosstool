FROM ubuntu:20.04

# Non-interactive frontend for apt-get
ENV DEBIAN_FRONTEND=noninteractive

# Update package lists
RUN apt-get update

# Install any needed packages
RUN apt-get install -y autoconf
RUN apt-get install -y automake
RUN apt-get install -y bison
RUN apt-get install -y bzip2
RUN apt-get install -y cmake
RUN apt-get install -y flex
RUN apt-get install -y g++
RUN apt-get install -y gawk
RUN apt-get install -y gcc
RUN apt-get install -y gettext
RUN apt-get install -y git
RUN apt-get install -y gperf
RUN apt-get install -y help2man
RUN apt-get install -y libncurses5-dev
RUN apt-get install -y libstdc++6
RUN apt-get install -y libtool
RUN apt-get install -y libtool-bin
RUN apt-get install -y make
RUN apt-get install -y patch
RUN apt-get install -y python3-dev
RUN apt-get install -y rsync
RUN apt-get install -y texinfo
RUN apt-get install -y unzip
RUN apt-get install -y wget
RUN apt-get install -y xz-utils

RUN git clone https://github.com/crosstool-ng/crosstool-ng.git /opt/crosstool-ng
WORKDIR /opt/crosstool-ng
RUN git checkout crosstool-ng-1.26.0

WORKDIR /opt/crosstool-ng
RUN ./bootstrap
RUN ./configure --prefix=/usr/local
RUN make
RUN make install

RUN useradd -m -s /bin/bash ctuser
USER ctuser

RUN mkdir /home/ctuser/toolchain
WORKDIR /home/ctuser/toolchain

CMD ["/bin/bash"]

