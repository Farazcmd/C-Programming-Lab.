### Task 1:

```
#include <stdio.h>

int main() {
// 50 51 21 51 23 84 7 1 5 4
int myArray[10] = {4, 5, 1, 7, 84, 23, 51, 21, 51, 50};
int temp;
int sum = 0;

printf("Original array is: \n");
for (int j = 0; j < 10; j++) {
	printf("%d\n", myArray[j]);

}


for (int i = 0; i < 5; i++) {
	temp = myArray[9-i];
	myArray[9-i] = myArray[i];
	myArray[i] = temp;
}

printf("\nReversed array is: \n");

for (int j = 0; j < 10; j++) {
	printf("%d\n", myArray[j]);
	sum += myArray[j];
}
	printf("\nSum: %d", sum);
	
	
	
	return 0;
}
```



### Task 2:

```
#include <stdio.h>
#include <string.h>

int main() {
	
	int myArray[10] = {4, 5, 1, 7, 84, 23, 51, 21, 51, 50};
	int evenSum = 0, oddSum = 0;
	
	for (int i = 0; i < 10; i++) {
		
		if (myArray[i] % 2 == 0) {
			evenSum += myArray[i];
		} else if (myArray[i] % 2 != 0) {
			oddSum += myArray[i];
		} else {
			printf("Neither odd nor even\n");
		}
		
	}
	
	printf("Odd sum: %d\n", oddSum);
	printf("Even sum: %d\n", evenSum);
	
	return 0;
}
```

### Task 3:

```
#include <stdio.h>
#include <string.h>

int main() {

	char myStr[20];
	printf("Enter string to search: ");
	scanf("%s", &myStr);
	printf("%s", myStr);
	
	int targetCount = 0;
	char target;
	printf("\nEnter target character to count: ");
	scanf(" %c", &target);

	for (int i = 0; i < 20; i++) {
	
	if (myStr[i] == target) {
		printf("\nCharacter found");
		targetCount += 1;
	} 
}
	if (targetCount == 0) {
		printf("\nTarget character not found at all");
	} else {
		printf("\nTarget character found %d times", targetCount);
	}

	
	return 0;
}
```
