# Klipper Firmware

Klipper config for CR-10S printer with the following modifications that impact firmware configuration:
- SKR 1.3 board
- TMC2209 drivers
- BondTech BMG Extruder
- Mosquito Magnum hotend (including Mosquito high temperature sensor and heater cartridge)
- 3DFused x, y and z linear rail kits
- 3DFused z-braces
- EZABL

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
