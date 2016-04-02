---
layout: note
title: Home Directory Installed Software
---


## Directories for Everything

* `src` for all source code
* `sw` or whatever directory you want to hold everything
* Within `sw` these directories:
  - `bin`, `include`, `lib/pkgconfig`, `man`, `share/{man,info}`

## .bashrc or .profile

```bash
# pkg-config setup (OS X it is not default installed)
export PKG_CONFIG_PATH="/usr/local/lib/pkgconfig:/usr/local/lib:/usr/lib/pkgconfig"

# "sw" directory
export PATH="${HOME}/sw/bin:${PATH}"
export MANPATH="${HOME}/sw/man:${HOME}/sw/share/man:${MANPATH}"
export INFOPATH="${HOME}/sw/info:${HOME}/sw/share/info:${INFOPATH}"
export PKG_CONFIG_PATH="${HOME}/sw/lib/pkgconfig:${PKG_CONFIG_PATH}"
export LD_LIBRARY_PATH="${HOME}/sw/lib"
```

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
* `make check`
* `make install`
* If you haven't already done so, update your `PKG_CONFIG_PATH` as mentioned above

# Building/Installing with CMake

Building with CMake is best done as an "out of tree build", which means build in a separate directory. If something goes wrong, just remove the build directory and start again.

If you wish a visual check of the options on the command line (`DCMAKE_...`), then call `ccmake` rather than `cmake` to run the graphical command-line program. Configure the build there by pressing `c` (you may need to press it twice). The option `Press [g] to generate and exit` will appear. Press `g`. Now continue with the usual 'make && make install`

## GLFW

* Clone GLFW: `cd ~/src && git clone https://github.com/glfw/glfw.git glfw-git`
* Checkout at a release: `cd glfw-git && git checkout 3.1.2`
* Compile/Build
  - `mkdir ~/src/glfw-build`
  - `cmake -DCMAKE_INSTALL_PREFIX:PATH="${HOME}/sw" -DCMAKE_C_FLAGS="-Wno-deprecated" -G "Unix Makefiles" ../glfw`
  - `make`
  - `make install`
  - Check some things: `pkg-config --static --libs glfw3`  `pkg-config --cflags glfw3`
* Check out the tests and the examples. Good stuff there.


# ADVANCED: Build a bleeding edge version of a compiler

I'm serious. This is advanced. If you mess it up, you can destroy much of your system's ability to function. So be careful. 

Check every command you type twice.

You have been warned.

## LLVM/Clang (on OSX)

These steps may be checked against the latest at the [clang website](clang.llvm.org/get_started.html)

```bash
cd ~/src
svn co http://llvm.org/svn/llvm-project/llvm/trunk llvm
cd llvm/tools/
svn co http://llvm.org/svn/llvm-project/cfe/trunk clang
cd ../projects/
svn co http://llvm.org/svn/llvm-project/compiler-rt/trunk compiler-rt
cd ../..
mkdir llvm-svn-build
cd llvm-svn-build

# THIS PART IS IMPORTANT!!! The INSTALL_PREFIX is crucial!
# Here we will install to ${HOME}/llvm-svn
cmake -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX="${HOME}/llvm-svn/" -DLLVM_TARGETS_TO_BUILD=host -G "Unix Makefiles" ../llvm
time -p make -j12
make install
```

