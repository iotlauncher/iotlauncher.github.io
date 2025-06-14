# PIR Motion Sensor using Lorfi-L

# Description

The pyroelectric infrared motion sensor detects infrared radiation emitted by moving people or animals and produces a corresponding switch signal. It's suitable for various applications involving human motion detection. Traditional pyroelectric infrared sensors typically rely on a separate infrared detector, dedicated chip, and complex circuitry, resulting in larger size, more complicated design, and reduced reliability.

This updated version, designed specifically for Arduino, features an all-in-one digital pyroelectric infrared sensor. It offers a more compact form factor, improved reliability, lower power consumption, and a simplified circuit, making it easier to integrate into projects.

# Specification

- Input Voltage: 3.3 ~ 5V, Maximum for 6V
- Working Current: 15uA
- Working Temperature: -20 ~ 85 ℃
- Output Voltage: High 3V, Low 0V
- Output Delay Time (High Level): About 2.3 to 3 Seconds
- Detection Angle: 100 °
- Detection Distance: 7 meters
- Output Indicator LED (if output HIGH, it will be ON)
- Limit Current for Pin: 100mA
- Size: 30*20mm
- Weight: 4g

## Hardware Setup

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
#define Sensor PB5
#define Led PB3

void setup()
{
  pinMode(Sensor,INPUT);
  pinMode(Led,OUTPUT);
  Serial.begin(9600);
}
void loop()
{
  byte state = digitalRead(Sensor);
  digitalWrite(Led,state);
  if(state == 1){
    Serial.println("Somebody is in this area!");
  }else if(state == 0){
    Serial.println("No one!");
    delay(500);
  }
}

```

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ
