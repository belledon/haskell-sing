BootStrap: docker
From: haskell:latest

%runscript
    echo "SINGULARITY RUNSCRIPT"
    echo "Arguments received: $*"

%post
    echo "Hello from inside the container"

    export LC_ALL=C
    export PATH=/bin:/sbin:/usr/bin:/usr/sbin:$PATH

    # add universe repo and install some packages
    sed -i '/xenial.*universe/s/^#//g' /etc/apt/sources.list
    apt-get -y update && apt-get -y install wget
    apt-get -y install locales
    apt-get -y install git
    apt-get -y install cmake
    apt-get -y install g++
    apt-get update
    apt-get clean
    locale-gen en_US.UTF-8
    