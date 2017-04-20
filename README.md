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

	Sensor naming prefixed with ECU name (where the data from).
	(HV, EN, Bat)

	Changing equation on negative value capable sensors

	Changing unusual metric like dV cV deciVolt CentiVolt
	(may be because of scangauge's limited display capability)


Explanation of some special PIDs:

Fuel Injection time for cyl #1:
	This value remains not 0 when engine is stopped.
	Must be combined with "Drive Situation ID"
	if Drive Situation ID is 0 => fuel injection is 0
	This can be used for instant fuel consumption measurement.

Shift Sensor 2:
	P : approx. 0.5 V 
	R : approx. 2.8 V 
	N : approx. 3.4 V 
	D : approx. 4.0 V 
	B : approx. 4.5 V

Shift Sensor 1:
	P : 1 
	R : 2 
	N : 4 
	D : 8 
	B : 16

Fuel system status #1:
	1 : Open loop due to insufficient engine temperature 
	2 : Closed loop, using oxygen sensor feedback to determine fuel mix 
	4 : Open loop due to engine load OR fuel cut due to deacceleration 
	8 : Open loop due to system failure 
	16: Closed loop, using at least one oxygen sensor but there is a fault in the feedback system

Drive Situation ID:
	0 : Engine stopped 
	1 : Engine about to be stopped 
	2 : Engine about to be started 
	3 : Engine operated or operating 
	4 : Generating power or load driving 
	6 : Revving up in P position



------------------------------------
Additionally
A perl script that converts the recorded tracklog.csv to excel format
and an excel sheet with customizable graphs to visualize the data.
