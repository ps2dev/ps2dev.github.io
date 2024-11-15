---
layout: default
title: PS2 Homebrew Development
---

# About ps2dev

ps2dev is an open source development environment for Playstation 2&reg; development.  
This allows you to create applications, games, and more (homebrew) to run on Playstation 2 console.  

## Community

Discussion forums, wiki, and chat rooms are available:

* [Discussions](https://github.com/ps2dev/ps2sdk/discussions)  
* [Wiki](https://www.psdevwiki.com/ps2/Main_Page)  

### Chat

You can chat using many clients:  

Channels are bridged, so e.g. users on Matrix can see messages on IRC (and vice versa).

* [IRC](https://web.libera.chat/#ps2dev)  
* [Matrix](https://matrix.to/#/#ps2dev:matrix.org)  
* Discord (coming later)  

## Getting Started

### Installing

See the [installation instructions for ps2dev](https://github.com/ps2dev/ps2dev).  

### Updating

Repeat the installation instructions above to update the development environment.

### Removing

To remove all traces of the development environment, just delete your `$PS2DEV` directory. You can then reverse the steps in installing the prerequisites.

## Platform

### Writing Code

See the [API reference](https://ps2dev.github.io/ps2sdk/).  
Once the development environment is installed, samples are available at `$PS2SDK/samples`.  
Also, see [ps2homebrew](https://ps2homebrew.github.io/) for full programs using the development environment.  

### Building

Building is generally done using GNU Make with `Makefile` files.  
CMake support is also available when using the definition `-DCMAKE_TOOLCHAIN_FILE=$PS2SDK/ps2dev.cmake`.  

### Running

To run homebrew, you need an [entrypoint](https://www.psdevwiki.com/ps2/Vulnerabilities).   
For ease of use, installing FreeMCBoot, FreeHDBoot, or Opentuna is recommended.  
Use one of the above exploits to launch [ps2link](https://github.com/ps2dev/ps2link)  
Once ps2link is running, use ps2client to load the executable file (in .elf format) and to receive debugging output.  

### Debugging

The current recommended way to debug is to use ps2link and ps2client, as mentioned above.  

### Porting libraries

See the [ps2sdk-ports repository](https://github.com/ps2dev/ps2sdk-ports).   
