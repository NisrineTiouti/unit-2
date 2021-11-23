#LED Curcuit connected to 3 buttons

![Frantic Amur-Rottis (3)](https://user-images.githubusercontent.com/89052189/143099202-961b49d4-83eb-43cd-922a-d4d751382465.png)

```.c
// code that connects each LED to a button
// The LED turns on when you press tyhe button
// The LED is off when the button is not pressed

//Define variables
int pin1 = 9;
int pin2 = 10;
int pin3 = 11;
int Button1 = 2;
int Button2 = 3;
int Button3 = 4;

// Define outputs and inputs 
void setup() {
  pinMode(Button1, INPUT);
  pinMode(Button2, INPUT);
  pinMode(Button3, INPUT);
  
  pinMode(pin1,OUTPUT);
  pinMode(pin2,OUTPUT);
  pinMode(pin3,OUTPUT);
  
  
}

// When button is high(PRESSED) the LED is HIGH(ON)
// When button is low (NOT PRESSED) the LED is LOW (OFF) 

void loop () {
  if (digitalRead(Button1) == HIGH){
   digitalWrite(pin1, HIGH); 
  }
  else{
    digitalWrite(pin1, LOW);
  }
  if (digitalRead(Button2) == HIGH){
   digitalWrite(pin1, HIGH); 
  }
  else{
    digitalWrite(pin2, LOW);
  }
  if (digitalRead(Button3) == HIGH){
   digitalWrite(pin3, HIGH); 
  }
  else{
    digitalWrite(pin3, LOW);
  }
}  

```.c
