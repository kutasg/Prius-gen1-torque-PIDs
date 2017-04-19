# Prius-gen1-torque-PIDs

This is for sharing the PID list for
Toyota Prius gen 1 (2000-2003)
model code NHW11

the nhw11.csv file can be used for
Torque OBD program v1.8.x
http://torque-bhp.com

Base of this work is the scangauge project,
converted to Torque.
But the automatic conversion is not perfect.

I've made modifications to make the file usable.
Main modifications:

Sensor naming prefixed with ECU name
(HV, EN, Bat)

Changing equation on negative value capable sensors

Changing unusual metric like dV cV deciVolt CentiVolt
(may be because of scangauge's limited display capability)

------------------
Additionally
A perl script that converts the recorded tracklog.csv to excel format
and an excel sheet with customizable graphs to visualize the data.
