## **Sample Code**
```c
#define Sensor PB5
  int value = 0;  // variable for reading the sensor status

void setup() {
  Serial.begin(9600);
}
void loop() {
  value = analogRead(Sensor);
  Serial.println(value, DEC);
  delay(1000);
}
```