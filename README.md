rubus-tools
===========

Toolchain for cross-compiling for RaspberryPi target (ARM) from x86_64 Linux hosts and x86_64 Cygwin hosts.

### How To Use It

This will take a while:

    $ git clone https://github.com/dpow/rubus-tools.git
    
Add the binaries to your $PATH:
    
    $ echo PATH="${PATH}:/path/to/file/rubus-tools/arm-unknown-linux-gnueabi_x86-64-linux-host/bin" >> ~/.bashrc
    $ source ~/.bashrc

Test them out:
    
    $ arm-unknown-linux-gnueabi-gcc --version
      arm-unknown-linux-gnueabi-gcc (crosstool-NG 1.18.0) 4.7.3 20130102 (prerelease)
      Copyright (C) 2012 Free Software Foundation, Inc.
      This is free software; see the source for copying conditions.  There is NO
      warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
