# Native Linux Setup Guide

## Overview
Linux Installation - Install CSSE3010 source and tools directly on Ubuntu (Not using a VM). You can install the CSSE3010 source and toolchain onto Ubuntu, directly. NOTE: You must first have your git account setup BEFORE attempting this.

**NOTE: ONLY USE THIS GUIDE IF YOU ARE NOT USING A VIRTUAL MACHINE**

## Ubuntu Automatic Script installation
The automatic script will download and install the required packages, add the sourcelib_env.sh script to your .bashrc startup script and add your user name to the “dialout” group.

1. Clone the sourcelib repository into your csse3010 directory using `git clone`
2. Go to the sourcelib/tools folder
3. Run the script sourcelib_install.sh as root – i.e. `sudo ./sourcelib_install.sh`
4. The script will download and install part of the toolchain
5. Run `source ~/.profile` 
6. Type `echo $SOURCELIB_ROOT` into your terminal. This command should return a path variable, i.e ~/csse3010/sourcelib


## Installing the GNU Arm Embedded Toolchain 

The GNU Arm Embedded Toolchain contains a compatible compiler for our MCU, while the utilities provided by STLink allows us to flash the Nucleo via the on-board STLinkV2 programmer.

1. Download the latest version of GNU Arm Embedded Toolchain for your OS via [https://developer.arm.com/open-source/gnu-toolchain/gnu-rm/downloads](https://developer.arm.com/open-source/gnu-toolchain/gnu-rm/downloads)
2. Run the following commands in your terminal:
    1. change into the home directory and make a new folder called tools `cd ~; mkdir tools`
    2. change into the directory where the file was downloaded into, Downloads is used here as an example, it could be called something different on your machine `cd ~/Downloads`
    3. extract the tar file into the tools folder that we created earlier `tar -xjf <NAME_OF_DOWNLOADED_FILE> -C ~/tools`
        * NOTE: Normally you'd need to add the executable folder to PATH but that had already been taken care of by the install script in step 3 of the previous section.  
        * test it with `arm-none-eabi-gcc --version`

