rubus-tools
===========

Toolchain for cross-compiling for RaspberryPi target (ARM) from x86_64 Linux hosts and x86_64 Windows hosts (hopefully).

### Status

The Linux-host toolchains targeting ARM and Mingw both work on my machine. The Windows-host toolchain is in progress.

### How To Use It

This will take a while:

    $ git clone https://github.com/dpow/rubus-tools.git
    
Add the binaries to your $PATH:
    
    $ echo PATH="${PATH}:/path/to/file/rubus-tools/toolchains/arm-rpi-linux-gnueabi/bin" >> ~/.bashrc
    $ source ~/.bashrc

Make sure it works on your system:
    
    $ arm-rpi-linux-gnueabi-gcc --version

### Test It

Compile the "Hello, world!" program:

    $ arm-rpi-linux-gnueabi-gcc -o test test.c
    
Copy it to your Raspberry Pi:

    $ scp ~/rubus-tools/test me@raspberrypi:/home/me/test

Execute it to see if it works:

    $ ssh me@raspberrypi
    $ ./test
    Hello, world!
    
### Dependencies

The `arm-rpi-linux-gnueabi` toolchain for x86-64 Linux hosts was compiled using `crosstool-ng_1.18.0` to build the following packages:
* autoconf-2.65
* automake-1.11.1
* binutils-2.22
* cloog-ppl-0.15.11
* dmalloc-5.5.2
* duma_2_5_15
* ecj-latest
* eglibc-2_17
* eglibc-ports-2_17
* expat-2.1.0
* gcc-linaro-4.7-2013.01
* gdb-linaro-7.5-2012.12-1
* gmp-4.3.2
* libelf-0.8.13
* libtool-2.2.6b
* linux-3.6.11
* ltrace_0.5.3
* m4-1.4.13
* make-3.81
* mpc-0.9
* mpfr-2.4.2
* ncurses-5.9
* ppl-0.11.2
* strace-4.5.19

The `x86_64-w64-mingw32` toolchain for x86-64 Linux hosts was compiled using using `crosstool-ng_1.18.0` to build the following packages:
* autoconf-2.65
* automake-1.11.1
* binutils-2.21.1a
* cloog-ppl-0.15.10
* ecj-latest (version uncertain)
* gcc-4.5.2
* gdb-7.4.1
* gmp-4.3.2
* libelf-0.8.13
* libtool-2.2.6b
* m4-1.4.13
* make-3.81
* mingw-w64-v2.0.7
* mpc-0.9
* mpfr-2.4.2
* ppl-0.10.2

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
