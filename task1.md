### Situation: In a game of guessing a number between 1-100 for two players, player A and player B. The player A knows the number. The player B is trying to guess with the least number of attempts. Player A can only reply to a guess from the other player B with “low”, “high”, or “That is the number”. Your task is to create a computer program for Player B. Good luck and let the best strategy for player B win!
```.py
#This program is a game for Player B

import random
num_A=int(random.randint(1,101))
num_B=50
num_attempts=1

if num_B<num_A:
    print("higher!")
    num_B=75
    print(75)
if num_B>num_A:
    print("lower!")
    num_B=25
    print(25)
if num_B==num_A:
    print("Player A: That is the number! {}".format(num_A))
    print("Number of attempts={}".format(num_attempts))

while num_B!=num_A:
    if num_B<num_A:
        print("higher!")
        num_B/=2
        print(num_B)
    if num_B>num_A:
        print("lower!")
        num_B/=2
        print(num_B)
    if num_B==num_A:
        print("Player A: That is the number! {}".format(num_A))
        print("Number of attempts={}".format(num_attempts))

```
