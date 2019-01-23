# ESP Simulation (First attempts)

## ESP pinout 

![Pinout](./esp-pinout.png)

## New libraries used 

1. [Adafruit Sensor Library](https://roboindia.com/tutorials/admin/source32145898/tutorials%20Images/nodeMCU_arduino/dht-11-plain/Adafruit_Sensor-master.zip)
2. [ESP8266 library for DHT11](https://roboindia.com/tutorials/admin/source32145898/surbhi/Arduino%20UNO/DHT_sensor_library.zip)

## The code with new modifications 

NOTE: Code is the same as Arduino Uno board, with a little modification! 

```c 

#define GREEN_LED 12
#define RED_LED 13
#define DHT11_PIN 5
#define DHTTYPE DHT11 

#include "DHT.h"
 
DHT dht(DHT11_PIN, DHTTYPE); 

void setup() {
  // put your setup code here, to run once:
  pinMode(GREEN_LED, OUTPUT); 
  pinMode(RED_LED, OUTPUT); 
  Serial.begin(9600); 
  Serial.println("Hello! This is DHT11 test"); 
  Serial.println("-------------------------");
  // Just a little bit of starting :))
  digitalWrite(RED_LED, HIGH); 
  delay(333); 
  digitalWrite(RED_LED, LOW); 
  delay(333); 
  digitalWrite(RED_LED, HIGH); 
  delay(333); 
  digitalWrite(RED_LED, LOW); 
  delay(300);
  digitalWrite(GREEN_LED, HIGH);
  
}

void loop() {
  // put your main code here, to run repeatedly:
  float h = dht.readHumidity() ;
  float t = dht.readTemperature() ;
  Serial.print("Temp. : "); 
  Serial.println(t); 
  Serial.print("Humid. : "); 
  Serial.println(h); 
  delay(5000);

}
``` 