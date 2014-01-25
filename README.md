#### **Voltage and Current Meter Shield**

This is a shield to measure voltage (±30V) and current (±10A). It is isolated, so you can hook it up either polarity and even measure negative voltages.

#### **Usage Ideas**
- Combine this shield with an SD card shield to create a data-logging multimeter.
- Combine this shield with a WiFi-Shield to log data to the internet.
- Use the WiFi shield with a solar panel to measure how much power you harvest
- Measure the power consumption of your QuadCopter during flight

#### **Theory of Operation**

Voltage is measured using the THS4521 differential amplifier by converting a bipolar single-ended voltage into a differential voltage, which is fed into the ADC.

Current is measured via the 5mΩ shunt resistor and amplified using the INA170 high-side current shunt monitor. It is converted into a voltage and fed into the ADC.  A 1.024V reference is used to level shift the signal for the ADC so that we can measure negative currents as well (negative range: 0-1.024V and positive range 1.024V to 2.048V).

The ADC used is a MCP3426, which supports up to 16 bits of resolution and an integrated gain amplifier (1x, 2x, 4x and 8x), so if you don't need the full input range of ±30V, you can measure smaller voltages with higher resolutions. The ADC is controlled via I²C.

The ADUM1250 isolates the I²C communications and a 5V DC to DC converter isolates the power rails for the shield.

#### **Specifications**
- Voltage Measurements from -30V to +30V
- Current Measurement from -10A to +10A
- Resolution is 12, 14 or 16 bits. This affects the sample rate (Samples per Second or SPS). 15 SPS at 16 Bits, 60 SPS at 14 Bits and 240 SPS at 12 Bits.
- Digital Gain control of 1x, 2x, 4x or 8x gain
- Input Impedance: >10MΩ
- Burden Voltage: 5mV/A
- Resolution for Voltage Measurements at 16 bit: 4mV at 1x gain (±30V), 2mV at 2x gain (±15V), 1mV at 4x gain (±7.5V) and 0.5mV at 8x gain (±3.75V)
- Resolution for Current Measurements at 16 bit: 1.2mA at 1x gain (±10A), 0.6mA at 2x gain (±5A), 0.3mA at 4x gain (±2.5A) and 0.15mA at 8x gain (±1.25A)
- Works out of the box with all Arduino platforms that feature VREF, SDA and SCL pins. For older Arduino platforms, you may wire VREF to +5V and SDA/SCL to A4/A5 pins.

#### **Project History**

I have built a [solar powered router](http://felicitus.org/solarwind/) for which I have designed a voltage and current measurement board. The voltage and current meter shield evolved from that monitoring board.

I have taken great care to make this shield relatively safe; it doesn't matter which way you connect the measurement inputs - your Arduino will survive due to the isolation (unless you exceed the specified ±30V ±10A input ranges).

#### **License**

This board is licensed under the CERN OHL v1.2.
