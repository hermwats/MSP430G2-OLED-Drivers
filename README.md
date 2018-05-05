# MSP430G2-OLED-Drivers
Driver library for MSP430G2 and 0.96 inch OLED display

This is development work to  build a library that will fit and work with MSP430G2553 Launchpad board.

The OLED is I2C interface to the MSP430 Launchpad.

The Launchpad is 16K program memory and only 512 bytes of SRAM.  Most libraries available use over 1K ram space, so no double buffering can be used - the display memory itself is 512 bytes.  This limits the capabilities of the functions (write only, no mirror of OLED buffer).

The Wire() library in Energia does not work for me on the OLED, so this work combines a direct minimal drive code with the OZ_OLED library.  This library works on Arduino Nano straight out, but compiling with GCC in Energia environment has multiple conflicts with predefined variables/functions.  First task was to get OZ_LED library to compile.  The have to merge code for direct drive of display that replaces Wire() and works.

