### Task 1

```
#include <stdio.h>
#include <string.h>

int main() {

    char message[100];

    printf("Enter a message: ");
    fgets(message, 100, stdin);
    message[strcspn(message, "\n")] = 0;   // remove newline

    strcat(message, "shadow");             // add shadow

    int total = strlen(message);
    int countExceptShadow = total - 6;     // shadow = 6 letters

    printf("\nThe code word '%s' has length %d characters.",
           message, countExceptShadow);

    return 0;
}
```

### Task 2:

```
#include <stdio.h>
#include <string.h>

int main() {

    char word[15];
    char search;

    printf("Enter a word without spaces: ");
    scanf("%s", word);

    printf("Enter character to search: ");
    scanf(" %c", &search);   // space before %c to skip newline

    char *p = strchr(word, search);

    if (p != NULL) {
        int pos = p - word;  // index of found character
        printf("Found at position %d\n", pos);
    } else {
        printf("Not found\n");
    }

    return 0;
}
```

### Task 3:

```
#include <stdio.h>
#include <string.h>

int main() {

    char code1[50], code2[50];
    int n;

    printf("Enter first product code: ");
    scanf("%s", code1);

    printf("Enter second product code: ");
    scanf("%s", code2);

    printf("Enter number of characters to compare: ");
    scanf("%d", &n);

    int len1 = strlen(code1);
    int len2 = strlen(code2);

    // If n is bigger than any string, limit n to the shortest length
    if (n > len1 || n > len2) {
        printf("\nWARNING: n is larger than one or both strings.\n");
        n = (len1 < len2) ? len1 : len2;
        printf("Comparing only first %d characters.\n", n);
    }

    if (strncmp(code1, code2, n) == 0) {
        printf("\nResult: SAME PREFIX (first %d characters match)\n", n);
    } else {
        printf("\nResult: DIFFERENT PREFIX (first %d characters do not match)\n", n);
    }

    return 0;
}
```

### Task 4:

```
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>

int main() {
	FILE* fptr;
	fptr = fopen("library.txt", "w");

	if (fptr == NULL) {
		printf("Error opening file\n");
		exit(1);
	}
	char line[15];

	for (int i = 0; i < 3; i++) {
		printf("\nEnter book ID number %d", i + 1);
		scanf("%s", line);
		fprintf(fptr, "%s\n", line);
	}

	fclose(fptr);

	fptr = fopen("library.txt", "r");
	for (int i = 0; i < 3; i++) {
		fgets(line, 16, fptr);
		printf("%s", line);

	}
	return 0;
}
```

### Task 5:

```
#include <stdio.h>
#include <string.h>

int main() {
		
	char original[10], backup[10];

	printf("Type a word: ");
	scanf("%s", original);

	strcpy(backup, original);

	printf("\nOriginal message: %s", original);
	printf("\nBackup message: %s", backup);

	return 0;
}
```

Task 6:

```
#include <stdio.h>
#include <string.h>

int main() {
		
	char name1[30], name2[15];

	printf("Type first name: ");
	scanf("%s", name1);
	printf("Type second name: ");
	scanf("%s", name2);

	strcat(name1, name2);

	printf("\nFinal name is: %s", name1);
	

	return 0;
}
```

### Task 7:

```
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>

int main() {
		
	char password[20], passcheck[20];

	printf("Type password to create: ");
	fgets(password, sizeof(password), stdin);
	password[strcspn(password, "\n")] = 0;
	printf("Type password again to confirm: ");
	fgets(passcheck, sizeof(passcheck), stdin);
	passcheck[strcspn(passcheck, "\n")] = 0;

	int len = strlen(password);
	while (len > 0 && password[len - 1] == ' ') {
		password[len - 1] = '\0'; // remove the last character
		len--;                    // move “len” backward
	}

	len = strlen(password);
	while (len > 0 && passcheck[len - 1] == ' ') {
		passcheck[len - 1] = '\0'; // remove the last character
		len--;                    // move “len” backward
	}

	(strcmp(password, passcheck) == 0) ? printf("Password Matched") : printf("Passwords do not match");

	
	

	return 0;
}
```

### Task 8:

```
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>

int main() {
		
	char Names[3][20], passcheck[20];

	for (int i = 0; i < 3; i++) {
		printf("\nEnter name of student %d: ", i + 1);
		fgets(Names[i], sizeof(Names[i]), stdin);
	}

	for (int i = 0; i < 3; i++) {
		printf("\nStudent %d: %s", i + 1, Names[i]);
	}


	return 0;
}
```


### Task 9:

```
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>
int main() {
	
	char names[3][15];

	char line[15];

	for (int i = 0; i < 3; i++) {
		printf("\nEnter name %d: ", i + 1);
		scanf("%s", names[i]);
	}

	
	for (int i = 0; i < 3; i++) {
		for (int j = 0; j < strlen(names[i]); j++) {
			printf("%c ", names[i][j]);
		}
		printf("\n");
		

	}
	return 0;
}
```


### Task 10:

```
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>
int main() {
	
	char names[5][20];

	char line[20];

	for (int i = 0; i < 5; i++) {
		printf("\nEnter name %d: ", i + 1);
		scanf("%s", names[i]);
	}

	FILE* fptr;
	fptr = fopen("names.txt", "w");
	
	if (fptr == NULL) {
		printf("\nError opening file");
		exit(1);
	}

	for (int i = 0; i < 5; i++) {
		fprintf(fptr, "%s\n", names[i]);
	}

	fclose(fptr);
	int found = 0;
	char name[20];
	printf("\nEnter name to search: ");
	scanf("%s", name);
	fptr = fopen("names.txt", "r");
	for (int i = 0; i < 5; i++) {
		fgets(line, sizeof(line), fptr);
		line[strcspn(line, "\n")] = 0;
		if (strcmp(line, name)) {
			printf("\n Name found");
			found = 1;
			break;
		}
	}
	if (found == 0) {
		printf("\nName not found");
	}

	return 0;
}
```

