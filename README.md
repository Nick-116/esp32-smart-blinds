#### Please be aware, this project is still in developement!

<img width="854" height="701" alt="Screenshot 2025-08-16 at 12 31 40 AM" src="https://github.com/user-attachments/assets/5d671300-07d9-4135-8769-cd3b3bce0e89" />

# esp32-smart-blinds
An ESP32-powered controller for 2-inch slat blinds. The system provides automated control and real-time feedback while still allowing manual adjustment of the blinds without damaging the motor or mechanism.

All of the products in this category cant lift a blind that heavy, and cant be moved manually without screwing them up. I designed this to fix both of those problems (and to save me $180 a blind lol).

## Cost
I built each of my blind controllers for around $25 each, including PCB assembly by JLCPCB. I did buy them in groups of 10 though.

## Features
- ESPHome Integration – fully compatible with Home Assistant and ESPHome for seamless automation, scheduling, and remote control.
- Accurate Angle Measurement – uses a magnetic encoder (AS5600) to continuously track the real position of the slats in 0–360° resolution.
- Human-Safe Design – blinds can still be moved by hand, and the system updates itself with the new position in real time instead of fighting the user.
- Smooth Motor Control – a DRV8871 motor driver controls a 12 V DC motor, providing reliable torque while keeping noise low.
- Compact PCB – custom 50×30 mm board integrates ESP32-C3, motor driver, power regulation, and expansion GPIO for extra buttons or sensors.
- Dual Power Input – supports 12 V operation for daily use, with USB-C available for firmware flashing and debugging.
- Status & Debug Outputs – onboard LED indicators, plus live telemetry (angle, magnitude, and magnet status) exposed via ESPHome sensors.

How It Works
	1.	The ESP32 runs ESPHome, connecting the blind to Home Assistant.
	2.	A magnetic encoder precisely measures shaft position, so the software always knows the blind angle.
	3.	When a control command is given (e.g., “open blinds 50%”), the DC motor driver turns the motor until the target angle is reached.
	4.	If someone physically moves the blinds, the encoder detects it, updates the system state, and prevents damage by not forcing the motor.

