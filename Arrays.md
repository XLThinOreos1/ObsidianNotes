I C-programmering används arrays (fält) för att lagra flera värden av samma datatyp i en enda variabel. En array är en samling av element som ligger i följd i minnet, och varje element kan nås med hjälp av ett index.

### Vad är en array?

En **array** är en datastruktur som kan lagra en fast storlek på sekventiella element av samma typ. Tänk på en array som en lista eller en rad med fack där varje fack innehåller ett värde.

### Hur definierar man en array i C?

För att definiera en array i C anger du typen av elementen, följt av namnet på arrayen och storleken inom hakparenteser. Storleken måste vara ett positivt heltal som bestämmer hur många element arrayen kan lagra.

#### Exempel på array-deklaration:

```c
int numbers[5];  // En array av 5 heltal
```

I det här exemplet har vi deklarerat en array med namnet `numbers` som kan lagra 5 heltal (int).

### Initiera en array

När du deklarerar en array kan du också initiera den (ge den värden) direkt:

```c
int numbers[5] = {10, 20, 30, 40, 50};
```

Här skapas en array av 5 heltal och initialiseras med värdena 10, 20, 30, 40 och 50. 

Du kan också lämna storleken tom och låta kompilatorn räkna ut storleken baserat på antalet initialvärden:

```c
int numbers[] = {10, 20, 30, 40, 50}; // Kompilatorn förstår att storleken är 5
```

### Åtkomst till array-element

Elementen i en array kan nås med hjälp av deras index. Observera att index i C är nollbaserat, vilket innebär att det första elementet har index 0, det andra har index 1, och så vidare.

#### Exempel:

```c
#include <stdio.h>

int main() {
    int numbers[5] = {10, 20, 30, 40, 50};

    // Skriva ut alla element i arrayen
    for (int i = 0; i < 5; i++) {
        printf("Element at index %d: %d\n", i, numbers[i]);
    }

    return 0;
}
```

**Utdata:**

```c
Element at index 0: 10
Element at index 1: 20
Element at index 2: 30
Element at index 3: 40
Element at index 4: 50
```

I koden ovan använder vi en `for`-loop för att iterera genom arrayen och skriva ut varje element. Variabeln `i` används som index för att komma åt respektive element i arrayen.

### Ändra värden i en array

Du kan enkelt ändra värdet på ett specifikt element i en array genom att tilldela ett nytt värde till ett specifikt index.

```c
numbers[2] = 100;  // Ändrar det tredje elementet (index 2) till 100
```

Efter denna operation kommer `numbers[2]` att vara `100` istället för `30`.

### Viktiga punkter att komma ihåg om arrays:

1. **Fast storlek**: Storleken på en array i C är fast när den deklareras och kan inte ändras under programmets gång.
2. **Nollbaserat index**: Det första elementet i en array har index `0`, det andra har index `1`, etc.
3. **Samma datatyp**: Alla element i en array måste vara av samma datatyp.
4. **Minnesåtkomst**: Eftersom elementen i en array ligger i följd i minnet, kan man snabbt få tillgång till ett element genom att beräkna dess minnesadress.

### Sammanfattning

Arrays är en grundläggande datastruktur i C som gör det möjligt att lagra flera värden av samma datatyp i en sekventiell struktur. De är användbara när du behöver arbeta med en stor mängd data av samma typ och vill ha snabb åtkomst till varje element via ett index.




# Dynamisk array

