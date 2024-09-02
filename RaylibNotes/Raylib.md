### Render
```c
SetTargetFPS(60); // Bestämmer hur länge EndDrawing() ska vänta innan den går över till nästa frame.

while (!WindowShouldClose()) {
	BeginDrawing(); // Allokerar dynamisk minne

	allt

	EndDrawing(); // Ta allokerat minne och kopiera till skärmen så den faktsikt ritar upp till skärmen. Sen nollställer den minnet så vi kan gå tillbaka till BeginDrawing();.
}
```


### Vector

[[Vector]]
