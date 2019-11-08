FROM spack/ubuntu-bionic

RUN apt-get -yqq update             \
 && apt-get -yqq install            \
        clang-6.0                   \
        gcc-6                       \
        gfortran-6                  \
        g++-6                       \
        python3-pip                 \
 && pip3 install boto3              \
 && rm -rf /var/lib/apt/lists/*

RUN spack compiler find && \
    spack install gcc@8.3.0

COPY config/compilers.yaml /root/.spack/linux/compilers.yaml

