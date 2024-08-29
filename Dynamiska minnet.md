

| Stacken  |
| -------- |
| "heapen" |
| data     |
| code     |

Heapen kan man göra dynamisk minne

Dynamisk minne kan man frigöra

``fopen -> malloc()``
``fclose -> free()``



Allokera -> malloc() 
	Låser en vis byte
	Söker genom heapen efter 16 bytes (malloc(16)) fria bredvid varandra och sen allokerar de. Säger till nästa gång jag söker efter 16 bytes så får jag inte använda de.
	Malloc returnar en pekare som pekar till första biten som den nyss allokerade till heapen.
	Fragmenterar när man friar upp med tiden.


Deallokera -> free()
	Låser upp låst bytes orsakad av malloc()

Reallokerar -> realloc()
	Först hittar ett nytt sätt att placera det du vill på
	Kopierar första delen av det
	Friar gamla pekaren


Man vill försöka undvika malloc() och användning av dynamisk minne


När arrayen får slut på plats så vill man kalla realloc och dubbla storleken

```c
typedef struct {
	int* data;
	int capacity;
	int occupied;
} darray-ints;

push(int)
pop()

remove-at(int id);
```
