# Setting Up
Creating a PS2 Development toolchain can be quite
troublesome for a beginner. Experience with C/C++
and other cross compiling toolchains is recommended.

### Installing via Docker (Recommended)
[Docker](https://www.docker.com/) can be installed on a multitude of operating systems
and helps ease the use of software built for another operating
system on the current operating system. The PS2 homebrew toolchain
is no exception and can be installed with a few simple commands or
with the GUI interface of [Docker Desktop](https://www.docker.com/products/docker-desktop/).
- Windows
  - [Docker Desktop](https://docs.docker.com/desktop/install/windows-install/)
- Mac OS X
  - [Docker Desktop](https://docs.docker.com/desktop/install/mac-install/)
  - [Homebrew](https://brew.sh/) 
    - can be used to install Docker with the following command:
    `brew cask install docker`
- Linux
  - [Docker Desktop](https://docs.docker.com/desktop/install/linux-install/)
  - Per-distro installation instructions:
    - [Debian](https://docs.docker.com/desktop/install/debian/)
    - [Fedora](https://docs.docker.com/desktop/install/fedora/)
    - [Ubuntu](https://docs.docker.com/desktop/install/ubuntu/)
    - [Arch](https://docs.docker.com/desktop/install/archlinux/)

After installing Docker, starting Docker Desktop if you did not install
Docker standalone (through the use of a package manager) is a must to start
up the Docker Engine and be able to use Docker commands.

Docker works with "containers", which are essentially mini Virtual Machines
that are designed to start as fast as possible and be as lightweight as possible. 
You can create a container with the PS2 Homebrew toolchain by first pulling the PS2DEV 
image and creating a container with the PS2DEV image that has been pulled, which can be 
done with the following commands from Command Prompt or Terminal:

```bash
docker pull ps2dev/ps2dev:latest
docker start -ai ps2dev/ps2dev:latest PS2Dev
```

If all goes well, you should be dropped into the terminal interface
of the Docker container, which is denoted by `#` at the beginning of
terminal line.

### Installing locally
Installing a PS2 toolchain through Docker might not be ideal for some
users and the PS2 toolchain can be installed easily even without Docker.

For Windows users, this is highly unadvisable to do and will NOT work easily.
Mac OS X and Linux users will have better luck with this method as the toolchain
is designed to work against POSIX-compliant operating systems.

The steps to install a PS2 Homebrew toolchain locally works by:
1) Set proper environment variables
2) Cloning the PS2DEV GitHub repository
3) Executing the `build-all` shell script

Setting the proper environment variables requires modifying `~/.bashrc`, `~/.bash_profile`,
or `~/.profile` (only one of these) to ensure that PATH and PS2DEV environment variables are
set properly, which looks like the following:
```bash
export PS2DEV=/usr/local/ps2dev
export PS2SDK=$PS2DEV/ps2sdk
export GSKIT=$PS2DEV/gsKit
export PATH=$PATH:$PS2DEV/bin:$PS2DEV/ee/bin:$PS2DEV/iop/bin:$PS2DEV/dvp/bin:$PS2SDK/bin
```

Steps 2 and 3 can be done with the following commands:
```bash
git clone https://github.com/ps2dev/ps2dev.git # git@github.com:ps2dev/ps2dev.git for SSH
cd ps2dev/
./build-all.sh # ./build-extras.sh for only the extras
```

If no issues occur, congratulations, you now have a PS2 Homebrew toolchain and can now compile
code for the PS2!