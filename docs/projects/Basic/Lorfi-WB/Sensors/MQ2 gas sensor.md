## **Sample Code**
```c
#define Sensor PB5

void setup() {
  Serial.begin(9600);  //Set serial baud rate to 9600 bps
}
void loop() {
  int val = analogRead(Sensor);       //Read Gas value from analog 0
  Serial.println(val, DEC);  //Print the value to serial port
  delay(100);
}
```