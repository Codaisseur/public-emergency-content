---
title: Arduino Blinking and Button input
description: Make a light blink and read button input through code.
---

# Arduino Blinking and Button input

With the Arduino we can read and write electronic signals through code. We can control a LED through code and read if a button is pressed.

## Basics

When you first open the Arduino IDE it provides you with a blank project, that is called a `sketch'.

You see 2 functions

The first is the `setup` function.
```C
void setup() {
  // put your setup code here, to run once:
}
```
The `setup` functions runs only once when the arduino is powered up. Here you put all your initialization code that is needed.

The second function is the `loop` function.

```C
void loop() {
  // put your main code here, to run repeatedly:
}
```

The `loop` function will we called in a loop as fast as possible. So slow code in here will make your Arduino run slower.

## Blink

Don't worry about wiring up the Arduino to the breadboard for now. That is already done.

- Open the `Blink` example sketch. `File` > `Examples` > `01.Basics` > `Blink`.
- Read the tutorial on [https://www.arduino.cc/en/Tutorial/Blink](https://www.arduino.cc/en/Tutorial/Blink)

### Modify the program
- Modify the program such that is blinks an SOS signal. `short short short long long long short short short`
- Compile your program. Click Verify.
- Connect your computer to the Arduino and click Upload.
- Verify that is works.

## Button
- Open the `Button` example sketch. `File` > `Examples` > `02.Digital` > `Button`.
- Read the tutorial on [https://www.arduino.cc/en/Tutorial/Button](https://www.arduino.cc/en/Tutorial/Button)

### Modify the program
- Modify the buttonPin to `3`.
- Modify the ledPin to `13`.
- Compile your program. Click Verify.
- Connect your computer to the Arduino and click Upload.
- Verify that is works.

## Button with Debouncing
Now you should be able to find your way through the examples.
- Create a Button with debouncing logic by following the following tutorial [https://www.arduino.cc/en/Tutorial/Debounce](https://www.arduino.cc/en/Tutorial/Debounce)
- Remember the button is connected to pin `3`

### Modify the program
- Modify the program such that is sends an SOS signal when the button was pressed once and test this.
- Refactor your code to make it more procedural, extract functions where needed.