rubus-tools
===========

Toolchain for cross-compiling for RaspberryPi target (ARM) from x86_64 Linux hosts and x86_64 Cygwin hosts.

### Status

The Linux-host toolchain works on my machine. The Cygwin toolchain is in progress.

### How To Use It

This will take a while:

    $ git clone https://github.com/dpow/rubus-tools.git
    
Add the binaries to your $PATH:
    
    $ echo PATH="${PATH}:/path/to/file/rubus-tools/arm-unknown-linux-gnueabi_x86-64-linux-host/bin" >> ~/.bashrc
    $ source ~/.bashrc

Make sure it works on your system:
    
    $ arm-unknown-linux-gnueabi-gcc --version

### Test It

Compile the "Hello, world!" program:

    $ cd test/
    $ arm-unknown-linux-gnueabi-gcc -o test test.c
    
Copy it to your Raspberry Pi:

    $ scp ~/rubus-tools/test/test me@othercomputer:/home/me/test

Execute it to see if it works:

    $ ssh me@othercomputer
    $ ./test
    Hello, world!
    
### Dependencies

This toolchain was compiled using `crosstool-ng_1.18.0` to build the following packages:
* binutils-2.19.1a
* cloog-ppl-0.15.11
* dmalloc-5.5.2
* duma-2.5.15
* expat-2.1.0
* gcc-linaro-4.7-2013.01
* gdb-6.8a
* glibc-2.9
* glibc-ports-2.9
* gmp-4.3.2
* libelf-0.8.13
* linux-3.2.37
* ltrace-0.5.3
* mpc-0.9
* mpfr-2.4.2
* ncurses-5.9
* strace-4.5.19

### Why?

There *is* an official toolchain for the RaspberryPi already available from https://github.com/raspberrypi/tools, so why bother?

Well, I'm teaching myself how to build embedded Linux systems, and since I already have a RaspberryPi to practice on, this seemed like a good place to start.

### License?

NONE. I make no claim of ownership or copyright to anything contained herein. All Programs and Software used to produce this Toolchain are Copyrighted and Licensed by their respective Owners. The source code for all the Software listed above can be obtained freely from their respective Websites. Do what you want. Within all those Licenses, of course.

### "Rubus?" Really?

*Yes, really*. It's the genus of plants that contains raspberries and blackberries.

### Anything else?

Nope. Cheers.

-Dylan
