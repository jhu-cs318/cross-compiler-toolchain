# Cross Compiler Toolchain

This repository hosts the binaries of the pre-built cross-compiler toolchain
for developing the Pintos projects. The binaries are prefixed with
`i386-elf-*`, e.g., `i386-elf-gcc`, `i386-elf-ld`. The release contains
binaries for two platforms: Linux and macOS. You should download the
appropriate ones.

To use the pre-built binaries (using macOS), 
```
mkdir -p ~/os/toolchain
cd ~/os/toolchain
wget https://github.com/jhu-cs318/cross-compiler-toolchain/releases/download/v1.0/macos-toolchain-binaries.tar.gz
tar xzvf macos-toolchain-binaries.tar.gz
```

(You can replace `~/os/toolchain` with any path you prefer. It is the `SWD` variable in 
the [project setup guide](https://www.cs.jhu.edu/~huang/cs318/fall22/project/setup.html))

Test if the toolchain works:

```
cd ~/os/toolchain/x86_64/bin
./i386-elf-gcc --version
```

If so, proceed with the Step 3 and Step 4 on the [project setup guide](https://www.cs.jhu.edu/~huang/cs318/fall22/project/setup.html) 
to build the Emulator and Pintos Utility Tools. Make sure you set the `SWD` variable 
to the path you choose above (e.g., `~/os/toolchain`).

Afterward, you can do a full test on building Pintos. Assume `~/os/pintos` 
is where you cloned the Pintos repository:

```
cd ~/os/pintos/src/threads
make
cd build
pintos --bochs -- run alarm-zero
```

You should see the Pintos compilation finishes successfully and Bochs window 
shows up.

**If the tools work, you can put `export PATH=$HOME/os/toolchain/x86_64/bin:$PATH` 
in your `.bashrc` or `.zshrc`**
