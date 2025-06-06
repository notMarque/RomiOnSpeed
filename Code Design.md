# Breakdown
The computation on our Romi was split across 4 (or 5) processors to practice distributing computational loads and using serial communication protocols.
1. Swerve Module Boards
2. Main board RP2040
3. Main board ESP32
4. OpenMV (if we had/have time)
Each type of board had it's own set of challenges for coding.
## Swerve Module Boards
These boards were in charge of tracking the motor speed and position as well as the overall wheel direction and reporting it to the main board RP2040. In order to do this we found a library for the quadrature encoders that use the PIO functionality of the RP2040. This means that the controller is not responding to interrupts regularly and therefore has less load on it. We also found a library to interface with the AS5600 magnetic encoders and modified that to suit our needs. 
To control the flow of information between processors we created a standard set of structs that could be used. These included the ModuleState struct (track wheel speed and direction), BotState struct (track overall robot movements), and Cecilia (used to share geometric information about the swerve modules). 
```cpp
// 10 bytes
struct ModuleState {
    uint8_t state = 0;
    uint16_t theta = 0;
    int16_t v = 0;
    uint8_t bat = 0;
    uint32_t time = 0;
    ModuleState(void) {}
    ModuleState(uint8_t _state, uint16_t _theta, int16_t _v, uint8_t _bat, long _time) : state(_state), theta(_theta), v(_v), bat(_bat), time(_time) {}
};  

// 12 Bytes
struct BotState {
    float u = 0.0f;
    float v = 0.0f;
    float w = 0.0f;
    BotState(void) {}
    BotState(float _u, float _v, float _w) : u(_u), v(_v), w(_w) {}
};

// This is a struct for the geometric position of a swerve module in case you can't tell from the name
// 4 bytes
struct Cecilia {
    float x = 0.0f;
    float y = 0.0f;
    Cecilia(void) {}
    Cecilia(float _x, float _y) : x(_x), y(_y) {}
};
```
The module boards act as I2C peripheral devices. The host a 256 byte array that can be read from and written two by the main board. The read and write functionality was mostly drawn from RP2040 example code; however, we implemented our own method to `memcpy` data into and out of the array. This allowed wheel speed data to be written from the main board to the module boards and also allowed the module boards to publish state information that the main board would have used to implement odometry.
==DRV Library==
## Main Board - RP2040
On our main board the low level processor was another RP2040. This one was planned to be tasked with communicating to the two swerve module boards over I2C, as described previously, monitoring battery voltage, monitoring the IMU, calculating necessary wheel speeds given a overall robot speed, and interpreting paths generated by the ESP32. Unfortunately, we were only able to get through I2C communications and calculating wheel speeds within our time constraint.
## Main Board - ESP32
The ESP32 on our main board was planned to handle communications to a mobile phone or laptop using UDP, pose estimation, and path planning using openMV cameras. UDP was successfully implemented; however, UART and I2C were being mean, and we were unable to communicate between this board and the main RP2040.