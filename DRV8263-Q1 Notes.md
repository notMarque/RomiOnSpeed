
# Basic Figures
## Variant Comparison
![[Pasted image 20250407211738.png]]
## Pinout
![[Pasted image 20250407212306.png]]

## Pin Functions
![[Pasted image 20250407212355.png]]

## Useful Times
![[Pasted image 20250407212540.png]]
![[Pasted image 20250407212842.png]]


## Pin Config Values
![[Pasted image 20250407213141.png]]

# FET Params
![[Pasted image 20250407213203.png]]
![[Pasted image 20250407213224.png]]
![[Pasted image 20250407213239.png]]
![[Pasted image 20250407213257.png]]

# How to Turn on
![[Pasted image 20250407213844.png]]

# What to do with Pins
## Figures
![[Pasted image 20250407214241.png]]
![[Pasted image 20250407214352.png]]
![[Pasted image 20250407214331.png]]![[Pasted image 20250407214416.png]]
![[Pasted image 20250407214719.png]]
![[Pasted image 20250407214734.png]]
## What to do with pins
### MODE
According to table 8-3, this should be R LVL 1OF3 for PH/EN MODE. This Means that it should constantly be pulled to GND.
### IPROPI 
Should be pulled to ground to disable over current and over voltage protection.
### nSleep
Should be connected to an IO pin, maybe with interrupt

### nFault
uhhhh idk

### DIAG
Pull low to gnd according to table 8-11 to turn on auto retry
### VM
.1 and 10 micro caps in parralel to gnd from VAA

### DRVOFF
Connect to GPIO

### IN1
Analog Pin

### IN2