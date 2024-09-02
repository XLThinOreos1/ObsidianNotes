#include <stdio.h>

// 1. Deklarera en pointer ('*')
// "int *ptr;" deklarerar en pointer som heter "ptr" som kan lagra adressen av en int typ.

// 2. Address-of Operator ('&')
// & operator används för att ge addressen av en variabel.

int num = 10;
// &num ger minnesaddressen av variabeln "num", som är senare sparat i "ptr" pointern.
int *ptr = &num;

// 3. Dereference Operator ('*')
// '*' operator används också för att dereferencea en pointer. Dereferenca en pointer innebär att accessa
// värdet som är lagrat i minnesadressen som pointern lagrar.
// T.ex

int num = 10;
int *ptr = &num;
printf("%d\n", *ptr); // Outputtar 10
// Här *ptr ger värdet som är lagrat i addressen som ptr lagrar som är 10.

// 4. Pointer initialization
// Pointer borde bli initialiserad till antingen "NULL" eller en valid adress annars riskerar man att det orsakar konstig beteende eller crashar.
int *ptr = NULL;

// 5. Modifiera värden genom pointers
// Du kan använda en pointer för att modifiera värdet av en variabel
int num = 10;
int *ptr = &num;
*ptr = 20; // Ändrar värdet av num till 20
printf("%d\n", num); // Outputtar 20

// 6. Pointer Arithmetic
// You can perform arithmetic operations on pointers to navigate through memory. When you add or subtract an integer to/from a pointer, 
// it moves by that number of elements, not bytes.
// For example, if ptr is an int* and you do ptr + 1, the pointer will move to the next int position,
// which is typically 4 bytes away (assuming an int is 4 bytes on your system).

int arr[3] = {1, 2, 3};
int *ptr = arr; // Pekar mot första elementet
printf("%d\n", *ptr); // Outputtar: 1
printf("%d\n", *(ptr + 1)); // Outputtar: 2
printf("%d\n", *(ptr + 2)); // Outputtar: 3

// Varför använda pointers?
// 
// Pointers är användbara för de tillåter en att göra:
// * Dynamisk minneshantering: Du kan allokera och deallokera minne under runtime med pointers (med "malloc", "calloc", "realloc" och "free")
// * Efficient array hantering: Pointers låter dig att navigera och manipulera arrays efficiently, speciellt för stora datasets.
// * Funktion argument: Pointers tillåter funktioner att modifera värdet av variabler som passerar de (pass-by-reference) istället för bara kopior av värdet (pass-by-value).
// * Datastrukturer: Pointers är viktiga för att implementera datastrukturer som länkade listor, trees och grafer, där nodes är dynamisk skapad och länkade.

// Exempel program:

#include <stdio.h>

int main() {
    int num = 42;      // Declare an integer variable
    int *ptr = &num;   // Declare a pointer and initialize it with the address of num

    printf("Value of num: %d\n", num);       // Outputs: 42
    printf("Address of num: %p\n", &num);    // Outputs: memory address of num
    printf("Value of ptr: %p\n", ptr);       // Outputs: memory address stored in ptr (same as &num)
    printf("Value pointed to by ptr: %d\n", *ptr);  // Outputs: 42

    // Modifying num using the pointer
    *ptr = 99;
    printf("Value of num after modification: %d\n", num);  // Outputs: 99

    return 0;
}


// Viktiga saker att komma ihåg:
// * Använd & för att få adressen av en variabel och * för att få tillgång till värdet på adressen.
// Va försiktig när man jobbar med pointer arithmetic och minneshantering för att undvika fel som segmentation fault och minnesluckor.
