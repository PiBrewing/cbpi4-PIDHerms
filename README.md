# CBPi4 HERMS PID KettleLogic 

### This Kettle Logic can be used to run a HERMS System with CraftbeerPi4. 

## Mash temperature is controlled via PID logic
- The Kettle logic is intended to be used in a HERMS system with HLT. It is a PID logic. PID parameters can be for instance derived from the PID AutoTune plugin (https://github.com/avollkopf/cbpi4-PIDAutoTune)
- It runs on PID control until it reaches a specified temperature. Above that temperature it heates w/o PID logic until a specified boil temp is reached.
- Power to run boil can be specified in the plugin
- Kettle Agitator (Pump) is siwtched on in Automode

![CBPi4 Settings](https://github.com/avollkopf/cbpi4-PIDHerms/blob/main/Settings.png?raw=true)

## Parameters:
- Configurable:
	- P: Proportional - Takes current value into account
	- I: Integral - Takes past values into account
	- D: Derivative - Takes future values into account
	- Max Output: Maximum Power (%) to be used for PID during Ramp up
	- Max Boil Output: Maximum Power during when Boil Temp is reached
	- Max Boil Temp: When Temp is reached,  power is set to Max Boil Output
	- Internal Loop: Seconds of the internal loop -> Determines maximum PID resolution
	- HLT Sensor: Sensor that measures your HLT temperature
	- DeltaTemp: Plugin allows control of HLT temp. This values determines the max delta temp that the HLT is allowed to be above the Target Mash Temp 

## Installation:
- sudo pip3 install cbpi4-PIDHerms 
- (or from the GIT repo) -> sudo pip3 install https://github.com/avollkopf/cbpi4-PIDHerms/archive/main.zip
- cbpi add cbpi4-PIDHerms 

## Requirements:
- CBPi4 Version 4.0.0.35 or later (currently only available from my fork)

Changelog:

- 23.09.21: Initial commit
