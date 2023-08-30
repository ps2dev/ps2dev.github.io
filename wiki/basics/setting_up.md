---
layout: wiki
title: Creating a PS2 Development environment
---

<div style="text-align: center;">
Setting up a PS2 development environment can be quite hard for a beginner. It is recommended to have experience
with C/C++ toolchains and Linux. <br> Experience with Docker is also recommended as it allows for one to develop on any OS
without explicitly managing dependencies and build scripts for each OS.
</div>

### Installing via Docker (Recommended)
If you already have Docker installed, please skip to the next section.
- Windows
  - [Docker Desktop](https://docs.docker.com/desktop/install/windows-install/)
- Mac OS X
  - [Docker Desktop](https://docs.docker.com/desktop/install/mac-install/)
  - Homebrew installation instructions
    - `brew cask install docker`
- Linux
  - [Docker Desktop](https://docs.docker.com/desktop/install/linux-install/)
  - Per-distro installation instructions
    - [Debian installation](https://docs.docker.com/desktop/install/debian/)
    - [Fedora installation](https://docs.docker.com/desktop/install/fedora/)
    - [Ubuntu installation](https://docs.docker.com/desktop/install/ubuntu/)
    - [Arch installation](https://docs.docker.com/desktop/install/archlinux/)

After installing Docker, a Docker container containing the PS2 homebrew toolchain
can be created by the following commands.

- `docker pull ps2dev/ps2dev:latest`
- `docker start -ai ps2dev/ps2dev:latest PS2Dev`

If all goes well, the following commands should drop you into the command line
of the underlying container (Alpine Linux). With Docker Desktop, the process is as
simple as clicking on the search bar, searching "PS2Dev", then selecting "Run" which
will automatically pull the image.

### Installing on Linux
- Requirements
  - GCC/Clang
  - Make
  - CMake
  - Patch
  - Git
  - TexInfo
  - Flex
  - Bison
  - GetText
  - Wget
  - Gsl
  - Gmp
  - Zlib
  - Mpfr
  - Mpc

Installing a PS2 toolchain on Linux may be easier than using the Docker container.
To start the installation process, first clone the [GitHub repository](https://github.com/ps2dev/ps2dev)
by using the `git` command or using GitHub Desktop.

To clone with SSH, use the following command:
`git clone git@github.com:ps2dev/ps2dev.git`

To clone with HTTPS, use the following command:
`git clone https://github.com/ps2dev/ps2dev`

After cloning the repository, change the current directory into the `ps2dev` folder by doing:
`cd ps2dev`

It is recommended to modify your ~/.bashrc, ~/.profile, or ~/.bash_profile (only 1 of these) to ensure the PS2 toolchain
is put on PATH and all necessary environment variables are set.
```bash
export PS2DEV=/usr/local/ps2dev
export PS2SDK=$PS2DEV/ps2sdk
export GSKIT=$PS2DEV/gsKit
export PATH=$PATH:$PS2DEV/bin:$PS2DEV/ee/bin:$PS2DEV/iop/bin:$PS2DEV/dvp/bin:$PS2SDK/bin
```

Then run `source ~/.bashrc` or whichever file was edited to apply the environment variables in the current terminal
temporarily (~/.bashrc is loaded on each login and will be applied the next time you log in).

To build the entire PS2 toolchain, run `./build-all.sh` which will download and set up the PS2 toolchain.

To build just the extra dependencies, run `./build-extra.sh`