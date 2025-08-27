# Obstacle Avoider Robot

An autonomous robot that navigates environments by detecting and avoiding obstacles using ultrasonic sensors and servo motors.

![Arduino Robot](https://img.shields.io/badge/Platform-Arduino-00979D?style=for-the-badge&logo=arduino&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

## Features

- **Autonomous Navigation**: Moves independently without human intervention
- **Obstacle Detection**: Uses HC-SR04 ultrasonic sensor to detect objects
- **360-Degree Scanning**: Servo motor allows the sensor to scan surroundings
- **Intelligent Decision Making**: Chooses optimal path when obstacles are detected
- **Smooth Movement**: Gradual acceleration for controlled movement

## Components Required

- Arduino Uno or similar microcontroller
- HC-SR04 Ultrasonic Sensor
- SG90 Micro Servo Motor
- Adafruit Motor Shield (or L293D motor driver)
- 4x DC Motors with wheels
- Chassis kit
- 9V battery or Li-ion battery pack
- Jumper wires


## Installation & Setup

1. **Hardware Assembly**:
   - Mount the Arduino, motor shield, and sensors on the chassis
   - Connect the motors to the motor shield ports
   - Wire the ultrasonic sensor and servo as shown in the circuit diagram
   - Secure the battery for power

2. **Software Setup**:
   - Install the Arduino IDE on your computer
   - Install required libraries:
     - `AFMotor.h` (for Adafruit Motor Shield)
     - `Servo.h` (for servo control)
     - `NewPing.h` (for improved ultrasonic sensor functionality)

3. **Upload the Code**:
   - Copy the provided code into a new sketch in Arduino IDE
   - Save the sketch as `ObstacleAvoider.ino`
   - Select the correct board and port in the Arduino IDE
   - Upload the code to your Arduino

## How It Works

1. The robot moves forward continuously while scanning with the ultrasonic sensor
2. When an obstacle is detected within 25cm, the robot stops
3. The servo rotates to scan both left and right distances
4. The robot decides the clearer path based on distance measurements
5. It turns in the chosen direction and continues moving forward

## Code Overview

### Key Functions:
- `readDistance()`: Measures distance using the ultrasonic sensor
- `left_Distance()`: Rotates servo left and measures distance
- `right_Distance()`: Rotates servo right and measures distance
- `moveForward()`: Moves all motors forward with acceleration
- `moveBackward()`: Moves all motors backward with acceleration
- `turnLeft()`: Turns the robot left
- `turnRight()`: Turns the robot right
- `moveStop()`: Stops all motors

### Customization:
You can adjust these parameters in the code:
- `Max_Speed`: Maximum motor speed (0-255)
- `Max_Dist`: Maximum detection distance in cm
- Obstacle detection threshold (currently 25cm)

## Troubleshooting

| Issue | Possible Solution |
|-------|-------------------|
| Robot doesn't move | Check motor connections and power supply |
| Doesn't detect obstacles | Verify ultrasonic sensor wiring |
| Servo not rotating | Check servo connections and power |
| Erratic movements | Adjust distance thresholds in code |

## Future Enhancements

- Add Bluetooth/WiFi connectivity for remote control
- Implement path memory to navigate more efficiently
- Add multiple sensors for better obstacle detection
- Include a camera for computer vision capabilities
- Add voice feedback or status indicators

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## Acknowledgments

- Adafruit for the motor shield library
- Tim Eckel for the NewPing library
- Arduino community for continuous support and inspiration

---

**Note**: Always be cautious when working with motors and batteries. Ensure proper insulation and never leave the robot unattended while powered on.
