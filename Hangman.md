Here is the code

```
1. # simple hangman game using turtle graphics
2. 
3. import turtle
4. import random
5. 
6. def drawMan(x):
7.     guess = x
8.     if guess == 1: 
9.         # draw head
10.         turtle.goto(-74, 140)
11.         turtle.pendown()
12.         turtle.right(90)
13.         turtle.circle(15,None,100)
14.         turtle.penup()
15.     elif guess == 2:
16.         # draw torso
17.         turtle.goto(-74, 140)
18.         turtle.pendown()
19.         turtle.left(90)
20.         turtle.penup()
21.         turtle.forward(30)
22.         turtle.pendown()
23.         turtle.forward(40)
24.         turtle.right(180)
25.         turtle.forward(30)
26.         turtle.penup()
27.     elif guess == 3:
28.         # draw first arm
29.         turtle.goto(-74, 100)
30.         turtle.pendown()
31.         turtle.left(55)
32.         turtle.forward(45)
33.         turtle.right(180)
34.         turtle.forward(45)
35.         turtle.penup()
36.     elif guess == 4:
37.         # draw second arm
38.         turtle.goto(-74, 100)
39.         turtle.pendown()
40.         turtle.left(70)
41.         turtle.forward(45)
42.         turtle.right(180)
43.         turtle.forward(45)
44.         turtle.penup()
45.     elif guess == 5:
46.         # draw first leg
47.         turtle.goto(-74, 100)
48.         turtle.pendown()
49.         turtle.left(55)
50.         turtle.forward(30)
51.         turtle.right(30)
52.         turtle.forward(60)
53.         turtle.right(180)
54.         turtle.forward(60)
55.         turtle.penup()
56.     elif guess == 6:
57.         # draw second leg
58.         turtle.goto(-74, 70)
59.         turtle.pendown()
60.         turtle.right(120)
61.         turtle.forward(60)
62.         turtle.penup()
63. 
64. # initialize turtle
65. turtle.hideturtle()
66. turtle.speed(0)
67. turtle.pensize(2)
68. 
69. wordbank = ['affix','bagpipes','bandwagon','banjo','buffalo',
70.             'cobweb','croquet','daiquiri','duplex','dwarves',
71.             'equip','exodus','fishhook','fixable','galaxy',
72.             'galvanize','ivy','juicy','kilobyte','megahertz',
73.             'oxygen','polka','quiz','rhubarb','schizophrenia',
74.             'unzip','uptown','vodka','whiskey','zombie']
75. 
76. bored = False
77. while not bored:
78. 
79.     # draw gallows
80.     turtle.home()
81.     turtle.pendown()
82.     turtle.left(90)
83.     turtle.forward(175)
84.     turtle.left(90)
85.     turtle.forward(74)
86.     turtle.left(90)
87.     turtle.forward(35)
88.     turtle.penup()
89.     turtle.goto(-135,-35)
90. 
91.     word = random.choice(wordbank)
92. 
93.     for i in word:
94.         turtle.write('_ ', True, font=("Courier", 14, "normal"))
95. 
96.     correct = []
97.     wrong = 0
98.     terminate = False
99.     while wrong < 6 and not terminate:
100.         letter = input('Guess a letter:')
101.         turtle.goto(-135,-35)
102.         if letter not in correct:
103.             for i in word:
104.                 if i == letter:
105.                     turtle.write(letter.upper() + ' ', True, font=("Courier", 14, "normal"))
106.                     correct += letter
107.                 else:
108.                     turtle.write('_ ', True, font=("Courier", 14, "normal"))  
109.         if letter not in word:
110.             wrong += 1
111.             drawMan(wrong)
112.         if wrong == 6:
113.             turtle.goto(-135,-35)
114.             for i in word:
115.                 if i in correct:
116.                     turtle.write('_ ', True, font=("Courier", 14, "normal"))
117.                 else:
118.                     turtle.write(i.upper() + ' ', True, font=("Courier", 14, "normal"))
119.             turtle.goto(-74, -60)
120.             turtle.write('Sorry, you lose!', False, align='center', font=("Courier", 14, "normal"))
121.         if len(correct) == len(word):
122.             turtle.goto(-74, -60)
123.             turtle.write('Congratulations!', False, align='center', font=("Courier", 14, "normal"))
124.             terminate = True
125. 
126.     # play again?
127.     response = input('Would you like to play again? (y or n): ')
128.     while response != 'y' and response != 'n':
129.         response = turtle.textinput('Hangman','Please enter "y" or "n": ')
130.     if response == 'y':
131.         turtle.clear()
132.     elif response == 'n':
133.         turtle.clear()
134.         turtle.home()
135.         turtle.write('Thanks for playing!', False, align='center', font=("Courier", 25, "normal")) 
136.         bored = True

```

![image](https://github.com/lookdeepu/Games/assets/24821571/3da7d3b4-2313-45c9-8d80-006022782cee)
