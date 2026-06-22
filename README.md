# Line-Following-Robot-with-Obstacle-Detection-Using-Arduino

## 📌 Project Overview

This project implements an autonomous Line Following Robot using an Arduino UNO, 3 IR sensors, L298N Motor Driver, and 4-wheel robot chassis. The robot follows a predefined black line and adjusts its movement based on the position of the line detected by the sensors.

The system uses three IR sensors (Left, Middle, Right) to continuously monitor the track and control the robot's direction. The robot can move forward, turn left, turn right, and perform sharp turns when necessary.

## 🎯 Features
 
 > Autonomous line following
 > Three-sensor line detection
 > Forward movement control
 > Left and right turning
 > Sharp corner handling
 > PWM-based motor speed control
 > Real-time sensor monitoring through Serial Monitor
 > Suitable for educational robotics and AGV demonstrations

## 🛠 Hardware Components
 
  Component	                     Quantity
Arduino UNO	                        1
L298N Motor Driver	                1
IR Sensor Module	                  3
DC BO Motors	                      4
4-Wheel Robot Chassis	              1
Battery Pack	                      1
Jumper Wires	                As Required

## 🔌 Circuit Connections
IR Sensors

Sensor	            Arduino Pin
Left IR	                D2
Middle IR	              D4
Right IR	              D3
VCC	                    5V
GND	                   GND

## L298N Motor Driver
L298N Pin	         Arduino Pin
ENA	                    D5
IN1                    	D8
IN2                    	D9
IN3	                    D10
IN4	                    D11
ENB	                    D6

## Motors

  Left Side Motors → OUT1 & OUT2
  Right Side Motors → OUT3 & OUT4

## ⚙️ Working Principle
 1. IR sensors continuously monitor the line.
 2. Arduino reads sensor outputs.
 3. Based on sensor values:
     Middle sensor detects line → Move Forward
     Left sensor detects line → Turn Left
     Right sensor detects line → Turn Right
     Multiple sensors detect line → Sharp Turn
 4. Motor driver controls wheel movement accordingly.
 5. The process repeats continuously for autonomous navigation.

## 🧠 Sensor Logic

Assumption used in this project:

Surface	Sensor          Output

Black Line	           HIGH (1)
White Surface	          LOW (0)

## Movement Logic

Left	    Middle	    Right	      Action
  0	        1	         0	        Forward
  1	        0	         0	        Turn Left
  0	        0	         1	        Turn Right
  1	        1	         0	        Sharp Left
  0	        1	         1	        Sharp Right
  1	        1	         1	        Forward
          Others	-	-	Stop

          
