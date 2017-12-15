BootStrap: docker
From: haskell:latest

%runscript
    echo "SINGULARITY RUNSCRIPT"
    echo "Arguments received: $*"

%post
    echo "Hello from inside the container"

    apt-get update && apt-get -y install locales
    locale-gen en_US.UTF-8
    apt-get -y install wget git cmake g++ cabal-install
    apt-get clean
    cabal update
    
    cd / && mkdir repo && cd repo
    git clone https://github.com/mightybyte/monad-challenges.git
    cd monad-challenges
    cabal install

%test
    cabal --version 
