
Overview
The Smart Toilet System is an automated sanitation and safety solution designed for public and private restrooms. It uses an Arduino Mega as the primary controller and integrates ultrasonic sensors, relay-controlled locks, cleaning pumps, a GSM module for emergency communication, an MP3 voice guidance module, and an ESP32 for mobile application support and external accessibility features. The system is designed to provide automated occupancy detection, controlled access, cleaning cycles, emergency notifications, and navigation assistance for visually impaired users.

Key Features

1. Automated Occupancy Detection

Two ultrasonic sensors are used:

* Entrance ultrasonic sensor detects a person approaching or entering the toilet.
* Commode ultrasonic sensor detects when a person sits on or leaves the commode seat.
  The system distinguishes between idle, occupied, and exit states.

2. Door Access Control

A solenoid lock controlled by a relay automatically manages door locking and unlocking:

* When vacant, the green light is enabled, and the door remains unlocked.
* When occupied, the red light is enabled, and the door locks after the user enters.
* After the user exits, the system unlocks the door briefly and then starts the cleaning cycle.

3. Cleaning Automation

Two cleaning modes are implemented:

* Commode cleaning pump runs for 30 seconds after the user leaves the commode.
* Full bathroom cleaning pump runs for 30 seconds once the user exits through the door.

4. Emergency SOS Function

An SOS button inside the toilet allows the user to request help:

* Pressing the SOS button sends three SMS alerts to a predefined emergency contact using the GSM module.

5. Blind Navigation Assistance

The system includes:

* A navigation button inside the toilet for visually impaired users.
* An MP3 module and speaker that play voice instructions, guiding the user toward the commode and the SOS button.
* An external navigation request button connected to the ESP32, allowing blind users outside to request audio instructions before entering.

6. ESP32 External Status Display

The ESP32 receives occupancy status from the Arduino Mega and drives:

* External red and green LEDs to indicate availability of the toilet.
* A navigation button for visually impaired users at the entrance.
  The ESP32 can also be expanded for mobile app integration using Wi-Fi or Bluetooth communication.

System Workflow

1. When idle, the toilet displays a green LED and the door remains unlocked.
2. When a person approaches the entrance sensor, the system waits for entry and locks the door 5 seconds after the user enters.
3. The commode ultrasonic sensor detects when the user sits and stands up.
4. After leaving the commode, the door unlocks after 5 seconds, and the commode cleaning pump activates.
5. When the user approaches the exit at the entrance sensor, the door locks temporarily and the full cleaning cycle runs.
6. After cleaning, the system returns to idle mode and displays the green LED.
7. Pressing the SOS button triggers emergency SMS alerts.
8. Pressing the navigation button triggers audio guidance for visually impaired users.
9. The ESP32 module continuously displays the occupied or free status and handles external navigation requests.

Hardware Components

Controllers

* Arduino Mega 2560 (main controller)
* ESP32 (external indicator and mobile application interface)

Sensors and Modules

* Ultrasonic Sensor (Entrance)
* Ultrasonic Sensor (Commode area)
* GSM module (for SOS alerts)
* DFPlayer Mini MP3 module
* Speaker for audio instructions

 Actuators and Outputs

* Solenoid lock with relay driver
* Commode cleaning pump (relay)
* Full bathroom cleaning pump (relay)
* Red and green LED indicators
* External red and green LEDs via ESP32

Input Buttons

* SOS emergency button
* Internal blind navigation button
* External blind navigation button via ESP32

 Applications

* Public restrooms in bus stations, railway stations, and airports.
* Smart sanitation units in rural development projects.
* Disabled-friendly restrooms in hospitals and campuses.
* IoT-based automated restroom systems in smart city environments.

