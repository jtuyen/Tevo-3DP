# Tevo-3DP
Personal configuration settings for Tevo 3d printer

# Cura 3.6 Settings #
Starting G-Code
```
G21 ;metric values
G90 ;absolute positioning
M82 ;set extruder to absolute mode
M107 ;start with the fan off
G28 X0 Y0 ;move X/Y to min endstops
G28 Z0 ;move Z to min endstops
G1 Z15.0 F9000 ;move the platform down 15mm
G92 E0 ;zero the extruded length
G1 F200 E3 ;extrude 3mm of feed stock
G92 E0 ;zero the extruded length again
G1 F200 E6 ;extrude 3mm of feed stock
G1 F9000
;Put printing message on LCD screen
M117 Printing...
```

Ending G-Code
```
M104 S0 ;extruder heater off
M140 S0 ;heated bed heater off (if you have it)
G91 ;relative positioning
G1 E-1 F300  ;retract the filament a bit before lifting the nozzle, to release some of the pressure
G1 Z+0.5 E-5 X-20 Y-20 F9000 ;move Z up a bit and retract filament even more
G90 ;absolute positioning
G1 X0 Y200 F3600 ;move extruder out of the way by moving the baseplate to the front for easier access to printed object
M84 ;steppers off
```
