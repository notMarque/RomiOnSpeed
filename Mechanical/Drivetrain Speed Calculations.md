---
tags:
  - mechanical
---
# OG Romi
## Specs
$$
D_{wheel}=70mm
$$
$$
\omega=150rpm \tag{4.5v}
$$
## Calcs
$$
\omega_{actual}=150rpm \cdot \frac{1.2\cdot 6v}{4.5v}=240rpm
$$
$$
V_{actual}=\frac{240rev}{min}\cdot \frac{2 \pi\cdot 0.07m}{rev} \cdot \frac{1min}{60sec}=1.76\tfrac{m}{s}
$$
# New Romi
## Output
### Wheel Speed
$$
R_{wheel}=50mm
$$
$$
C=2\pi \cdot r
=2\pi \cdot 0.05m
=0.31415m
$$
$$
C\cdot \omega=V
$$
$$
\omega=\frac{V}{C}
=\frac{3.5m}{s}\cdot \frac{1}{0.31415m} \cdot \frac{60s}{1min}
=668rpm
$$
### Twist Speed
$$
\omega_{desired}=150rpm
$$
## Gear Calculations
Big Bevel Gear Teeth: Probably 1bout 40
Small Bevel Gear: 11-12 teeth
Spur Gear: 51 teeth
Pinion Gear: ?
### Wheel Speed Calculations
$$
\omega_{wheel}\cdot \frac{11t}{40t}\cdot\frac{50t}{Xt}=\omega_{motor}
$$
$$
\omega_{wheel}\cdot \frac{11t}{40t}\cdot 50t = \omega_{motor}\cdot Xt
$$
### Twist Speed Calculations
$$
\omega_{twist}\cdot \frac{50t}{Xt}=\omega_{motor}
$$
$$
\omega_{twist}\cdot 50t=\omega_{motor}\cdot Xt
$$
### Twist to Wheel Speed Ratio
$$
\frac{\omega_{twist}}{\omega_{wheel}}=\frac{11}{40}
$$
$$
\omega_{twist}=\frac{11}{40}\cdot \omega_{wheel}
=\frac{11}{40}\cdot 668rpm
=183.7rpm
$$
### Twist Speed to Motor Speed
$$
\omega_{motor}= \frac{50t}{14t}\cdot 183.7rpm = 656rpm
$$
**Decision:** 16t pinion
20.41:1