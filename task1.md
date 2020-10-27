### Situation: In a game of guessing a number between 1-100 for two players, player A and player B. The player A knows the number. The player B is trying to guess with the least number of attempts. Player A can only reply to a guess from the other player B with “low”, “high”, or “That is the number”. Your task is to create a computer program for Player B. Good luck and let the best strategy for player B win!
```.py
#This program is a game for Player B
import random
num_A=int(random.randint(1,101))
num_attempts=int(0)
num_B=int(0)
while num_B!=num_A:
    num_B=int(input("Player B, enter a number --> "))
    num_attempts+=1
    if num_B<num_A:
        print("Player A: higher!") 
    if num_B>num_A:
        print("Player A: lower!")
    if num_B==num_A:
        print("Player A: That is the number!")
        print("Number of attempts={}".format(num_attempts))
```
