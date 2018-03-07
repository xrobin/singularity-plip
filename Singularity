BootStrap: docker
From: ubuntu:16.04

%post
    # install some system deps
    apt-get -y update
    apt-get -y install locales
    locale-gen en_US.UTF-8
    # apt-get -y install python-future python-numpy python-lxml pymol python-openbabel git
    apt-get -y install python-future python-numpy python-lxml pymol git
    # For OpenBabel:
    apt-get -y install cmake build-essential libxml2 libxml2-dev libeigen3-dev zlib1g-dev wget python-dev
    apt-get clean

    if [ -d /opt/pliptool ]; then rm -rf /opt/pliptool; fi
    git clone https://github.com/ssalentin/plip.git /opt/pliptool


    if [ -d openbabel ]; then rm -rf openbabel; fi
    mkdir openbabel
    cd openbabel
    wget https://sourceforge.net/projects/openbabel/files/openbabel/2.4.1/openbabel-2.4.1.tar.gz
    tar -xf openbabel-2.4.1.tar.gz
    cd openbabel-2.4.1
    mkdir build
    cd build
    cmake .. -DPYTHON_BINDINGS=ON 
    make
    make install

%runscript

   exec /opt/pliptool/plip/plipcmd "$@"

   #"I can put here whatever I want to happen by default when the user runs the container"
   #cat << EOF
#This container includes the following apps:
#PyMOL 1.7.2.1 - https://pymol.org
#      --app PyMOL or --app pymol ...
#OpenBabel 2.3.2 - http://openbabel.org
#      -- app OpenBabel or --app obabel ...
#PLIP 1.4.0 (git) - https://github.com/ssalentin/plip
#      -- app PLIP or --app plip
#EOF

%environment
    export PYTHONPATH=/opt/pliptool/plip

#%apprun plip
#	exec /opt/pliptool/plip/plipcmd "$@"

#%apprun PLIP
#	exec ~/pliptool/plip/plipcmd "$@"

#%apprun openbabel
#	exec /usr/bin/obabel "$@"

#%apprun OpenBabel
#	exec /usr/bin/obabel "$@"

#%apprun pymol
#	exec /usr/bin/pymol "$@"

#%apprun PyMOL
#	exec /usr/bin/pymol "$@"
