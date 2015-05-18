# x64BareBones, starting a 64 Bits OS almost from scratch.


## Introduction
**x64BareBones** is a basic setup to develop operating systems for the Intel 64 bits architecture.

The final goal of the project is to provide an entry point for a C kernel and the possibility to load extra binary modules separated from the main kernel.

It uses a [modification](PatchedPure64) of the [Pure64](http://www.returninfinity.com/pure64.html) boot loader to boot up the basic system. The modification enables to load a greater payload than the restrictive 26k that Pure64 allows.

**x64BraeBones** is written primarily in C, there is a small loader written in x86-64 assembly (Intel idiom).

## Environment setup
1- Install the following packages before building the Toolchain and Kernel:

```
nasm qemu gcc make
```

2- Build the Toolchain

Execute the following commands on the x64BareBones project directory:

```
user@linux:$ cd Toolchain
user@linux:$ make all
```

3- Build the Kernel

From the x64BareBones project directory run:

```
user@linux:$ make all
```

4- Run the kernel

From the x64BareBones project directory run:

```
user@linux:$ ./run.sh
```

## TODO
* Add output filename option for C Packer
* Add dongers ╰༼ •̀۝•́ ༽╯ (つ◉益◉)つ ლ(ಠ益ಠლ) ʕ ﹒︣ ᴥ ﹒︣ ʔ

Author: Rodrigo Rearden (RowDaBoat)
Collaborator: Augusto Nizzo Mc Intosh