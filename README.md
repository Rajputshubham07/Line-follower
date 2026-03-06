# 🤖 Line Follower Robot Project

[![Project Status](https://img.shields.io/badge/Status-Active-success.svg)](https://github.com)
[![Arduino](https://img.shields.io/badge/Arduino-UNO-00979D.svg?logo=arduino)](https://www.arduino.cc/)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

> An autonomous line-following robot built with Arduino UNO and IR sensors, designed to navigate along a predefined path using real-time sensor feedback and motor control algorithms.

**Created by:** Shubham Singh (BBDNIIT) | [LinkedIn](https://www.linkedin.com/in/shubham-singh-b6a586307/)

---

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Architecture](#architecture)
- [Technology Stack](#technology-stack)
- [Hardware Components](#hardware-components)
- [Circuit Diagram](#circuit-diagram)
- [Software Architecture](#software-architecture)
- [How It Works](#how-it-works)
- [Project Structure](#project-structure)
- [Setup & Installation](#setup--installation)
- [Usage](#usage)
- [Web Interface](#web-interface)
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)
- [Acknowledgments](#acknowledgments)

---

## 🎯 Overview

The Line Follower Robot is an autonomous mobile robot that uses infrared (IR) sensors to detect and follow a black line on a white surface. This project demonstrates fundamental concepts in robotics, embedded systems, and control algorithms, making it an excellent educational tool for understanding autonomous navigation.

### Key Capabilities
- **Autonomous Navigation**: Follows predefined paths without human intervention
- **Real-time Decision Making**: Processes sensor data and adjusts movement instantly
- **Adaptive Control**: Corrects trajectory based on line detection
- **Educational Platform**: Ideal for learning robotics and embedded programming

---

## ✨ Features

- ✅ **Autonomous Line Tracking** - Follows black lines on white surfaces with high accuracy
- ✅ **IR Sensor Array** - Uses 3 infrared sensors (left, center, right) for precise line detection
- ✅ **Arduino-Based Control** - Powered by Arduino UNO for reliable processing
- ✅ **Motor Driver Integration** - L298N/L293D motor driver for efficient motor control
- ✅ **Real-time Processing** - Instant response to sensor inputs
- ✅ **Interactive Web Documentation** - Beautiful HTML interface with project details
- ✅ **Scroll Animations** - Engaging user experience with reveal-on-scroll effects
- ✅ **Responsive Design** - Mobile-friendly documentation interface

---

## 🏗️ Architecture

### System Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    LINE FOLLOWER ROBOT                   │
└─────────────────────────────────────────────────────────┘
                            │
        ┌───────────────────┼───────────────────┐
        │                   │                   │
   ┌────▼────┐        ┌─────▼─────┐      ┌─────▼─────┐
   │ SENSORS │        │ PROCESSOR │      │  ACTUATORS │
   └─────────┘        └───────────┘      └───────────┘
        │                   │                   │
   ┌────▼────┐        ┌─────▼─────┐      ┌─────▼─────┐
   │ IR Left │        │  Arduino  │      │   Motor   │
   │IR Center│───────▶│    UNO    │─────▶│  Driver   │
   │ IR Right│        │           │      │ (L298N)   │
   └─────────┘        └───────────┘      └─────┬─────┘
                            │                   │
                      ┌─────▼─────┐      ┌─────▼─────┐
                      │   Power   │      │  DC Motors│
                      │  Supply   │      │  (Left +  │
                      │ (Battery) │      │   Right)  │
                      └───────────┘      └───────────┘
```

### Control Flow

```
┌──────────────┐
│ IR Sensors   │ ──┐
│ Detect Line  │   │
└──────────────┘   │
                   ▼
┌──────────────────────────────┐
│ Arduino UNO Reads Sensor     │
│ Values (Digital/Analog)      │
└──────────────────────────────┘
                   │
                   ▼
┌──────────────────────────────┐
│ Decision Algorithm:          │
│ • All sensors on line → FWD  │
│ • Left sensor off → Turn R   │
│ • Right sensor off → Turn L  │
│ • All sensors off → Stop     │
└──────────────────────────────┘
                   │
                   ▼
┌──────────────────────────────┐
│ Motor Driver Receives PWM    │
│ Signals from Arduino         │
└──────────────────────────────┘
                   │
                   ▼
┌──────────────────────────────┐
│ Motors Rotate Based on       │
│ Control Signals              │
└──────────────────────────────┘
```

---

## 💻 Technology Stack

### Hardware
| Component | Technology | Purpose |
|-----------|-----------|---------|
| **Microcontroller** | Arduino UNO (ATmega328P) | Main processing unit |
| **Sensors** | IR Sensors (3x) | Line detection |
| **Motor Driver** | L298N / L293D | Motor control interface |
| **Motors** | DC Geared Motors (2x) | Robot movement |
| **Power** | Li-ion Battery / 9V | Power supply |
| **Chassis** | Acrylic/Plastic | Robot frame |

### Software
| Technology | Purpose |
|-----------|---------|
| **Arduino IDE** | Firmware development |
| **C/C++** | Programming language |
| **HTML5** | Web documentation |
| **CSS3** | Styling and animations |
| **JavaScript** | Interactive features |

### Web Technologies
- **Frontend Framework**: Vanilla JavaScript
- **Styling**: Custom CSS with animations
- **Font**: Poppins (Google Fonts)
- **Design Pattern**: Responsive, mobile-first
- **Animation**: Scroll-triggered reveals, floating elements

---

## 🔧 Hardware Components

### Bill of Materials (BOM)

| S.No | Component | Quantity | Specifications |
|------|-----------|----------|----------------|
| 1 | Arduino UNO | 1 | ATmega328P, 5V operating voltage |
| 2 | IR Sensors | 3 | Digital output, adjustable sensitivity |
| 3 | Motor Driver | 1 | L298N or L293D, dual H-bridge |
| 4 | DC Motors | 2 | 6V-12V, geared (100-300 RPM) |
| 5 | Wheels | 2 | Compatible with motor shaft |
| 6 | Caster Wheel | 1 | Front/rear support |
| 7 | Chassis | 1 | Acrylic or plastic base |
| 8 | Battery | 1 | 7.4V Li-ion or 9V |
| 9 | Jumper Wires | 20+ | Male-to-male, male-to-female |
| 10 | Switch | 1 | Power on/off |

### Component Details

#### Arduino UNO
- **Microcontroller**: ATmega328P
- **Operating Voltage**: 5V
- **Digital I/O Pins**: 14 (6 PWM outputs)
- **Analog Input Pins**: 6
- **Flash Memory**: 32 KB

#### IR Sensors
- **Type**: Reflective infrared sensors
- **Detection Range**: 2-30 cm (adjustable)
- **Output**: Digital (HIGH/LOW)
- **Working Principle**: Detects light reflection difference between black and white surfaces

#### Motor Driver (L298N)
- **Type**: Dual H-Bridge
- **Motor Channels**: 2
- **Max Current**: 2A per channel
- **Input Voltage**: 5V-35V
- **Logic Voltage**: 5V

---

## 📐 Circuit Diagram

### Wiring Connections

```
Arduino UNO          IR Sensors
-----------          ----------
    5V    ────────▶  VCC (All 3 sensors)
    GND   ────────▶  GND (All 3 sensors)
    D2    ────────▶  OUT (Left Sensor)
    D3    ────────▶  OUT (Center Sensor)
    D4    ────────▶  OUT (Right Sensor)

Arduino UNO          Motor Driver (L298N)
-----------          --------------------
    D5    ────────▶  IN1 (Left Motor)
    D6    ────────▶  IN2 (Left Motor)
    D9    ────────▶  IN3 (Right Motor)
    D10   ────────▶  IN4 (Right Motor)
    5V    ────────▶  Logic VCC
    GND   ────────▶  GND

Motor Driver         Motors & Power
------------         --------------
    OUT1  ────────▶  Left Motor (+)
    OUT2  ────────▶  Left Motor (-)
    OUT3  ────────▶  Right Motor (+)
    OUT4  ────────▶  Right Motor (-)
    12V   ────────▶  Battery (+)
    GND   ────────▶  Battery (-)
```

### Pin Configuration Summary

| Arduino Pin | Connected To | Function |
|-------------|--------------|----------|
| D2 | Left IR Sensor | Line detection (left) |
| D3 | Center IR Sensor | Line detection (center) |
| D4 | Right IR Sensor | Line detection (right) |
| D5 | Motor Driver IN1 | Left motor control |
| D6 | Motor Driver IN2 | Left motor control |
| D9 | Motor Driver IN3 | Right motor control |
| D10 | Motor Driver IN4 | Right motor control |
| 5V | Sensors + Driver | Power supply |
| GND | Common Ground | Ground reference |

---

## 🧠 Software Architecture

### Algorithm Logic

```cpp
// Pseudo-code for line following algorithm

void loop() {
    // Read sensor values
    leftSensor = digitalRead(LEFT_SENSOR_PIN);
    centerSensor = digitalRead(CENTER_SENSOR_PIN);
    rightSensor = digitalRead(RIGHT_SENSOR_PIN);
    
    // Decision making
    if (centerSensor == BLACK && leftSensor == WHITE && rightSensor == WHITE) {
        moveForward();  // On track
    }
    else if (leftSensor == BLACK) {
        turnLeft();     // Line detected on left
    }
    else if (rightSensor == BLACK) {
        turnRight();    // Line detected on right
    }
    else if (allSensors == WHITE) {
        stop();         // Lost the line
    }
}
```

### State Machine

```
        ┌─────────────┐
        │   FORWARD   │ ◀─── Center sensor detects line
        └──────┬──────┘
               │
       ┌───────┼───────┐
       │               │
  ┌────▼────┐     ┌────▼────┐
  │ TURN    │     │  TURN   │
  │  LEFT   │     │  RIGHT  │
  └────┬────┘     └────┬────┘
       │               │
       └───────┬───────┘
               │
        ┌──────▼──────┐
        │    STOP     │ ◀─── All sensors off line
        └─────────────┘
```

---

## 📁 Project Structure

```
line-follower/
│
├── line follower/
│   ├── index.html              # Main web documentation
│   └── image/                  # Project images
│       ├── 1.JPG              # Robot overview
│       ├── 2.JPG              # Sensor details
│       ├── 3.JPG              # Assembly process
│       ├── 4.JPG              # Additional view
│       ├── s2.jpeg            # Team photo
│       └── s5.jpg             # Creator photo
│
├── README.md                   # This file
└── arduino_code/              # (To be added)
    └── line_follower.ino      # Arduino sketch
```

---

## 🚀 Setup & Installation

### Prerequisites
- Arduino IDE (v1.8.x or higher)
- USB cable (Type A to Type B)
- Basic soldering skills (optional)
- Multimeter (for testing)

### Hardware Assembly

1. **Mount the Chassis**
   - Attach motors to the chassis using screws
   - Install wheels on motor shafts
   - Add caster wheel for balance

2. **Install Arduino & Motor Driver**
   - Secure Arduino UNO on chassis
   - Mount motor driver near motors
   - Ensure proper spacing for wiring

3. **Position IR Sensors**
   - Mount 3 IR sensors at the front
   - Height: 5-10mm above ground
   - Spacing: 2-3cm apart
   - Alignment: Perpendicular to ground

4. **Wire Connections**
   - Follow the circuit diagram above
   - Use color-coded wires (Red: +5V, Black: GND)
   - Secure connections with tape or heat shrink

5. **Power Setup**
   - Connect battery to motor driver
   - Add power switch for easy control
   - Verify voltage levels with multimeter

### Software Setup

1. **Install Arduino IDE**
   ```bash
   # Download from: https://www.arduino.cc/en/software
   ```

2. **Clone Repository**
   ```bash
   git clone https://github.com/yourusername/line-follower.git
   cd line-follower
   ```

3. **Upload Code**
   - Open `arduino_code/line_follower.ino` in Arduino IDE
   - Select Board: Tools → Board → Arduino UNO
   - Select Port: Tools → Port → (Your Arduino Port)
   - Click Upload button

4. **Calibrate Sensors**
   - Adjust potentiometers on IR sensors
   - Test on black line: LED should light up
   - Test on white surface: LED should turn off

---

## 🎮 Usage

### Running the Robot

1. **Prepare the Track**
   - Create a black line (2-3cm wide) on white surface
   - Use electrical tape or black marker
   - Ensure good contrast

2. **Power On**
   - Turn on the power switch
   - Check if Arduino LED lights up
   - Verify motor driver power LED

3. **Place Robot**
   - Position robot on the line
   - Center sensor should be on the line
   - Ensure wheels are on white surface

4. **Start Navigation**
   - Robot will automatically start following the line
   - Observe sensor LEDs for debugging
   - Adjust sensor sensitivity if needed

### Troubleshooting

| Issue | Possible Cause | Solution |
|-------|---------------|----------|
| Robot doesn't move | Power issue | Check battery voltage and connections |
| Moves in circles | Motor wiring reversed | Swap motor wires on one side |
| Doesn't follow line | Sensor calibration | Adjust IR sensor potentiometers |
| Erratic movement | Loose connections | Secure all wire connections |
| Slow response | Low battery | Recharge or replace battery |

---

## 🌐 Web Interface

The project includes a beautiful, interactive web documentation interface built with modern web technologies.

### Features
- **Hacker-style Boot Animation**: Terminal-like initialization sequence
- **Scroll Animations**: Smooth reveal effects as you scroll
- **Responsive Design**: Works on desktop, tablet, and mobile
- **Image Gallery**: Project photos with glowing borders
- **Floating LinkedIn Button**: Direct contact link
- **Dark Theme**: Eye-friendly cyberpunk aesthetic

### Viewing the Documentation

```bash
# Navigate to project directory
cd line-follower

# Open in browser (macOS)
open "line follower/index.html"

# Or use a local server
python3 -m http.server 8000
# Then visit: http://localhost:8000/line%20follower/index.html
```

### Customization

Edit `line follower/index.html` to:
- Update project details
- Add more images
- Modify color scheme (search for `#00eaff`)
- Change animations timing
- Update LinkedIn profile link

---

## 🔮 Future Enhancements

### Planned Features
- [ ] **PID Control Algorithm** - Smoother line following with proportional-integral-derivative control
- [ ] **Speed Control** - Variable speed based on line curvature
- [ ] **Obstacle Detection** - Ultrasonic sensors for obstacle avoidance
- [ ] **Bluetooth Control** - Mobile app for remote monitoring
- [ ] **Data Logging** - SD card module for recording sensor data
- [ ] **OLED Display** - Real-time status display
- [ ] **Multi-line Detection** - Handle intersections and junctions
- [ ] **Battery Monitoring** - Low battery warning system

### Advanced Upgrades
- Replace Arduino with ESP32 for WiFi connectivity
- Add camera module for computer vision-based tracking
- Implement machine learning for adaptive behavior
- Create PCB for cleaner wiring
- 3D print custom chassis

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork the Repository**
2. **Create a Feature Branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Commit Your Changes**
   ```bash
   git commit -m "Add amazing feature"
   ```
4. **Push to Branch**
   ```bash
   git push origin feature/amazing-feature
   ```
5. **Open a Pull Request**

### Contribution Guidelines
- Follow Arduino coding standards
- Comment your code thoroughly
- Test hardware changes before submitting
- Update documentation for new features
- Add images for hardware modifications

---

## 📚 Learning Resources

### Robotics Fundamentals
- [Arduino Official Tutorials](https://www.arduino.cc/en/Tutorial/HomePage)
- [IR Sensor Working Principle](https://www.electronicshub.org/ir-sensor/)
- [Motor Driver Basics](https://lastminuteengineers.com/l298n-dc-stepper-driver-arduino-tutorial/)

### Advanced Topics
- PID Control for Line Followers
- Sensor Fusion Techniques
- Embedded Systems Design
- PCB Design for Robotics

---

## 🏆 Acknowledgments

### Team
- **Shubham Singh** - Project Lead & Developer
- **BBDNIIT Technical Team** - Support and Guidance
- **College Faculty** - Mentorship

### Inspiration
This project was developed as part of robotics coursework at BBDNIIT, demonstrating practical applications of embedded systems and autonomous navigation.

### Special Thanks
- Arduino Community for extensive documentation
- Open-source robotics community
- All contributors and supporters

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 📞 Contact

**Shubham Singh**
- LinkedIn: [Shubham Singh](https://www.linkedin.com/in/shubham-singh-b6a586307/)
- Institution: BBDNIIT
- Year: 2nd Year B.Tech

---

## 🌟 Show Your Support

If you found this project helpful, please consider:
- ⭐ Starring the repository
- 🔄 Sharing with others
- 🐛 Reporting bugs
- 💡 Suggesting new features

---

<div align="center">

**Made with ❤️ by Shubham Singh**

*Empowering the next generation of robotics enthusiasts*

</div>