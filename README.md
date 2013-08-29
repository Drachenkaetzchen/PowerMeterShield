Power Meter Shield
==================

This is an arduino shield to measure voltage (0..10A) and current (0..30V) with a resolution of up to 16 bits (15 bits on a completely positive rail). This results in 1.2mA or 3.6mV.

Design
======

The design is based on the INA138 differential op-amp designed for current measurement, a voltage divider, and the MCP3426 16 bit I²C DAC.

Additionally, the design uses a 5V DC-DC converter and the ADUM1250 I²C isolator to give the following benefits:

* Fully isolated measurement
* Reverse polarity protection
* Short-circuit protection
* No need to have common GND with your arduino

Issues
======
Because we measure current and voltage at the same time, there will be a small error of 0.005V/A in your measurements. A relais to switch between current and voltage measurements was skipped in order to keep the costs down.

