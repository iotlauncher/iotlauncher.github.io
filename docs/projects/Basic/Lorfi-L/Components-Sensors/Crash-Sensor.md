# Crash Sensor using Lorfi-W

# Description

The crash sensor, also referred to as an electronic switch, is a digital on/off input module commonly used in basic electronics education.

Through programming, it can be used to control devices such as lights, sound modules, or to implement button-selection functions on an LCD display.

For example, you can create a collision-activated flasher using this sensor along with a built-in LED. By connecting the sensor to pin PB5, the LEDs on both the main board and the sensor module will light up simultaneously when a collision is detected.

# Specification

- Type: Digital on/off input module
- Use: Detects collisions for basic electronics and robotics projects
- Applications:
  - Ideal for Arduino and 4WD robot platforms
  - Can trigger lights, sounds, or LCD functions
  - Example: Connect to pin 3; onboard LED lights up on collision

- Features:
  - Outputs LOW on collision, HIGH otherwise
  - Built-in indicator LED (ON = collision)
  - M3 mounting hole for easy installation
  - Uses 3P sensor cable for connection

## Hardware Setup

Positive pin (+): connect to 3v-12v power supply
Negative pin (-): connect to GND
Signal pin (S): connect to High-low level output

Connect the S pin of module to Digital Input of the Lorfi board, connect the negative pin to GND port, positive pin to 5V port.

#### Using directly Lorfi-L

You can find complete [Lorfi-L IO pinout here].

*MIGHT NEED TO ADD NOTES ON POWER REQUIREMENTS, PIN CONSIDERATIONS, ETC.*

#### Using Lorfi Interface board

You can find complete guide for [Lorfi Interface here].

*MIGHT NEED TO ADD NOTES ON POWER REQUIREMENTS, PIN CONSIDERATIONS, ETC.*

## Software Setup

Lorfi-L is based on RAK3172 LoRaWAN module. This must be added to Arduino IDE.

Here's the guide [how to add RAK3172 on your Arduino IDE].

Once RAK3172 is added, you can now select it from the board selection.

*ADD HERE IMAGE OF RAK3172 ON BOARD SELECTION IN ARDUINO IDE.*

If failing, test the UART connection by checking the version. Use `AT+VER=?` command with baud rate of 115200. In case of MCU brick, revive the RAK3172 by following this [guide from RAKwireless](https://learn.rakwireless.com/hc/en-us/articles/26687606549911-How-To-Guide-STM32CubeProgrammer-for-RAK-Modules).

## **Sample Code**
```c
#define Sensor PB5  // set pin for collision sensor

int sensorState;  // set digital variable val
void setup() {
  pinMode(Sensor, INPUT);  // set collision sensor as input
}
void loop() {
  sensorState = digitalRead(Sensor);
  if (sensorState == LOW)            // when collision sensor detects a signal, it prints its instance.
  {
    Serial.println("Shock Detected!");
    delay(500);
  } else {
    Serial.println("Shock Not Detected!");
    delay(500);
  }
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ
