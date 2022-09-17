# Our Spy In New Terrain (OSINT) 
## Category
Forensics
## Problem Description
It is up to you to determine who The Enemy is going to attack next and when they plan to strike! Their newest recruit is on twitter as DarkRoom8109. Good luck. nc misc.chal.csaw.io 5005
## Approach
I checked out DarkRoom8109's twitter profile and found he joined twitter on **08/2022** and I also found his github username **spyduhman**.<br>
Checking out spyduhman's github profile I found that **log.txt** contains all the conversations between the enemy and the evil spy.<br>
Checking out his commits I found that he deleted log.txt and it contained the link [bit.ly/evilevilinfo](bit.ly/evilevilinfo).<br>
The website had an audio file **Assignment.wav** which was in morse. Converting it from morse I found the following:<br>

```


HELIHELLO EVIL AGENT YOUR NEXT TARGET IS A BANK THE BANK'S BIN NUMBER IS 452234 THE TARGETS SWIFT CODE IS YOUR PASSWORD FOR MORE INSTRUCTIONS VISIT BIT.LY SLASH OSINTSEC GOOD LUCK

```

Checking out the bank's bin number I found that the next target's bank is **TORONTO-DOMINION BANK**. Toronto-Dominion Bank's International Swift Code is **TDOMCATTTOR**.<br>
Visiting [bit.ly/osintsec](bit.ly/osintsec) I put TDOMCATTTOR as password the reveal an image which when I took the screenshot of found the crime to be **Copyright Infringement** and voila!

```
siddharth@siddharth-pc:~$ nc misc.chal.csaw.io 5005
Welcome agent! We have reason to believe a user with the twitter handle Darkroom8109 is working with The Enemy! Can you help us determine what The Enemy is planning?
1. When did the enemy agent join twitter? Please use the format MM/YYYY
Please enter your answer:
08/2022
That's right!
2. What is the spy's github username?
Please enter your answer:
spyduhman
That's right!
3. What is the full name of the file that contains communications between The Enemy and the Evil Spy?
Please enter your answer:
log.txt
That's right!
4. Which country is the target based in?
Please enter your answer:
canada
That's right!
5. What is the target's international Swift code?
Please enter your answer:
TDOMCATTTOR
That's right!
6. What is a crime?
What is the answer? Hint: it is two words
Copyright Infringement
That's right!
Congrats! Thanks to you, we now have more information about The Enemy's upcoming attack!
Here's a little reward for your trouble: flag{C0N6r475463N7600DW0rKN3X771M3N0PU811C53rV3r}
```

## Flag
flag{C0N6r475463N7600DW0rKN3X771M3N0PU811C53rV3r}
