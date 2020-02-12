# Klipper Firmware

> ### WARNING!
> This repo is for my own personal use so that I have a backup of my Klipper config.  Copying this config as-is
> to use as your own could worst case cause damage to your printer.  If you are using this as a base to define
> your own configuration, make sure that you also read the [official Klipper examples](https://github.com/KevinOConnor/klipper/blob/master/config/example-extras.cfg) to understand what the 
> settings mean, and more importantly what they need to be set for your particular printer.
>
> Use at your own risk!

Klipper config for CR-10S printer with the following modifications that impact firmware configuration:
- SKR 1.3 board
- TMC2209 drivers
- BondTech BMG Extruder
- Mosquito Magnum hotend (including Mosquito high temperature sensor and heater cartridge)
- 3DFused x, y and z linear rail kits
- 3DFused z-braces
- EZABL Pro
- 24V PSU
- Moons MS17HA6P4200-06 0.9 deg steppers on X/Y, and Mons MS17HD6P4200-29 1.8 deg steppers on Z/Z1

Includes the following macros
- START_PRINT : to be called at start of each print.  Homes, loads the bed mesh profile, then calls PRIME_LINE
- PRIME_LINE : called by START_PRINT to draw a couple of primes before the print to prime the nozzle
- END_PRINT : to be called at the end of each print.  Turns off heaters and motors
- M600 : Load filament macro (calls PAUSE_MACRO then UNLOAD macros)
- PAUSE_MACRO : Saves the gcode state, calls PAUSE, then PARK_MACRO
- PARK_MACRO : Moves the nozzle to a safe location
- UNLOAD : Retracts the filament
- PURGE : Purges 45mm of filament
- LOAD_FILAMENT : Loads filament
- RESUME_MACRO : Loads the gcode state that was saved during PAUSE_MACRO, then calls RESIME
- G29 : Automatic bed levelling

Other points to note:
TODO
