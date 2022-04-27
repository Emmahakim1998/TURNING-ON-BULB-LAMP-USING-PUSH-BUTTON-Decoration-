# TURNING-ON-BULB-LAMP-USING-PUSH-BUTTON-Decoration-
# I. ABSTRACT 
Turning on bulb lamp using pushbutton, is arduino based project which is used for decoration.  We are going to explain in all details how it can work. This project will help for lighting all decoration-designs with only one push. The benefits of implementing our project as solution it will provide good appearance in Christmas lighting, rooms, events i.e. wedding ceremony, birthday’s party.
# II.	PROBLEM STATEMENT
The current decorations without bulb lamp are not very brilliant as we wish. And it is hard to control the ordinary lighting decoration’s design but with our project it require only one press to control or designs, the loss of trees and other vegetation for using in decoration can cause climate change, increase greenhouse gases in the atmosphere.
# III.	BLOCK DIAGRAM AND DESCRIPTION
![image](https://user-images.githubusercontent.com/103589681/164707247-b5aa9525-e481-4a25-9cf0-7524fea90116.png)
# Description
This block diagram contains many different electronic components such as push buttons, Arduino uno board, relays, lamps and AC supply.
These two push buttons are installed in parallel, the push button1 is used to start our installation with long press for one second and also the push button2 is used to stop this installation with long press for one second. The purpose of this long press is to prevent disturbance of someone who can press some of these push buttons by an accident which can disturb our decoration.
When you press on push button1 these all four lamps are lighting alternatively. There is a timing of two seconds between one lamp and each other. After alternatively all lamps are lighting at the same time, then after two seconds the system restart again.
At any time the push button2 is pressed a long one second the system will be stopped.
# IV.	CIRCUIT DIAGRAM
![image](https://user-images.githubusercontent.com/103589681/164708443-4e8294da-a950-468f-8468-9b3cf3cee853.png)
# V.	SIMULATION IN PROTEUS
![image](https://user-images.githubusercontent.com/103589681/164709486-a01427bb-a34a-44f7-b0b9-00ee7b072999.png)
# VI.	DEVELOP SOURCE CODES IN ARDUINO IDE

/*
  Button

  Turns on and off a light emitting diode(LEDs) connected to digital pin 13,,9,7,5,
  
  when pressing a pushbutton attached to pin 2.

  The circuit:
  
  - LED attached from pin 13 to ground
  - 
  LED attached from pin 9 to ground
  
  LED attached from pin 7 to ground
  
  LED attached from pin 5 to ground
  
  - Two pushbutton attached to pin 2&3 from +5V
 
  - 10K resistor attached to pin 2&3 respectively from ground*/


const int buttonPin1 = 2;// the number of the pushbutton pin

const int buttonPin2 = 3;

const int ledPin1 =  13; // the number of the LED pin

const int ledPin2 =  9;

const int ledPin3 =  7;

const int ledPin4 =  5;

// variables will change:

int buttonState1 = 0;// variable for reading the pushbutton status

int buttonState2 =0;

void setup() {
  
  // initialize the LED pin as an output:
  
  pinMode(ledPin1, OUTPUT);
  
  pinMode(ledPin2, OUTPUT);
  
  pinMode(ledPin3, OUTPUT);
  
  pinMode(ledPin4, OUTPUT);
  
  // initialize the pushbutton pin as an input:
  
  pinMode(buttonPin1, INPUT);
  
  pinMode(buttonPin2, INPUT);
}

void loop() {
  
  // read the state of the pushbutton value:
  
  buttonState1 = digitalRead(buttonPin1);
  
  buttonState2 = digitalRead(buttonPin2);

  // check if the pushbutton is pressed for 1sec. If it is, the buttonState is HIGH:
  
  if (buttonState1 ==( HIGH)) {
  
    delay(1000);
    
   if (buttonState1 ==( HIGH)) {//Nested if. to create delay of 1sec for pushbutton
    
    // turn LED on:
    
    if_1:   // Creating link to join with goto statment
    
    digitalWrite(ledPin1, HIGH);
    
    digitalWrite(ledPin2, LOW);
    
    
    digitalWrite(ledPin3, LOW);
    
    digitalWrite(ledPin4, LOW);
    
    buttonState2 = digitalRead(buttonPin2); // Updates for button state
    
    if (buttonState2 == HIGH)
    
    {digitalWrite(ledPin1, LOW);
    
    digitalWrite(ledPin2, LOW);
    
    digitalWrite(ledPin3, LOW);
    
    digitalWrite(ledPin4, LOW);
    
    goto off;
    
    }
    
    delay(2000);
    
    digitalWrite(ledPin1, LOW);
    
    digitalWrite(ledPin2, HIGH);
    
    digitalWrite(ledPin3, LOW);
    
    digitalWrite(ledPin4, LOW);
    
    buttonState2 = digitalRead(buttonPin2);
    
    if (buttonState2 == HIGH)
    
    {digitalWrite(ledPin1, LOW);
    
    digitalWrite(ledPin2, LOW);
    
    digitalWrite(ledPin3, LOW);
    
    digitalWrite(ledPin4, LOW);
    
    goto off;}
    
    delay(2000);
    
    digitalWrite(ledPin1, LOW);
    
    digitalWrite(ledPin2, LOW);
    
    digitalWrite(ledPin3, HIGH);
    
    digitalWrite(ledPin4, LOW);
    
    buttonState2 = digitalRead(buttonPin2); //Updates for button state
    
    if (buttonState2 == HIGH)
    
    {digitalWrite(ledPin1, LOW);
    
    digitalWrite(ledPin2, LOW);
    
    digitalWrite(ledPin3, LOW);
    
    digitalWrite(ledPin4, LOW);
    
    goto off;}
    
    delay(2000);
    
    digitalWrite(ledPin1, LOW);
    
    digitalWrite(ledPin2, LOW);
    
    digitalWrite(ledPin3, LOW);
    
    digitalWrite(ledPin4, HIGH);
    
    buttonState2 = digitalRead(buttonPin2);
    
    if (buttonState2 == HIGH)
    
    {digitalWrite(ledPin1, LOW);
    
    digitalWrite(ledPin2, LOW);
    
    digitalWrite(ledPin3, LOW);
    
    digitalWrite(ledPin4, LOW);
    
    goto off;}
    
    delay(2000);
    
    digitalWrite(ledPin1, HIGH);
    
    digitalWrite(ledPin2, HIGH);
    
    digitalWrite(ledPin3, HIGH);
    
    digitalWrite(ledPin4, HIGH);
    
    buttonState2 = digitalRead(buttonPin2);
    
    if (buttonState2 == HIGH)
    
    {digitalWrite(ledPin1, LOW);
    
    digitalWrite(ledPin2, LOW);
    
    digitalWrite(ledPin3, LOW);
    
    digitalWrite(ledPin4, LOW);
    
    goto off;}
    
    delay(2000);
    
    goto if_1;}}

    
    else{
      
    // turn LED off:
    
    off:
    
    digitalWrite(ledPin1, LOW);
    
    digitalWrite(ledPin2, LOW);
    
    digitalWrite(ledPin3, LOW);
    
    digitalWrite(ledPin4, LOW);
    
  }
  
}
