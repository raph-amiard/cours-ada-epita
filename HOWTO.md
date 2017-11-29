How-tos
-------

## How to install GNAT GPL Native

- Go to http://adacore.com/download and download the package for your OS

- Extract it (on linux):

~~~sh
tar xvf <archive_name>.tar.gz
~~~

- Create a GNAT.sh file in a place practical for you, with contents

~~~sh
export PATH=<path to extracted archive dir>/bin:$PATH
~~~

- To use GNAT GPL, just source your sh file

~~~sh
source /path/to/GNAT.sh
~~~

- You can now run

~~~sh
$ gnatls --version
GNATLS GPL 2017 (20170515-63)
Copyright (C) 1992-2017, Free Software Foundation, Inc.
This is free software; see the source for copying conditions.
There is NO warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
~~~

## How to install arm-eabi toolchain

Same instructions as above, except:

- The toolchain is always 32 bits, so you will need some 32 bit libs installed
  on Linux.
- The gcc toolchain binaries start with arm-eabi: arm-eabi-gcc, arm-eabi-ld, etc

## Setting up stlink

- Follow instructions from here: https://github.com/texane/stlink/

On Linux, you might have to set-up udev rules. Run:

~~~sh
# Go in the stlink repo
cd stlink

# Copy udev rule files 
sudo cp etc/udev/rules.d/49-stlinkv* /etc/udev/rules.d
~~~

## Setting up Ada_Drivers_Library

- Follow instructions from here: https://github.com/AdaCore/Ada_Drivers_Library/tree/master/examples
