FROM ubuntu:18.04

RUN apt update -y \
  && apt upgrade -y \
  && apt install -y \
  git \
  gcc \
  g++ \
  gfortran \ 
  patch \
  bzip2 \
  findutils \
  automake \
  autoconf \
  make \
  m4 \
  unzip \
  vim \
  file \
  wget \
  curl \
  mercurial \
  cpio \
  gpg \
  zlib1g-dev \
  libffi-dev \
  libssl-dev \
  libxml2-dev \
  rsync \
  locate \
  pciutils \
  iputils-ping \
  iproute2 \
  emacs \
  gcc-6 \
  clang-6.0 \
  ncurses-dev \
  sudo \
  python3-pip \
  && python3 -m pip install --upgrade pip setuptools wheel \
  && python3 -m pip install --upgrade gnureadline \
  && apt autoremove --purge && apt clean \
  && ln -s /usr/bin/gpg /usr/bin/gpg2

COPY /build_cache /mirror/build_cache
COPY /public.key /mirror
COPY /packages.yaml /etc/spack/packages.yaml
COPY /tutorial-test.sh /tutorial/.test/tutorial-test.sh

RUN useradd -ms /bin/bash spack \
 && chmod -R go+r /mirror \
 && chmod -R go+r /etc/spack \
 && chmod go+r /tutorial/.test/tutorial-test.sh
