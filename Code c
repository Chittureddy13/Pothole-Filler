#include <Servo.h>
Servo myservo; 
const int trigPin = 9; 
const int echoPin = 8;
long int duration,inches,cm;
int pos = 0;   
int enA=3;
int enB=5;
const int in1=13;
const int in2=12;
const int in3=11;
const int in4=10;
void setup() { 
 Serial.begin(9600); 
 myservo.detach();
} 
void loop() 
{ 

 ultrasonic(0); 
 while(cm>7)
 {
   Serial.print("Pathole detected \n");
   analogWrite(enB,0);
   analogWrite(enA,0);
   servo(0);
   myservo.detach();
   ultrasonic(5);
 }
    analogWrite(enB,80);
    digitalWrite(in1,HIGH);
    digitalWrite(in2,LOW);
    analogWrite(enA,120);
    digitalWrite(in3,LOW);
    digitalWrite(in4,HIGH);
  
} 
long microsecondsToCentimeters(long microseconds)
{
  return microseconds/ 29/ 2;
}
void servo(int)
{
  myservo.attach(7);
  for (pos = 0; pos <= 90; pos += 1) { 
    myservo.write(pos);              
    delay(30);  
    break;     
   }
  for (pos =90; pos >= 0; pos -= 1) { 
    myservo.write(pos);              
    delay(30);                    
   } 
   myservo.detach();
}
void ultrasonic(int)
{
 pinMode(trigPin, OUTPUT); 
 digitalWrite(trigPin, LOW); 
 delayMicroseconds(20); 
 digitalWrite(trigPin, HIGH); 
 delayMicroseconds(20); 
 digitalWrite(trigPin, LOW); 
 pinMode(echoPin, INPUT); 
 duration = pulseIn(echoPin, HIGH); 
 cm = microsecondsToCentimeters(duration);  
 Serial.print(cm); 
 Serial.print("cm"); 
 Serial.println(); 
 delay(500); 
}
