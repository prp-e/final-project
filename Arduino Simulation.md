# Arduino Simulation and Code 

## Arduino Schematics 

![Arduino Test](./Arduino%20-%20First%20Test.bmp)

## The Code 
This is the code : 

```c 

#define GREEN_LED 12
#define RED_LED 13
#define DHT11_PIN 7 

#include <dht.h>

dht DHT; 

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
  int chk = DHT.read11(DHT11_PIN); 
  Serial.print("Temp. : "); 
  Serial.println(DHT.temperature); 
  Serial.print("Humid. : "); 
  Serial.println(DHT.humidity); 
  delay(5000);

}
``` 
In this code, we have different parts. The parts will be explained below. 

### Part 1 : Macros 

```
#define GREEN_LED 12
#define RED_LED 13
#define DHT11_PIN 7 
``` 
These three macros define which pins are used for Green LED, Red LED and DHT11 sensor. 

### Preprocessors 

```
#include <dht.h> 
``` 
This is the library used for DHT sensors. Also this line : 

```
dht DHT
``` 
makes an object of DHT type. 

### viod setup() 

```
  pinMode(GREEN_LED, OUTPUT); 
  pinMode(RED_LED, OUTPUT); 
  Serial.begin(9600); 
``` 

First two lines, make 2 pins outputs, third line is responsible for starting a serial communication with the computer. 

```
  digitalWrite(RED_LED, HIGH); 
  delay(333); 
  digitalWrite(RED_LED, LOW); 
  delay(333); 
  digitalWrite(RED_LED, HIGH); 
  delay(333); 
  digitalWrite(RED_LED, LOW); 
  delay(300);
  digitalWrite(GREEN_LED, HIGH);
``` 
These lines are for user to make sure circuit is on service. The red LED blinks 3 times then Green one stays on. It means circuit is okay and device works well. 