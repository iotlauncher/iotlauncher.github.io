## **Sample Code**
```c
#define Sensor PB3

void setup() {
  Serial.begin(9600);  //Open the serial to set the baud rate as 9600bps
}
void loop() {
  int val = analogRead(Sensor);  //Connect the sensor to analog interface A0
  Serial.print("Vibration is ");
  Serial.println(val, DEC);  //Print the analog value read on serial port
  delay(100);
}
```