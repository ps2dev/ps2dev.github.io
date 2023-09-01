# Using VSCode

### Developing with Docker
1. Install the [Remote - Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) 
plugin in VSCode. This extension allows you to connect to a running Docker instance, edit files inside, share files
back to the host, etc.
2. Install the [C/C++](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools) extension or the 
[clangd](https://marketplace.visualstudio.com/items?itemName=llvm-vs-code-extensions.vscode-clangd) extension to have
proper C/C++ support in VSCode.
3. Install [Makefile Tools](https://marketplace.visualstudio.com/items?itemName=ms-vscode.makefile-tools) or
[CMake Tools](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cmake-tools) extensions.

Start the Docker container using the `docker` command or with Docker Desktop. After the container is started
successfully, launch VSCode, click the Docker icon in the sidebar, click on the running container, then select
"Attach Visual Studio Code" to attach VSCode to the Docker container. The Remote Containers extension should start
downloading a VSCode remote server into the Docker container and after completion, will display a VSCode window
with the contents of the Docker container.

Development samples can be in `/usr/local/ps2dev/ps2sdk/samples` and can be compiled with the `make` command or
with the Makefile Tools extension above.

Congratulations! You are now able to create PS2 Homebrew using the PS2 SDK with Docker and VSCode.

### Developing without Docker
1. Install the [C/C++](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools) extension or the
   [clangd](https://marketplace.visualstudio.com/items?itemName=llvm-vs-code-extensions.vscode-clangd) extension to have
   proper C/C++ support in VSCode.
2. Install [Makefile Tools](https://marketplace.visualstudio.com/items?itemName=ms-vscode.makefile-tools) or
   [CMake Tools](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cmake-tools) extensions.

