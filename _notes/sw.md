---
layout: note
title: Home Directory Installed Software
---


## Directories for Everything

* `src` for all source code
* `sw` or whatever directory you want to hold everything
* Within `sw` these directories:
  - `bin`, `include`, `lib/pkgconfig`, `man`, `share/{man,info}`

## bashrc

'''
# pkg-config setup (OS X it is not default installed)
export PKG_CONFIG_PATH="/usr/local/lib/pkgconfig:/usr/local/lib:/usr/lib/pkgconfig"

# "sw" directory
export PATH="${HOME}/sw/bin:${PATH}"
export MANPATH="${HOME}/sw/man:${HOME}/sw/share/man:${MANPATH}"
export INFOPATH="${HOME}/sw/info:${HOME}/sw/share/info:${INFOPATH}"
export PKG_CONFIG_PATH="${HOME}/sw/lib/pkgconfig:${PKG_CONFIG_PATH}"
export LD_LIBRARY_PATH="${HOME}/sw/lib"
'''

# Building/Installing Software

## Build/Install CMake (you'll probably need it)

* [Download CMake source](https://cmake.org/download/)
* Unpack in `src` directory: `tar -xvf cmake-3.5.1.tar.gz`
* `cd cmake-3.5.1`
* `./bootstrap --prefix="${HOME}/sw" && make && make install`

## Build/Install pkg-config

* [Download pkg-config source](https://pkg-config.freedesktop.org/releases/)
* Unpack in `src` directory: `tar -xvf pkg-config-0.29.1.tar.gz`
* `cd pkg-config-0.29.1`
* `./configure --prefix="${HOME}/sw" --with-internal-glib`
* If you haven't already done so, update your PKG_CONFIG_PATH as mentioned above

# Building/Installing with CMake

Building with CMake is best done as an "out of tree build", which means build in a separate directory. If something goes wrong, just remove the build directory and start again.

## GLFW

* Clone GLFW: `cd ~/src && git clone https://github.com/glfw/glfw.git glfw-git`
* Checkout at a release: `cd glfw-git && git checkout 3.1.2`
* Compile/Build
  - `mkdir ~/src/glfw-build`
  - `cmake -DCMAKE_INSTALL_PREFIX:PATH="${HOME}/sw" -DCMAKE_C_FLAGS="-Wno-deprecated" ../glfw
* Check out the tests and the examples. Good stuff there.