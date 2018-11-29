---
title: Arduino installation
description: Install the Arduino IDE and required libraries
---

# Arduino installation

Arduino has an easy to setup development environment.
- Install the Arduino Desktop IDE for your platform. You can download and install that here: [https://www.arduino.cc/en/Main/Software](https://www.arduino.cc/en/Main/Software). See also: [https://create.arduino.cc/projecthub/Arduino_Genuino/getting-started-with-the-arduino-desktop-ide-623be4](https://create.arduino.cc/projecthub/Arduino_Genuino/getting-started-with-the-arduino-desktop-ide-623be4)

- Open the Arduino IDE, and click the Verify button. This compiles your empty code. No errors should appear.

## Additional libraries
- For our our purposes we need to install the One Wire library for later use.
- Goto `Sketch` > `Include library` > `Manage libraries` and install the `onewire` version 2.3.4 library.


## Testing
- Select the Arduino Yun under `tools`->`boards`.
- Please connect your computer to the arduino device and check if you see the board under `tools`->`port`.
