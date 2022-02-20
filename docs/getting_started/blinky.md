# Compiling your first app

## Getting Started
Navigate to sourcelib -> examples -> getting-started -> blink

Select your platform here, for most people this will be nucleo-f429. If you are an external student, you may have one of the other boards, check it carefully.

## Compiling
Inside the platform folder, there should be a file called `main.c` and a file called `Makefile`. Execute the command:
`make`

All the c files should now start building, when it finishes, there will be a main.bin file, main.elf file, main.hex file, and main.o file, as well as an obj directory.


## Updating flashing tools

The flashing tools used in this course rely on JLink libraries, JLink is used to communicate with the debugging chip on the board which will then flash the code (amongst doing other things).However the board dy default comes with a different debugging chip, ST-LINK, thus we will need to replace the ST-LINK firmware with JLink firmware. If you are an internal student, this may have already been done for you, and you can try skipping to the next section, external students should read on.

* Download and install the ST-LINK USB Drivers for Windows [ST-LINK](https://www.st.com/en/development-tools/stsw-link009.html), on your Windows machine (or RDP into UQ if you dont have Windows)
* Download and install the latest Windows [JLink-Firmware](https://www.segger.com/downloads/jlink/), on your Windows machine
* Download the ST-Link Reflash Utility from [Segger](https://www.segger.com/downloads/jlink/#STLink_Reflash)

Run the reflasher -> accept -> [1] Upgrade To J-Link -> [0] Quit

## Verifying JLink

Inside your VM, make sure the nucleo is attached as a device, verify by using `sudo dmesg` and looking at the bottom of the log for newly attached devices, as well as looking for /dev/ttyACM0 when the usb is pluged in and the device is attached to the VM. (Note the nucleo cannot be attached both to the VM and to the Host OS, so if its visible in your Host OS, it isnt attached to your VM)

Execute the following

```
JLinkExe
connect
STM32F429ZI (or other depending on your nucleo)
S
<Enter> (Default)
```

There should be some text ending with Cortex-M4 Identified

```
q (for quit)
```

## Flashing Code
Now we are ready to flash, navigate back to the getting started, blinky makefile and execute
```
make flash
```
Accept any popups, the flasher will now cycle through the Compare, Erase, Program, Verify steps, after which the LED's on the Nucleo should start blinking.


## Tips and Troubleshooting
* `make clean` cleans the compiled binaries, this is not always necessary when recompiling code, since not everything needs to be recompiled, however it is useful when a lot of changes have been made.
* `make -j` makes compiling faster by using all allocated cpu cores, note that when using a VM to make full use of this you would need to allocate more CPU cores in the VM settings
* if `make` complains about a `.depend` target, you open the makefile and change `include .depend` to `-include .depend`
