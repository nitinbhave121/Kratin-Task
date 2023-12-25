
# Automated alarm system for Overloaded Diaper and pads

This project aims to make an efficiet solution for aged persons as well as children or bedridden patients as they are not in good health condition.Sometimes aged persons have dont idea about their health condition. In such condition this project will definitely help by detecting the wetness in diaper giving alarm to the care taker.
        


## Technology used
Internet of Things
Arduino Platform
## Software and Hardware used
Ardunio UNO , Sensor , buzzer , Jumper wires , LEDs , Cable , Power Supply , Arduino IDE
## Working
When we supply power to the circuit,green LED will blow which indicates circuit is ready to work.When We inserted the circuit in Diaper or pads then when the sensor in the circuit detect the presence of moisture then it will give the alarm and Red LED will blow.So care taker will get the notification on their mobile phones by using Blynk software

## Program code for Arduino
const int analogInPin = A0;
int sensorValue = 0;

void setup() {
  // declare pin  to be an output:
  pinMode(15, OUTPUT);
  Serial.begin(9600);
}

// the loop routine runs over and over again forever:
void loop() {
  sensorValue = analogRead(analogInPin);
  Serial.print("sensor = ");
  Serial.print(sensorValue);
  Serial.print("\n");
  delay(2);

  if (sensorValue >= 100 && sensorValue <= 600) {
    digitalWrite(15, HIGH);
    delay(100);
  } else {
    digitalWrite(15, LOW);
    delay(100);
  }
}