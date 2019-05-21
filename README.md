# PyTango conda recipe for windows

Temporary repo with a conda recipe to build PyTango conda package on windows.

It is based on the wheel files from pypi, not a source build (that is why it is temporary).


```bash
# prepare a clean conda environment (ex: pytango-build)
# remember you can use the same conda environment to build 
# to multiple python versions because conda build will setup 
# its own isolated environment.
conda create -n pytango-build

# enter environment
conda activate pytango-build

# install conda build
conda install conda-build conda-verify

# to upload to anaconda cloud you also need:
conda install anaconda-client
anaconda login

# clone this repository, enter main repo directory 

# conda build
conda build --python=3.7 pytango

# ...there will be a message saying something like:
# # Automatic uploading is disabled
# # If you want to upload package(s) to anaconda.org later, type:
# anaconda upload C:\ProgramData\Miniconda3\envs\pytango-build\conda-bld\win-64\pytango-9.3.1.dev1-py37h39e3cac_1.tar.bz2

# to upload to anaconda select your channel (official is tango-controls):
anaconda upload -u <channel> <previous filename>
```