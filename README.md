# Cross Compiler Toolchain

This repository hosts the binaries of the pre-built 
[cross-compiler toolchain](https://www.cs.jhu.edu/~huang/cs318/fall21/project/setup.html) for 
developing the Pintos projects. The binaries are prefixed with `i386-elf-*`,
e.g., `i386-elf-gcc`, `i386-elf-ld`. The release contains binaries for two platforms: 
Linux and macOS. You should download the appropriate ones.

To use the pre-built binaries (using macOS):

```
mkdir -p ~/os/toolchain
cd ~/os/toolchain
wget https://github.com/jhu-cs318/cross-compiler-toolchain/releases/download/v1.0/macos-toolchain-binaries.tar.gz
tar xzvf macos-toolchain-binaries.tar.gz
```

Test if they work:

```
export PATH=$HOME/os/toolchain/x86_64/bin:$PATH
i386-elf-gcc --version
cd ~/os/pintos/src/threads
make
```
