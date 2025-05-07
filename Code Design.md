# Breakdown
The computation on our Romi was split across 4 (or 5) processors to practice distributing computational loads and using serial communication protocols.
1. Swerve Module Boards
2. Main board RP2040
3. Main board ESP32
4. OpenMV (if we had/have time)
Each type of board had it's own set of challenges for coding.
## Swerve Module Boards
These boards were in charge of tracking the motor speed and position as well as the overall wheel direction and reporting it to the main board RP2040. In order to do this we found a library for the quadrature encoders that use the PIO functionality of the RP2040. This means that the controller is not responding to interrupts regularly and therefore has less load on it. We also found a library to interface with the AS5600 magnetic encoders and modified that to suit our needs. 
To control the flow of information between processors we created a standard set of structs that could be used. These included the ModuleState struct (track wheel speed and direction), BotState struct (track overall robot movements), and Cecilia (used to share geometric information about the swe