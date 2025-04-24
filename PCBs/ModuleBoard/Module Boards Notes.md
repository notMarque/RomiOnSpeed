- [ ] Grounds and 3v3 with spare pinouts
- [ ] LEDS!
- [x] Add AS5600 (and check location)
- [x] [[#Big Boy Connector]]

# I2C Connections
One two as5600 and one to main board for simplicity/speed
Having one be on pins 4 and 5 is really convenient because these are the default pins
The other can be on any pair of pins according to this diagram (feel free to change to make routing easier)
![[pico-pinout.png]]
# AS5600
pulling Dir high leads to counter clockwise being positive
PGO can be used for mannually programming, but we will use i2c
# Big Boy Connector
I've locked this in place because I got it completely centered, but it can be moved up and down a bit if needed or rotated
Two open pins (unless I forgot something)
Pins can definitelly be moved about as needed, they just need to stay up to date with main board