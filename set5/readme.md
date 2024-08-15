TODO: Reflect on what you learned this week and what is still unclear.

no indentation loops & indentation loops differents
python3 ../course/set5/tests.py
This week I followed the teacher's online class and consolidated the loops, but it would be nice if the teacher could give me the code template for the course, as I didn't look up the information on these Korean boy band artists online to the form.

I learnt to count the length of names, the number of letters. 
“lengths = []
for name in names:
    lengths.append(len(name))
print(lengths)”
This code calculates the length of each name by looping through it and storing the result in the lengths list. len(name) function returns the number of characters in the string name, and the append() method adds it to the lengths list. Finally, the lengths list is printed.

Consolidates the use of while

Learned the use of random, 

import random 

guard = 0
coin = "tails"
while coin == "tails" and guard < 10:
    coin = random.sample(["heads", "tails"], 1)[0]
    print(coin, guard)
    guard += 1
this code segment simulates a coin flip process, the initial coin state is "tails", each loop randomly generates "heads" or "tails", until the coin state becomes "heads" or the number of loops reaches 10. random.sample () function from the list of randomly selected an element, the guard variable is used to control the number of loops.

I also learnt that you need to use import to add functionality to your code, such as import random.

