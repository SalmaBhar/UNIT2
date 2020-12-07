```cpp
// include the library code:
#include <LiquidCrystal.h>
int index = 0; 
// add all the letters and digits to the keyboard
String keyboard[]={"SEND", "DEL","A", "B", "C", "D","E","F","G","H","I","J","K","L","M","N","O","P","Q","R","S","T","U","V","W","X","Y","Z"};
String text = "";
int numOptions = 28;

// definitions of components
int led=10;
int btn_right=2;
int btn_left=3;
  
// initialize the library with the numbers of the interface pins
LiquidCrystal lcd(12, 11, 5, 4, 9, 8);

void setup() {
  // set up the LCD's number of columns and rows:
  lcd.begin(16, 2);
  Serial.begin(9600);
  // Print a message to the LCD.

  // These two commands create interruptions for the buttons.
  // Interruptions are a way of telling the arduino to pay 
  // attention to specific events, in this case the buttons
  attachInterrupt(0, changeLetter, RISING);//button A in port 2
  attachInterrupt(1, selected, RISING);//button B in port 3
  pinMode(13, OUTPUT);
}

void loop() {
  // set the cursor to column 0, line 1
  // (note: line 1 is the second row, since counting begins with 0):
  lcd.clear();
  lcd.setCursor(0, 0);
  lcd.print(keyboard[index]);
  lcd.setCursor(0, 1);
  lcd.print(text);
  delay(100);
}

//This function changes the letter in the keyboard
void changeLetter(){
 	index++;
//check for the max row number
	if(index==numOptions){
		index=0; //loop back to first row
	} 
}

//this function adds the letter to the text or send the msg
void selected(){
  String key = keyboard[index];
  if (key == "DEL")
  {
      int len = text.length();
      text.remove(len-1);
  }
  else if(key == "SEND")
  {
      En2Morse();
  }
  else{
      text += key;
  }
      index = 0; //restart the index

}

void dash(){
  	Serial.println("sending a dash");
	digitalWrite(led, HIGH);
    Serial.println("led on");
	delay(2000);
    digitalWrite(led, LOW);
    Serial.println("led off");
	delay(2000);
}

// definition of the dash and dot functions for the Morse Language
void dot(){
    Serial.println("sending a dot");
	digitalWrite(led, HIGH);
    Serial.println("led on");
	delay(1500);
	digitalWrite(led, LOW);
    Serial.println("led off");
	delay(1500);
}

// equivalent of the English alphabet in Morse Code
void En2Morse(){
  Serial.print(text);
  for(int i=0; i<text.length(); i++){
    if(text[i]=='A'){
    dot();
    dash();}    
    else if(text[i]=='B'){
    dash();
    dot();
    dot();
    dot();}
    else if(text[i]=='C'){
    dot();
    dot();
    dot();}
    else if(text[i]=='D'){
    dash();
    dot();
    dot();}
    else if(text[i]=='E'){
    dot();}
    else if(text[i]=='F'){
    dot();
    dash();
    dot();}
    else if(text[i]=='G'){
    dash();
    dash();
    dot();}
    else if(text[i]=='H'){
    dot();
    dot();
    dot();
    dot();}
    else if(text[i]=='I'){
    dot();
    dot();}
    else if(text[i]=='J'){
    dash();
    dot();
    dash();
    dot();}
    else if(text[i]=='K'){
    dash();
    dot();
    dash();}
    else if(text[i]=='L'){
    dot();
    dash();
    dot();
    dot();}
    else if(text[i]=='M'){
    dash();
    dash();}
    else if(text[i]=='N'){
    dash();
    dot();}
    else if(text[i]=='O'){
    dash();
    dash();
    dash();}
    else if(text[i]=='P'){
    dot();
    dash();
    dash();
    dot();}
    else if(text[i]=='Q'){
    dash();
    dash();
    dot();
    dash();}
    else if(text[i]=='R'){
    dot();
    dash();
    dot();}
    else if(text[i]=='S'){
    dot();
    dot();
    dot();}
    else if(text[i]=='T'){
    dash();}
    else if(text[i]=='U'){
    dot();
    dot();
    dash();}
    else if(text[i]=='V'){
    dot();
    dot();
    dot();
    dash();}
    else if(text[i]=='W'){
    dot();
    dash();
    dash();}
    else if(text[i]=='X'){
    dash();
    dot();
    dot();
    dash();}
    else if(text[i]=='Y'){
    dash();
    dot();
    dash();
    dash();}
    else if(text[i]=='Z'){
    dash();
    dash();
    dot();
    dot();}
  }  
}
```
