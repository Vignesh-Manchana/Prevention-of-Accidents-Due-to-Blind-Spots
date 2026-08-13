Prevention of Accidents Due to Blind Spots

📌 Project Overview

Prevention of Accidents Due to Blind Spots is an Arduino-based road safety system designed to reduce the risk of accidents on curved, narrow, and mountainous roads where drivers have limited visibility of approaching vehicles.

The system uses an Arduino Uno, HC-SR04 ultrasonic distance sensor, I2C LCD display, and red/green LED indicators. The ultrasonic sensor detects an approaching object, while the LCD displays distance and estimated speed information. The LED indicators provide a quick visual warning to the driver.

The project was tested using Tinkercad simulation and demonstrated using a physical prototype.

🎯 Problem Statement

Mountain roads, narrow roads, sharp curves, and T-junctions can create blind spots where drivers cannot see vehicles or obstacles approaching from the other side.

Limited visibility combined with vehicle speed can reduce the driver's reaction time and increase the possibility of collisions or vehicles leaving the road.

This project proposes a smart road safety system that detects approaching vehicles and provides real-time visual and display-based warnings to drivers.

💡 Proposed Solution

The proposed system uses an ultrasonic sensor to detect an approaching vehicle/object.

Working

The HC-SR04 ultrasonic sensor sends an ultrasonic pulse.

The reflected signal is received by the sensor.

Arduino calculates the distance of the detected object.

Two distance measurements are used to estimate the object's speed.

The LCD displays distance and speed information when an object is detected.

A red LED indicates that an object is within the configured detection threshold.

A green LED indicates a clear path.

🛠️ Hardware Components

Arduino Uno

HC-SR04 Ultrasonic Distance Sensor

16×2 I2C LCD Display

Red LED

Green LED

Resistors

Breadboard

Connecting wires

💻 Software and Tools

Arduino IDE

Tinkercad Circuits

C/C++ (Arduino programming)

Arduino Libraries

#include <Wire.h>
#include <LiquidCrystal_I2C.h>

🔌 Pin Connections

The following connections correspond to the Arduino code included in this repository:

Component

Arduino Pin

HC-SR04 TRIG

D8

HC-SR04 ECHO

D9

Red LED

D2

Green LED

D3

I2C LCD SDA

A4

I2C LCD SCL

A5

LCD VCC

5V

LCD GND

GND

HC-SR04 VCC

5V

HC-SR04 GND

GND

⚙️ Working Principle

The HC-SR04 measures the distance between the sensor and an object using ultrasonic waves.

The distance is calculated using:

Distance = (Time × 0.034) / 2

The division by 2 accounts for the ultrasonic signal travelling to the object and returning to the sensor.

The project takes two distance measurements and estimates speed from the change in distance over the elapsed time.

🚦 LED Indication

The current Arduino program uses a 35 cm threshold.

Condition

Red LED

Green LED

LCD

Distance < 35 cm

ON

OFF

Distance + Speed

Distance ≥ 35 cm

OFF

ON

Clear Path Ahead

Note: The threshold is configured in the Arduino code and can be changed according to the simulation or prototype requirements.

🖥️ Tinkercad Simulation

The project was simulated using Tinkercad Circuits. The simulation includes the Arduino, ultrasonic sensor, LCD display, and LED indicators.

Tinkercad Link

Add your Tinkercad share link here:

YOUR_TINKERCAD_LINK

📊 Testing and Results

The project was tested under different vehicle-detection scenarios.

Scenario 1 — Vehicle Detected

When an object/vehicle is detected within the configured threshold:

Red LED turns ON.

Green LED turns OFF.

LCD displays distance.

LCD displays estimated speed.

Scenario 2 — No Vehicle Detected

When the detected distance is outside the configured threshold:

Red LED turns OFF.

Green LED turns ON.

LCD displays "Clear Path Ahead".

The project report also describes testing under both-side detection, single-side detection, and no-detection scenarios.
