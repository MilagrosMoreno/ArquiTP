# x64BareBones

x64BareBones is a basic setup to develop operating systems for the Intel 64 bits architecture.

The final goal of the project is to provide an entry point for a kernel and the possibility to load extra binary modules separated from the main kernel.

It uses a modification of the [Pure64](http://www.returninfinity.com/pure64.html) boot loader to boot up the basic system. The modification enables to load a greater payload than the restrictive 26k that Pure64 allows.

## Environment setup:
1- Install the following packages before building the Toolchain and Kernel:

nasm qemu gcc-4.8 g++-4.8 make

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


Author: Rodrigo Rearden (RowDaBoat)
Welcome to your wiki! This is the default page we've installed for your convenience. Go ahead and edit it.

## Wiki features

This wiki uses the [Markdown](http://daringfireball.net/projects/markdown/) syntax.

The wiki itself is actually a git repository, which means you can clone it, edit it locally/offline, add images or any other file type, and push it back to us. It will be live immediately.

Go ahead and try:

$ git clone https://RowDaBoat@bitbucket.org/RowDaBoat/x64barebones.git/wiki
```

Wiki pages are normal files, with the .md extension. You can edit them locally, as well as creating new ones.

## Syntax highlighting


You can also highlight snippets of text (we use the excellent [Pygments][] library).

[Pygments]: http://pygments.org/


Here's an example of some Python code:

```
#!python

def wiki_rocks(text):
    formatter = lambda t: "funky"+t
    return formatter(text)
```


You can check out the source of this page to see how that's done, and make sure to bookmark [the vast library of Pygment lexers][lexers], we accept the 'short name' or the 'mimetype' of anything in there.
[lexers]: http://pygments.org/docs/lexers/


Have fun!