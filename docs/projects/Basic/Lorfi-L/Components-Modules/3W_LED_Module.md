# 3W LED Module using Lorfi-L

# Description
This LED module features high brightness, thanks to its 3W lamp beads. It's well-suited for Arduino projects and is especially useful in robotics or search and rescue platforms.

For instance, smart robots can utilize this module for lighting purposes. However, for safety reasons, avoid shining the LED directly into human eyes.

# Specification

- Color temperature: 6000~7000K
- Luminous flux: 180~210lm
- Current: 700~750mA
- Power: 3W
- Light angle: 140 degree
- Working temperature: -50~80℃
- Storage temperature: -50~100℃
- High power LED module, controlled by IO port microcontroller
- IO Type: Digital
- Supply Voltage: 3.3V to 5V
- Size: 40x28mm
- Weight: 6g


## Hardware Setup

#### Using directly Lorfi-L

You can find complete [Lorfi-L IO pinout here].

*MIGHT NEED TO ADD NOTES ON POWER REQUIREMENTS, PIN CONSIDERATIONS, ETC.*

#### Using Lorfi Interface board

You can find complete guide for [Lorfi Interface here].

![Ultrasonic Sensor Connection]({{ '/assets/images/ultrasonic-connection.png' | relative_url }})

*MIGHT NEED TO ADD NOTES ON POWER REQUIREMENTS, PIN CONSIDERATIONS, ETC.*

## Software Setup

Lorfi-L is based on RAK3172 LoRaWAN module. This must be added to Arduino IDE.

Here's the guide [how to add RAK3172 on your Arduino IDE].

Once RAK3172 is added, you can now select it from the board selection.

*ADD HERE IMAGE OF RAK3172 ON BOARD SELECTION IN ARDUINO IDE.*

If failing, test the UART connection by checking the version. Use `AT+VER=?` command with baud rate of 115200. In case of MCU brick, revive the RAK3172 by following this [guide from RAKwireless](https://learn.rakwireless.com/hc/en-us/articles/26687606549911-How-To-Guide-STM32CubeProgrammer-for-RAK-Modules).

## **Sample Code**
```c
#define LED PB5
void setup() {
  // initialize digital pin as an output.
  pinMode(LED, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(LED, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(1000);              // wait for a second
  digitalWrite(LED, LOW);    // turn the LED off by making the voltage LOW
  delay(1000);              // wait for a second
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ

1. Why button is not responding?
- Check if the header pins are properly connected

2. Why LED is dim?
- Check if you are using 5V or 3.3V
