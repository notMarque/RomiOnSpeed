# Breakdown
The computation on our Romi was split across 4 (or 5) processors to practice distributing computational loads and using serial communication protocols.
1. Swerve Module Boards
2. Main board RP2040
3. Main board ESP32
4. OpenMV (if we had/have time)
Each type of board had it's own set of challenges for coding.
## Swerve Module Boards
These boards were in charge of tracking the motor 