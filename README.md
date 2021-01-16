# WaterFlowMeter
Example of connecting a Sensus 620 water flow meter to home automation
The goals was to link the flow of water to a Home Automation system. Domoticz was used but that could be HomeAssistant as well.

# Hardware
- [ ] NodeMCU V3 from Lolin
- [ ] Inductive sensor, measures the presence of metal in the spinning disc indicating the liters
- [ ] 12 Volt 2Amp switching power supply
- [ ] Breadboard, wires, Resistors, capacitor
- [ ] 2 basic diodes
- [ ] BC550 transistor
- [ ] Metal strip with hole to mount the sensor in
- [ ] Tire wraps to strap the metal to the watermeter

# Schematic
After a bit of tinkering this was the end result:
![Schematic](https://github.com/plando2act/WaterFlowMeter/blob/main/Schematic.PNG)
Things to explain:
- The Vin pin should be able to deal with 16 Volt.. but I've seen comments on it that it can break the board. That is why 2 Diodes were added to lower the voltage at Vin with 2 x 0.6 Volt
- Using a general purpose BC550 worked well. Measurements on the voltages and testing with metal to create pulses gave the resistor values. Note that the sensor voltage will destroy the NodeMCU input if higher than 3.3 Volt
- By Using this sensor, it would not rely on reflection of Infra Red light but use the metal disk in the spinning meter. It indicates 1 liter used with one turn.
![Sensor](https://github.com/plando2act/WaterFlowMeter/blob/main/Proximity%20sensor.PNG)

# Software
EasyESP combined with the NodeMCU is a very easy way to connect sensors over WiFi to your home automation.

# Test Setup
![Setup](https://github.com/plando2act/WaterFlowMeter/blob/main/1.jpg)
Note that the sensor is positioned off-center of the spinning indicator. Otherwise it does not create pulses but 'sees' the metal all the time.
![View](https://github.com/plando2act/WaterFlowMeter/blob/main/2.jpg)

# PCB 
With EasyEDA a PCB was made. Never used it but in 2 hours including learning curve, the board was ordered.
![PCB](https://github.com/plando2act/WaterFlowMeter/blob/main/PCB.PNG)
I did use KiCAD before but this was also really easy. The software knows a lot of components and footprints.
