## **Sample Code**
```c
///Arduino Sample Code
#define Sensor PB5

void setup() {
  Serial.begin(9600);
}
void loop() {
  int value = analogRead(temt6000Pin);
  Serial.println(value);
  delay(100); //only here to slow down the output so it is easier to read
}
```