### Vanlig program

o main()
|
v
o
|
v
x

### Event-driven program

o main
|
v
Enkel loop [Väntar på input (Enter)] (event-driven architecture) (exempel Microsoft Word, Excel, Photoshop, typ Browser)
|
v
quit

### Spel program

main()
|
v
[Game Loop] <- input
|
v
quit

Vanligtvis vill man köra game loopen så snabbt vi kan.
Logik vill man ha snabbt
Grafik kan behöva vänta på grund av refresh rate (60hz t.ex)

#### Vad händer i Game Loopen?

det är ofta en while loop

Den körs tills användaren vill lämna

I Raylib kan man skriva ``while(!WindowShouldQuit())``

Generellt ser det ut så här
Input funktion som tar in input logik (pad, mus, keyboard etc.)
Update funktion som uppdaterar logiken, typ allt.
	I Update kan man ha fysik logik, collision detection, ai (inte som ChatGPT AI), musik/ljud
Render funktion som ritar upp allting

Allt det här händer varje frame

[[Raylib]] 