### 1. **int** (Heltal)

- **Beskrivning**: Används för att lagra hela tal (heltal) som inte har några decimaler.
- **Exempel**: `int a = 5;`
- **Minne**: Vanligtvis 4 byte (kan variera beroende på systemet).
- **Värdeområde**: Vanligtvis från -2,147,483,648 till 2,147,483,647 (på de flesta system).

### 2. **float** (Flyttal)

- **Beskrivning**: Används för att lagra flyttal (tal med decimaler), men med enkel precision.
- **Exempel**: `float b = 5.5;`
- **Minne**: Vanligtvis 4 byte.
- **Värdeområde**: Cirka 1.2E-38 till 3.4E+38 med upp till 6-7 decimalers precision.

### 3. **double** (Dubbel precision flyttal)

- **Beskrivning**: Används för att lagra flyttal med dubbel precision, vilket innebär högre noggrannhet än `float`.
- **Exempel**: `double c = 5.123456789;`
- **Minne**: Vanligtvis 8 byte.
- **Värdeområde**: Cirka 2.3E-308 till 1.7E+308 med upp till 15-16 decimalers precision.

### 4. **char** (Tecken)

- **Beskrivning**: Används för att lagra ett enda tecken (t.ex. bokstäver, siffror, symboler).
- **Exempel**: `char d = 'A';`
- **Minne**: 1 byte.
- **Värdeområde**: Från -128 till 127 (eller 0 till 255 om den är osignerad).

### 5. **unsigned int** (Osignerat heltal)

- **Beskrivning**: Lagrar endast positiva heltal eller noll.
- **Exempel**: `unsigned int e = 10;`
- **Minne**: Vanligtvis 4 byte.
- **Värdeområde**: Från 0 till 4,294,967,295.

### 6. **short** (Kort heltal)

- **Beskrivning**: Används för att lagra mindre heltal.
- **Exempel**: `short f = 32000;`
- **Minne**: Vanligtvis 2 byte.
- **Värdeområde**: Från -32,768 till 32,767.

### 7. **long** (Långt heltal)

- **Beskrivning**: Används för att lagra större heltal än vad `int` klarar av.
- **Exempel**: `long g = 1000000;`
- **Minne**: Vanligtvis 4 eller 8 byte, beroende på system.
- **Värdeområde**: Kan variera, men vanligtvis större än `int`.

### 8. **bool** (Boolean, C99-standard och framåt)

- **Beskrivning**: Används för att lagra sant eller falskt värde.
- **Exempel**: `bool j = true;`
- **Minne**: 1 byte (C använder `stdbool.h` för att definiera `bool`).
- **Värdeområde**: `true` eller `false`.

## Exempel

```C
#include <stdio.h>
#include <stdbool.h> // Behövs för bool

int main() {
    int a = 5;                 // Heltal
    float b = 5.5;             // Flyttal
    double c = 5.123456789;    // Dubbel precision flyttal
    char d = 'A';              // Tecken
    unsigned int e = 10;       // Osignerat heltal
    short f = 32000;           // Kort heltal
    long g = 1000000;          // Långt heltal
    unsigned char h = 200;     // Osignerat tecken
    long long i = 1000000000000; // Mycket långt heltal
    bool j = true;             // Boolean

    printf("int: %d\n", a);
    printf("float: %.1f\n", b);
    printf("double: %.9f\n", c);
    printf("char: %c\n", d);
    printf("unsigned int: %u\n", e);
    printf("short: %d\n", f);
    printf("long: %ld\n", g);
    printf("unsigned char: %u\n", h);
    printf("long long: %lld\n", i);
    printf("bool: %d\n", j);

    return 0;
}
```

## Sammanfattning

Varje variabeltyp har sitt eget användningsområde baserat på hur mycket minne de använder och vilka värdeintervall de stöder. När du skriver ett C-program är det viktigt att välja rätt typ av variabel för att optimera minnesanvändning och prestanda.