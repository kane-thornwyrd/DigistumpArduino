# Changes made in this fork to enable reduced code size
- **To shrink generated code size by 5 to 15 percent** (depending on your code) the lto flag was added in `platform.txt`. To help finding code which consumes the flash, the generating of disassembler and memory map files are added. For Arduino IDE you will find these files in *C:\Users\<Name>\AppData\Local\Temp\arduino_build_<number>*.
- To **reflect the smaller bootloader size** of [micronucleus version 2.5](https://github.com/ArminJo/micronucleus-firmware) which allow 6522 instead of 6012 bytes (+9%) the *upload.maximum_size* entry was changed in `boards.txt`.
- Since the original gcc version does not support the lto flag, the compiler path was changed to the latest Arduino gcc (7.3.0-atmel3.6.1-arduino5) in the `package_digistump_index.json`.
- Enabled *compiler.cpp.extra_flags*.
- Bumped version to 1.6.8.

# Installation
To get all the benefits, just replace the old Digispark board URL **http://digistump.com/package_digistump_index.json** (e.g.in Arduino *File/Preferences*) by the new  **https://raw.githubusercontent.com/ArminJo/DigistumpArduino/master/package_digistump_index.json** and install the **Digistump AVR Boards** version **1.6.8**.
![Boards Manager](https://github.com/ArminJo/DigistumpArduino/blob/master/Digistump1.6.8.jpg)

## Update the bootloader to version 2.5
To **update** your old flash consuming **bootloader** you simply run one of the window [scripts](https://github.com/ArminJo/micronucleus-firmware/tree/master/utils)
like e.g. [Burn_upgrade-t85_default.cmd](https://github.com/ArminJo/micronucleus-firmware/blob/master/utils/Burn_upgrade-t85_default.cmd).
