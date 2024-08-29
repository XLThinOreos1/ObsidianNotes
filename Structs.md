I C-programmering kan strukturer (structs) användas för att skapa komplexa datatyper som kan innehålla olika typer av data.


### Vad är en struct?

En `struct` är en användardefinierad datatyp i C som gör det möjligt att gruppera olika datatyper under ett enda namn. Den är användbar när man vill representera en komplex datamodell som består av flera olika typer av data.

### Hur skriver man en struct?

Struct skriver man oftast genom att börja det med ``typedef struct`` med sen curly brackets för att mata in datan.

#### Exempel:
```c
#include <stdio.h>

typedef struct {
	char name[50];
	int age;
	float height;
} Person;

int main() {
	// Deklarera en variabel av typen Person utan att skriva struct
	Person person1;

	// Tilldela värden till strukturfälten
	snprintf(person1.name, sizeof(person1.name), "Pontus");
	person1.age = 30;
	person1.height = 5.7;

	// Skriva ut värdena
	printf("Name: %s\n", person1.name);
	printf("Age: %d\n", person1.name);
	printf("Height: %.1f\n", person1.name);

	return 0;
}
```
