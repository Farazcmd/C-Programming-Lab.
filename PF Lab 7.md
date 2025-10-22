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

### Task 4

```
#include <stdio.h>
#include <string.h>

int main() {
	
	int temp;
	int myArray[10] = {19, 51, 21, 63, 24, 74, 12, 22, 16, 17};
	
	for (int i = 0; i < 10; i++) {
		for (int j = 0; j < 10 - 1 - i; j++) {
			
			if (myArray[j] > myArray[j+1]) {
				temp = myArray[j+1];
				myArray[j+1] = myArray[j];
				myArray[j] = temp;
			}
			
		}
	}
	
	printf("Median is %f", (myArray[4] + myArray[5]) / 2.0);
	printf("\nSorted array is: ");
	for (int i = 0; i < 10; i++) {
		printf("\n%d", myArray[i]);
	}
	
	
	return 0;
}
```

### Task 5

```
#include <stdio.h>
#include <string.h>

int main() {
	
	int myArray[10] = {};
	int max, min, maxI = 1, minI = 1, avg = 0;
	
	printf("Enter grade of student 1: ");
	scanf("%d", &myArray[0]);
	max = myArray[0];
	min = myArray[0];
	avg += myArray[0];
	
	for (int i = 1; i < 10; i++) {
		
		printf("\nEnter grade of student %d: ", i + 1);
		scanf("%d", &myArray[i]);
		avg += myArray[i];
		
		if (max < myArray[i]) {
			max = myArray[i];
			maxI = i;
		} 
		if (min > myArray[i]) {
			min = myArray[i];
			minI = i;
		}
		
	}
	
	printf("\nStudent grades are: ");
	
	for (int i = 0; i < 10; i++) {
		printf("\n%d", myArray[i]);
	}
	printf("\nAverage is %f", avg / 10.0);
	printf("\nMaximum grade is %d at index %d",max , maxI);
	printf("\nMinimum grade is %d at index %d",min, minI);
	
	myArray[minI] = 63;
	printf("\nUpdated Student grades are: ");
	
	for (int i = 0; i < 10; i++) {
		printf("\n%d", myArray[i]);
	}
	
	
	
	return 0;
}
```

### Task 6

```
#include <stdio.h>

int main() {
	
	int oldArr[5] = {};
	int newArr[5] = {};
	
	for (int i = 0; i < 5; i++) {
		printf("\nEnter number %d: ", i+1);
		scanf("%d", &oldArr[i]);
		
	}
	
	for (int i = 0; i < 5; i++) {
		newArr[i] = ((oldArr[i] + 10) - 5 ) * 2;
		
	}	
	
	printf("\noriginal numbers are: ");
	for (int i = 0; i < 5; i++) {
		printf("\n%d", oldArr[i]);
		
	}
	
	printf("\nnew numbers are: ");
	
		for (int i = 0; i < 5; i++) {
		printf("\n%d", newArr[i]);
		
	}
	
	return 0;
}


```

### Task 7

```
#include <stdio.h>
#include <string.h>

int main() {
	
	int myArr[10] = {};
	int remove;
	int size =10;
	for (int i = 0; i < 10; i++) {
		printf("\nEnter 3-digit product id %d: ", i+1);
		scanf("%d", &myArr[i]);
		
	}
	
	printf("\nEnter product id to remove: ");
	scanf("%d", &remove);
	
    
    for (int i = 0; i< size; i++) {
    	if (myArr[i] == remove) {
    		for (int j = i; j< size - 1; j++) {
    			myArr[j] = myArr[j+1];
			}
			size--;
    		i--;
		}
	}
	
	for (int i = 0; i < size; i++) {
		printf("\n%d", myArr[i]);
}
	return 0;
}
```

### Task 8

```
#include <stdio.h>
#include <string.h>

int main() {
	
	
	char sttr[100];
	printf("Enter string: ");
	fgets(sttr, 100, stdin);
	
	for (int i = 0; i< 100;i++){
		
	if ((sttr[i] == 'a')||(sttr[i] == 'e')||(sttr[i] == 'i')||(sttr[i] == 'o')||(sttr[i] == 'u') ){
		
		sttr[i] = sttr[i] - 32;
}
	}
	
	printf("%s", sttr);
	return 0;
}
```

### Task 9

```
#include <stdio.h>
#include <string.h>

int main() {
	
	
	int oArr[5] = {};
	int nArr[5] = {};
	int merged[10];
	
	for (int i = 0; i < 5; i++) {
	printf("\nEnter number %d: ", i+1);
	scanf("%d", &oArr[i]);
	}
	for (int i = 0; i < 5; i++) {
	printf("\nEnter number %d: ", i+1);
	scanf("%d", &nArr[i]);
	}
	
	for ( int i = 0; i< 5; i++) {
		merged[i] = oArr[i];
	}
	int i = 5;
	for ( int j = 0; j< 5; j++) {
		merged[i+j] = nArr[j];
	}
	
	for (int k = 0;k<10;k++) {
		printf("\n%d", merged[k]);
	}
	
	return 0;
}
```

### Task 10

```
#include <stdio.h>
#include <string.h>

int main() {
	
	int size;
	printf("how many elements array do you want: ");
	scanf("%d", &size);
	
	int myArr[size];
	
	for (int i =0; i< size; i++) {
		printf("\nEnter value %d: ", i + 1);
		scanf("%d", &myArr[i]);
	}
	
	for (int i =0; i< size; i++) {
		printf("\n%d", myArr[i]);	
	}
	
	int index, val;
	printf("\nwhich element you want to modify? :");
	scanf("%d", &index);
	printf("\nWhat value do you want to put there?: ");
	scanf("%d", &val);
	myArr[index] = val;
	
		for (int i =0; i< size; i++) {
		printf("\n%d", myArr[i]);	
	}
	
	
	return 0;
}
```
