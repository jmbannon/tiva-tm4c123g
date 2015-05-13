# TIVA TM4C123G Embedded Programming
## Installation
1. Follow [these well laid out instructions](http://chrisrm.com/howto-develop-on-the-ti-tiva-launchpad-using-linux/)

Note your GCC ARM compiler version when copying/pasting the commands provided

2. Within your embedded workspace, create an openocd-bin folder

`mkdir openocd-bin`

3. Copy `openocd` executable and contents within `tlc/` to `openocd-bin/`

## Flashing
`./lm4flash ~/path/to/executable/main.bin`

## Debugging with ARM-GDB
1. Assure there is a path exported to your ARM-GDB executables

`export PATH=$PATH:$HOME/path/to/gcc-arm-none-eabi-4_9-2015q1/bin`

2. (optional) Use the openocd executable or `sudo yum install openocd`

3. Link openocd to your board configuration
 
`sudo openocd -f openocd-bin/board/ek-tm4c123gxl.cfg`

4. Open ARM-GDB with your executable

`arm-none-abi-gdb main.out`

5. Connect the debugger to your microcontroller

`target extended-remote :3333`
