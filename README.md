# esp32-smart-blinds
the ESP32 Smart Blinds project started becuase I wanted a way to open and close my blinds using Home Assistant, that was reliable and powerful. My blinds are very large (72 inch x 2 inch slats) so I needed a powerful motor. This design works with many different sizes of motors, anywhere from nema 8 steppers all the way to geared nema17s.

This project is in development. When the project is finished, I will post all STLs and pcb designs here

## Cost
Altogether this project costs around $20 per blind but depending on the motor you use and where you get it from, it can be much cheaper. I use a nema 17 1:5 geared stepper motor, which works well for my medium sized blinds, and will work good in most cases. This costs around $10 on aliexpress. If you have lighter blinds you can get a normal nema 17 stepper, which costs around $5 on aliexpress, or $10 on amazon.


An ESP32-powered controller for 2-inch slat blinds, designed and built by me. The system provides automated control and real-time feedback while still allowing manual adjustment of the blinds without damaging the motor or mechanism.

##Features
	•	ESPHome Integration – fully compatible with Home Assistant and ESPHome for seamless automation, scheduling, and remote control.
	•	Accurate Angle Measurement – uses a magnetic encoder (AS5600) to continuously track the real position of the slats in 0–360° resolution.
	•	Human-Safe Design – blinds can still be moved by hand, and the system updates itself with the new position in real time instead of fighting the user.
	•	Smooth Motor Control – a DRV8871 motor driver controls a 12 V DC motor, providing reliable torque while keeping noise low.
	•	Compact PCB – custom 50×30 mm board integrates ESP32-C3, motor driver, power regulation, and expansion GPIO for extra buttons or sensors.
	•	Dual Power Input – supports 12 V operation for daily use, with USB-C available for firmware flashing and debugging.
	•	Status & Debug Outputs – onboard LED indicators, plus live telemetry (angle, magnitude, and magnet status) exposed via ESPHome sensors.

🚀 How It Works
	1.	The ESP32 runs ESPHome, connecting the blind to Home Assistant or any MQTT-based system.
	2.	A magnetic encoder precisely measures shaft position, so the software always knows the blind angle.
	3.	When a control command is given (e.g., “open blinds 50%”), the motor driver turns the motor until the target angle is reached.
	4.	If someone physically moves the blinds, the encoder detects it, updates the system state, and prevents damage by not forcing the motor.

🛠️ Use Cases
	•	Integrate blinds into smart home automations (e.g., open at sunrise, close when it gets hot).
	•	Maintain exact blind angles for energy efficiency and comfort.
	•	Allow hybrid control (manual or automated) without conflict.
