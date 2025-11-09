Task 1

```
#include <stdio.h>

int square() {
	int num;
	printf("Enter number to square: ");
	scanf("%d", &num);
	return (num*num);
}

int main() {
	
	printf("\nSquare is %d", square());
	return 0;
}
```

Task 2

```
#include <stdio.h>

int main() {
	int arr[5];
	for ( int i = 0; i < 5; i++) {
		printf("\nEnter value for index %d: ", i);
		scanf("%d", &arr[i]);
	}
	int *p = arr;
	for ( int i = 0; i < 5; i++) {
	
	printf("Address of arr[%d]: %d, value: %d\n", i, (p + i), *(p + i));

	}
	

	return 0;
}
```

Task 3

```
#include <stdio.h>

void displayMatrix(int arr[2][3]) {
	for (int i = 0; i < 2; i++) {
		for (int j = 0; j < 3; j++) {
			printf("%d\t", arr[i][j]);
		}
		printf("\n");
	}
}

int calculateSum(int arr[2][3]) {
	int sum = 0;
	for (int i = 0; i < 2; i++) {
		for (int j = 0; j < 3; j++) {
			sum += arr[i][j];
		}
	}
	return sum;
}

float calculateAverage(int arr[2][3]) {
	float sum = 0;
	for (int i = 0; i < 2; i++) {
		for (int j = 0; j < 3; j++) {
			sum += arr[i][j];
		}
	}
	return (sum / 6);
}

int findMax(int arr[2][3]) {
	int max = arr[0][0];
	for (int i = 0; i < 2; i++) {
		for (int j = 0; j < 3; j++) {
			if (arr[i][j] > max) {
				max = arr[i][j];
			}
		}
	}
	return max;
}

int main() {
	
	int matrix[2][3] = {{5, 7, 2}, {6, 1, 7}}; 
	displayMatrix(matrix);
	printf("\nSum is %d", calculateSum(matrix));
	printf("\nAverage is %f", calculateAverage(matrix));
	printf("\nMax is %d", findMax(matrix));
	
	return 0;
}
```

Task 4

```
#include <stdio.h> 

int findMax(int arr[], int size) {
	int max = arr[0];
	for (int i = 0; i < size; i++) {
		
		if (max < arr[i]) {
			max = arr[i];
		}
		
	}
	return max;
}

int main() {
	
	int myArray[9] = {6, 2, 61, 12, 63, 72, 13, 63, 25};

	
	printf("Max value in array is %d", findMax(myArray, 9));
	
	
	return 0;
}
```

Task 5

```
#include <stdio.h>

void swap(int *a, int *b) {
    int temp;
    temp = *a;
    *a = *b;
    *b = temp;
}

int main() {

    int firstVar = 5, secondVar = 10;
    printf("Before swap:");
    printf("\nFirst Variable: %d", firstVar);
    printf("\nSecond Variable: %d", secondVar);
    
    int *c = &firstVar;
    int *d = &secondVar;
    swap(c, d);
    printf("\nAfter swap:");
    printf("\nFirst variable: %d", firstVar);
    printf("\nSecond variable: %d", secondVar);
    
    return 0;
}
```

Task 6

```
#include <stdio.h>
void calculate(int a, int b, int *sum, float *avg) {
    *sum = a+b;
    *avg = *sum / 2.0;
}
int main() {
    
int first = 8, second = 9;
int mySum;
float average;
float *avgPoint = &average;
int *sumPoint = &mySum;
calculate(first, second, sumPoint, avgPoint);
printf("\nSum is %d", mySum);
printf("\nAvg is %.2f", average);
return 0;
}
```

Task 7

```
#include <stdio.h>

int main() {
    
    int *myPointer = NULL;
    
    if (myPointer == NULL) {
        printf("Pointer doesn't reference valid memory\n");
    } else{
        printf("Pointer references valid memory\n");
    }

return 0;
}
```

Task 8

```
#include <stdio.h>

int main() {
    
    void *pointer;
    int a = 7;
    float b = 9.9;
    char c = 'd';
    pointer = &a;
    printf("\nInteger a is %d", *(int *)pointer);
    pointer = &b;
    printf("\nFloat b is %.2f", *(float *)pointer);
    pointer = &c;
    printf("\nCharacter c is %c", *(char *)pointer);

return 0;
}
```

Task 9

```
#include <stdio.h>

float add(int a, int b) {
    return a+b;
}
float subtract(int a, int b) {
    return a-b;
}
float multiply(int a, int b) {
    return a*b;
}
float divide(int a, int b) {
    if (b==0) {
        printf("\nWarning! Division by zero");
        return 0;
    }
    return (float)a/b;
}

int main() {
    int x, y, choice;
    float (*operation)(int, int);
    
    printf("Mini calculator\n");
    printf("\n1. Add\n2. Subtract\n3. Multiply\n4. Divide\n");
    printf("Enter your choice: ");
    scanf("%d", &choice);
    
    printf("\nEnter two numbers: ");
    scanf("%d %d", &x, &y);
    
    switch (choice) {
        case 1:
            operation =(float (*)(int, int)) add;
            break;
            
        case 2:
            operation =(float (*)(int, int)) subtract;
            break;
            
        case 3:
            operation =(float (*)(int, int)) multiply;
            break;
            
        case 4:
            operation = divide;
            break;
            
        default:
            printf("\nInvalid choice");
            return 1;
            break;
    }
    float result = operation(x, y);
    printf("\nResult: %.2f\n", result);
    
    
return 0;
}
```

Task 10

```
#include <stdio.h>
float average(int a, int b, int c) {
    return ((a+b+c) / 3.0);
}

int main() {

printf("Average of 6, 1, 7 is %.2f", average(6, 1, 7));

    return 0;
}
```

