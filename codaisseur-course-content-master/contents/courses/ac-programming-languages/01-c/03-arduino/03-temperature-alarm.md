---
title: Arduino temperature alarm
description: Program the Arduino to monitor the temperature
---

# Arduino temperature alarm

## Reading a value from the temperature sensor

We will use a onewire Temperature sensor. OneWire is an electronics communication protocol that allows multiple devices to communicate digitally over 1 wire. Don't worry too much about the specifics, we will use a library that handles the communication for us.

- Open the `DS18_20_Temperature` example sketch. `File` > `Examples` > `Examples from custom libraries` > `OneWire` > `DS18_20_Temperature`.
- Modify the pin number to `2`. (The sensor is connected to pin 2).
`OneWire  ds(2);`

- Verify and upload the program to the Arduino
- Open the `Tools`->`Serial Monitor` while connected and check the output. You should see the printouts from the `Serial.print` calls.

### Modify the program
- Modify the program such that the LED on pin 13 will blink when the temperature is above a certain threshold. (You can increase the temperature by holding the sensor in your hand.)
- You only need to read the temperature sensor once a second
- Refactor the code to make it more readable and procedural
- *Extra: Make the LED blink speed dependant on the temperature.*