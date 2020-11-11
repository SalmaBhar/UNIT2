# UNIT 2 - Salma Bhar
# Braille Counting Project
## Criteria A: Planning
### Context of the problem
This project is a program to count from 0 to 9. The preceding has been done last year with the current G12s who used the standard 7 figures to count. Therefore, this year's G11s will have to think outside the box and come up with more creative ways to create a program with the purpose of counting while using the same criteria and resources. We will dispose of: <br>
- 7 LEDs <br>
- 4 Buttons <br>
- Arduino <br>
- Circuits components <br>

### Justification of the solution
I will create a program dsiplayed on LEDs which counts from 0 to 9 in braille language when we press different combinations of buttons. As for hardware, I am using 4 LEDs, 4 buttons and an Arduino. It is worth noting that only 4 LEDs will be used out of the 7 provided which optimizes this solution even further. Moreover, I will be using C++ as a software language since it is the primary coding language for the Arduino and we have had practise sessions during class in that language. In fact in 2017, C++ ranked 4th among 24 other programming languages in September [1] due to its fast processing and several built-in functions. The program will be first run on the simulator Tinkercad to avoid damaging the physical components when testing the solution. <br>

[1] Ramasubramanian, Sowmya. “C++ Is Now the Fastest-Growing Programming Language, Report Says.” The Hindu, The Hindu, 11 Sept. 2020, www.thehindu.com/sci-tech/technology/c-is-now-the-fastest-growing-programming-language/article32580426.ece. 

T.E.L.O.S. Study: <br>
T-Technical-Is the project technically possible? We dispose of a computer, Arduino
E-Economic-
L-Legal-
O-Operational-
S-Scheduling-
### Criteria for success
1. There are no bugs in the program <br>
2. Provides clear signage of the counting <br>
3. Full Documentation on GitHub <br>

## Criteria B: Design
### System Diagram
We drew the following system diagram in class: <br>
![alt text](systemdiagram.jpg) <br>
### Initial Sketches
These are braille numbers: <br>
![alt text](braillenumbers.png) <br>
I drew the initial idea of the system in a sketch:
![alt text](Braillesketch.jpg) <br>
## Criteria C: Devolepment
I started with a truth table of the 4 LEDs: a, b, c, d. <br>
![alt text](truthtable.png) <br>
Then I traced the K-maps of each of the 4 LEDs. <br>
![alt text](kmaps.jpg) <br>
These are the logic gates circuits for each of the 4 LEDs. <br>
![alt text](logicgatesa.jpg) <br>
This is the C++ code for the Arduino:
```cpp
// Definitions
int led_a=11;
int led_b=8;
int led_c=7;
int led_d=10;
int btn_x=6;
int btn_y=12;
int btn_z=13;
int btn_w=5;
int val_x=0;
int val_y=0;
int val_z=0; 
int val_w=0;  

// Setup of the inputs/outputs
void setup(){
  pinMode(led_a, OUTPUT);
  pinMode(led_b, OUTPUT);
  pinMode(led_c, OUTPUT);
  pinMode(led_d, OUTPUT);
}

// Equations
void loop(){
  val_x=digitalRead(btn_x);
  val_y=digitalRead(btn_y);
  val_z=digitalRead(btn_z);
  val_w=digitalRead(btn_w);
  int a=(!val_z)&&(val_w)&&(!val_x)||(val_z)&&(val_w)&&(!val_x)||(val_z)&&(!val_w)&&(!val_x)||(!val_z)&&(!val_w)&&(!val_x)&&(val_y)||(!val_z)&&(!val_w)&&(val_x)&&(!val_y);
  digitalWrite(led_a, a);
  int b=(!val_z)&&(!val_w)&&(!val_x)||(val_z)&&(val_w)&&(!val_x)||(val_z)&&(!val_w)&&(!val_x)&&(val_y)||(!val_z)&&(val_w)&&(val_x)&&(!val_y);
  digitalWrite(led_b, b);
  int c=(val_x)&&(!val_y)&&(!val_z)||(val_x)&&(!val_y)&&(!val_z)||(!val_x)&&(!val_y)&&(!val_w);
  digitalWrite(led_c, c);
  int d=(!val_z)&&(!val_w)&&(!val_x)||(!val_x)&&(val_y)&&(val_w)||(val_x)&&(!val_y)&&(!val_w)&&(!val_z);
  digitalWrite(led_d, d);
}

```
## Criteria D: Functionality
VIDEO !!!
## Criteria E: Evaluation
???
