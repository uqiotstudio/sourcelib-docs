# Compiling your first app

## Getting Started
Navigate to sourcelib -> examples -> getting-started -> blink

Select your platform here, for most people this will be nucleo-f429. If you are an external student, you may have one of the other boards, check it carefully.

## Compiling
Inside the platform folder, there should be a file called `main.c` and a file called `Makefile`. Execute the command:
`make`

All the c files should now start building, when it finishes, there will be a main.bin file, main.elf file, main.hex file, and main.o file, as well as an obj directory.



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
