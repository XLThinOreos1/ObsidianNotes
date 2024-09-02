https://www.tutorialspoint.com/c_standard_library/stdio_h.htm

```c
FILE =  fopen(const char *filename, const char *mode)
fprintf(FILE *stream, const char *format, ...) // Skriva
fscanf(FILE *stream, const char *format, ...); // Läsa
```

``"r"``: Open for reading. The file must exist
``"w"``: Open for writing. Creates an empty file or truncates an existing file.
``"a"``: Open for appending. Writes data at the end of the file. Create the file if it does not exist.
``"r+"``: Open for reading and writing. The file must exist.
``"w+"``: Open for reading and writing. Creates an empty file or truncates an existing file.
``"a+"``: Open for reading and appending. The file is created if it does not exist.

``"rb"``: Läsa från en *binär* fil


```c
#include <stdio.h>

int main() {
	char *name = "Sebastian";
	int age = 38;

	FILE* my_file = fopen("myfile.txt", "w");
	if (NULL == my_file) {
		printf("ERROR! Could not open file!\n");
		return 1;
	}

	fprintf(my_file, "Name: %s Age: %d", name, age); // Skriver ut till en fil
	fclose(my_file);

	// Viktig att stänga första filen innan man öppnar samma för att göra en annan ändring för den kommer inte låta dig
	my_file = fopen("myfile.txt", "r");
	char mychar[65];
	fscanf(my_file, "Name: %64s Age: %d\n", mychar, &age);
	fclose(my_file);

	printf("%s\n", mychar);
	return 0;
}
```