# Flame Sensor using Lorfi-W

# Description

This flame sensor is designed to detect fire or light sources with wavelengths ranging from 760nm to 1100nm. It is especially useful in fire-fighting robot competitions, where it acts as the robot’s "eyes" to locate the source of a flame.

# Specification

- Supply Voltage: 3.3V to 5V
- Detection range: 20cm (4.8V) ~ 100cm (1V)
- Rang of Spectral Bandwidth: 760nm to 1100nm
- Operating temperature: -25℃to 85℃
- Interface: digital
- Size: 44*16.7mm
- Weight: 4g

## Hardware Setup

Connect the D0 pin of module to Digital Input of the Lorfi board, connect the GND pin to GND port, VCC pin to 5V port.

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
#define Sensor PB5
int State = 0;  // variable for reading the pin status

void setup() {
  Serial.begin(9600);
  // initialize the pushbutton pin as an input:
  pinMode(Sensor, INPUT);
}
void loop() {
  // read the state of the value:
  State = digitalRead(Sensor);
  if (State == HIGH) {
    Serial.println("Fire detected!");
  } else if(State == LOW) {
    Serial.println("No Fire detected!");
  }
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ
