### Task 1

```
#include <stdio.h>

int main() {
	int evenCount, oddCount, num;
	char choice;
 	do {
 		printf("Enter number: ");
 		scanf("%d", &num);
 		
 		if (num % 2 == 0) {
			evenCount += 1;
			printf("Even number");
		} else {
			oddCount += 1;
			printf("Odd number");
		}
 		
 		printf("\nDo you want to continue? (y for yes / n for no): ");
 		scanf(" %c", &choice);

	} while (choice == 'y');
 	
 	printf("Amount of even numbers: %d", evenCount);
 	printf("Amount of odd numbers: %d", oddCount);

 	return 0;
}
```

### Task 2

```
#include <stdio.h>

int main() {

int nnn;
int sum = 0;
int count = 0;
int primeCount = 0;
printf("Enter limit: ");
scanf("%d", &nnn);
int i;
int j;
for (i = 1; i <= nnn; i++) {
	
	for (j = 1; j <= i; j++) {
		if (i % j == 0) {
			count += 1;
		}
	}
	if (count == 2) {
		printf("\n%d is prime number", i);
		sum += i;
		primeCount += 1;
	}
	count = 0;
}

printf("\nSum is %d", sum);
printf("\nPrime number count is %d", primeCount);



	return 0;
}
```
