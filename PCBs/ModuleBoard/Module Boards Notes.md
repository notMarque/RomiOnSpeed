- [ ] Grounds and 3v3 with spare pinouts
- [ ] ==Circuitry to provide VM to linreg without accidentally sending 12V up usb cable==
- [ ] LEDS!
- [x] Add AS5600 (and check location)
- [x] [[#Big Boy Connector]]
- [ ] [[#XT30]]

# I2C Connections
One two as5600 and one to main board for simplicity/speed
Having one be on pins 4 and 5 is really convenient because these are the default pins
The other can be on any pair of pins according to this diagram (feel free to change to make routing easier)
![[pico-pinout.png]]
# AS5600
pulling Dir high leads to counter clockwise being positive
PGO can be used for mannually programming, but we will use i2c
Locked in place but can be rotated however is needed. Just make sure that center is at (100, 97.25)
# Big Boy Connector
I've locked this in place because I got it completely centered, but it can be moved up and down a bit if needed or rotated
Two open pins (unless I forgot something)
Pins can definitelly be moved about as needed, they just need to stay up to date with main board
# XT30
Would be kinda nice to have for testing, but I imagine we won't have space
# Power Supply
Lin Reg Dropout: 1.2V
Diode forward voltage shit: 1.1V
3.3+1.2+1.1=5.5v ⊙﹏⊙∥

2mm In from edge first pins are
20mm board edge to swerve center
# Leds
[Newer Coller LEDS](https://www.digikey.com/en/products/detail/sparkfun-electronics/COM-16347/11630204)
