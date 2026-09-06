Building a Laser-Based Intrusion Detection System with ESP32

I recently designed and implemented a low-cost security tripwire system using an ESP32 microcontroller, a laser transmitter module, and an LDR (Light Dependent Resistor) sensor.

System overview:
The laser module projects a continuous beam onto the LDR sensor, forming an invisible detection line. When the beam is interrupted, the LDR registers a sharp drop in light intensity on its analog output. The ESP32 continuously samples this signal via its ADC and, upon detecting the interruption, triggers a buzzer to raise an immediate alert.

Key technical aspects:

Analog signal acquisition and threshold-based triggering using the ESP32's ADC
Point-to-point wiring for a compact, breadboard-free build
Alarm latching logic to ensure the alert persists until manually reset
Sensor calibration and threshold tuning for reliable detection under varying ambient light
