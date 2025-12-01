### Task 1

```
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>

int main() {
	int* arr = (int*)malloc(5 * sizeof(int));
	if (arr == NULL) printf("\nAllocation failed");

	for (int i = 0; i < 5; i++) {
		arr[i] = i + 1;
	}

	printf("%d", arr[5]);

	return 0;
}
```

### Task 2

```
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>

int main() {
	int* arr = (int*)malloc(5 * sizeof(int));

	if (arr == NULL) printf("\nAllocation failed");

	free(arr);
	free(arr);
	
	//Code doesn't execute. For me, cmd is blank
	//It works if I have only one free(arr)

	return 0;
}
```

### Task 3

```
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>

int main() {
	int* arr = (int*)malloc(5 * sizeof(int));

	if (arr == NULL) printf("\nAllocation failed");

	for (int i = 0; i < 5; i++) {
		*(arr + i) = i + 1;
	}
	for (int i = 0; i < 5; i++) {
		printf("\n%d", *(arr + i));
	}

	return 0;
}
```

### Task 4

```
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>

int main() {
	int* arr = (int*)malloc(5 * sizeof(int));
	
	if (arr == NULL) printf("\nAllocation failed");

	int i = 0, userChoice;

	do {
		if (i > 4) {
			printf("\nArray length exceeded");
			break;
		}
		printf("\nEnter value for index %d: ", i + 1);
		scanf("%d", &arr[i]);
		i++;
		printf("\nDo you want to enter more values?(1 = yes, 0 = no): ");
		scanf("%d", &userChoice);
	} while (userChoice == 1);
	
	arr = (int*)realloc(arr, 10 * sizeof(int));

	for (int i = 0; i < 10; i++) {
		printf("\n%d", arr[i]);
	}

	return 0;
}
```

### Task 5

```
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>

int main() {
	int** arr = (int**)calloc(5, sizeof(int));
	
	

	for (int i = 0; i < 5; i++) {
		arr[i] = (int*)calloc(5, sizeof(int));
	}

	for (int i = 0; i < 5; i++) {
		for (int j = 0; j < 5; j++) {
			arr[i][j] = 0;
		}
	}
	int val;

	for (int i = 0; i < 5; i++) {
		for (int j = 0; j < 5; j++) {
			printf("\nEnter value of row %d column %d: ", i, j);
			scanf("%d", &arr[i][j]);
		}
	}

	for (int i = 0; i < 5; i++) {
		for (int j = 0; j < 5; j++) {
			printf("%d ", arr[i][j]);
			
		}
		printf("\n");
	}

	return 0;
}
```

### Task 6

```
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <stdlib.h>



int main() {

    int* ptr;   // pointer has no memory, it points to random garbage
    *ptr = 6;   // writing to random address may cause crash or unexpected behaviour
	printf("%d", *ptr);
    return 0;
}
```

### Task 7

```
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <stdlib.h>

int main() {

    int* ptr = malloc(5 * sizeof(int));
    printf("\nOriginal pointer address: %p", (void*)ptr);

    int * newptr = realloc(NULL, 10*sizeof(int));
    printf("\nNew pointer address: %p", (void*)newptr);

    if (newptr != ptr) {
        printf("\nRealloc worked like malloc and returned a new pointer");
    }
    else {
        printf("\nPointer did not change (unexpected)");
    }
    return 0;
}
```

### Task 8

```
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <stdlib.h>

int main() {
    int* arr;
    arr = malloc(10 * sizeof(int));

    for (int i = 0; i < 10; i++) {
        arr[i] = i + 1;
    }
    printf("\nOriginal array\n");
    for (int i = 0; i < 10; i++) {
        printf("%d\t", arr[i]);
    }

    arr = malloc(10 * sizeof(int));
     
    if (arr == NULL) {
        printf("\n\nMemory allocation failed");
        return 1;
    }

    for (int i = 0; i < 10; i++) {
        arr[i] = i + 100;
    }
    printf("\nNew array\n");
    for (int i = 0; i < 10; i++) {
        printf("%d\t", arr[i]);
    }
    return 0;
}
```

### Task 9

```
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <stdlib.h>

int main() {
  
    int n;
    printf("\nHow many integers do you want to store: ");
    scanf("%d", &n);

    int* arr = malloc(n);  //Causes unexpected behaviour on big n input

    for (int i = 0; i < n; i++) {
        arr[i] = i + 1;
    }

    printf("\n");
    for (int i = 0; i < n; i++) {
        printf("%d\t", arr[i]);
    }


    return 0;
}
```

### Task 10

```
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <stdlib.h>

int main() {
  
    int* ptr = malloc(5 * sizeof(int));
    if (ptr == NULL) {
        printf("\nMalloc failed\n");
        return 1;
    }
    for (int i = 0; i < 3; i++) {
        ptr[i] = i + 1;
    }

    printf("\nOriginal array: ");
    for (int i = 0; i < 3; i++) {
        printf("%d\t", ptr[i]);
    }

    int* newptr = realloc(ptr, 10 * sizeof(int));
    if (newptr == NULL) {
        printf("\nRealloc failed");
        return 1;
    }

    free(ptr);

    printf("\nAccessing old pointer after freeing (unsafe): ");
    for (int i = 0; i < 10; i++) {
        printf("%d\t", ptr[i]);
    }



    return 0;
}
```








