### Task 1

```
#include <stdio.h>

int main() {
	
	int myArray[3][3];
	bool symm = true;
	
	for (int i = 0; i < 3; i++) {
		for (int j = 0; j < 3; j++) {
			printf("Enter element of row %d column %d\n", i+1, j+1);
			scanf("%d", &myArray[i][j]);
		}
	}
	
	int i = 0, j = 0;
	while ((i < 3) && (symm)) {
		j = 0;
		while ((j < 3) && (symm)) {
			if (myArray[i][j] != myArray[j][i]) {
				symm = false;
			}
			j +=1;
		}
		i +=1;
	}
	
	if (symm) {
		printf("Array is symmetric");
	} else {
		printf("Array is not symmetric");
	}
	
	return 0;
}

```

### Task 2

```
#include <stdio.h>

int main() {
	
	int spaces = 8;
	int num = 2;
	
	for (int k = 0; k < 5; k++) {
	
		for (int i = 0; i < spaces; i++) {
			printf(" ");
		}
		spaces -= 2;
		for (int j = 1; j < num; j++) {
			printf("%d ", j);
		}
		num+= 1;
	printf("\n");
}
	
	return 0;
}
```

### Task 3

```
#include <stdio.h>

int main() {
	int n;
	printf("Enter square matrix length: ");
	scanf("%d", &n);
	int matrix[n][n];
	
	for (int i = 0; i < n; i ++) {
		for (int j = 0; j < n; j++) {
			printf("Enter element of row %d column %d: ", i+1, j+1);
			scanf("%d", &matrix[i][j]);
		}
	}
	
	int diag1 = 0, diag2 = 0;
	
	for (int i = 0; i < n; i++) {
		diag1 += matrix[i][i];
		diag2 += matrix[i][n-1-i];
	}
	
	printf("\ndiagonal 1 sum is %d", diag1);
	printf("\ndiagonal 2 sum is %d", diag2);
	
	int sum = 0;
	
	sum = diag1 + diag2;
	
	if (n%2 == 1) {
		sum -= matrix[n/2][n/2];
		
	}
	printf("\nsum is %d", sum);
	return 0;
}
```

### Task 4

```
#include <stdio.h>

int main() {
	
	
	int myArray[3][3];
	
	for (int i = 0; i < 3; i++) {
		for (int j = 0; j < 3; j++) {
			printf("Enter element of row %d column %d\n", i+1, j+1);
			scanf("%d", &myArray[i][j]);
		}
	}

	if ((myArray[1][0] == 0) && (myArray[2][0] == 0) && (myArray[2][1] == 0)) {
		printf("\nTriangle is upper triangular");
	}
	
	if ((myArray[0][1] == 0) && (myArray[0][2] == 0) && (myArray[1][2] == 0)) {
		printf("\nTriangle is lower triangular");
	}
	
	return 0;
}

```

### Task 5

```
#include <stdio.h>

int main() {
	
	int n;
	printf("Enter number of rows for top half of diamond: ");
	scanf("%d", &n);
	
	for (int i = 1; i <= n; i++) {
		
		for (int j = 1; j < n - i +1 ; j++) {
			printf(" ");
		}
		for (int k = 0; k < i; k++) {
			printf("* ");
		}
		printf("\n");
	}
	
		for (int i = n - 1; i >= 1; i--) {
		
		for (int j = n; j > i; j--) {
			printf(" ");
		}
		for (int k = 1; k <= i; k++) {
			printf("* ");
		}
		printf("\n");
	}
	
	
	
	return 0;
}

```

### Task 6

```
#include <stdio.h>

int main() {
	
	int myArray[3][3];
	int myArrayTranspose[3][3];
	
	for (int i = 0; i < 3; i++) {
		for (int j = 0; j < 3; j++) {
			printf("Enter element of row %d column %d\n", i+1, j+1);
			scanf("%d", &myArray[i][j]);
		}
	}
	
	for (int i = 0; i < 3; i++) {
		for (int j = 0; j < 3; j++) {
			myArrayTranspose[j][i] = myArray[i][j];
		}
	}
	
	printf("\nOriginal array: \n");
	for (int i = 0; i < 3; i++) {
		for (int j = 0; j < 3; j++) {
			printf("%d\t", myArray[i][j]);
		}
		printf("\n");
	}
	
	printf("\nTranspose array: \n");
	for (int i = 0; i < 3; i++) {
		for (int j = 0; j < 3; j++) {
			printf("%d\t", myArrayTranspose[i][j]);
		}
		printf("\n");
	}	
	
	return 0;
}

```

### Task 7

```
#include <stdio.h>

int main() {
	
	int matrixB[2][2];
	int matrixA[2][2];
	int matrixC[2][2];
	
	for (int i = 0; i < 2; i++) {
		for (int j = 0; j < 2; j++) {
			printf("Enter element of matrix 1 row %d column %d\n", i+1, j+1);
			scanf("%d", &matrixA[i][j]);
		}
	}
	
	
	for (int i = 0; i < 2; i++) {
		for (int j = 0; j < 2; j++) {
			printf("Enter element of matrix 2 row %d column %d\n", i+1, j+1);
			scanf("%d", &matrixB[i][j]);
		}
	}
	
	for (int i = 0; i < 2; i++) {
		for (int j = 0; j < 2; j++) {
			matrixC[i][j] = 0;
			
			for (int k = 0; k < 2; k++) {
				matrixC[i][j] += matrixA[i][k] * matrixB[k][j];
			}
			
		}
	}
	
	printf("\nResultant matrix is: \n");
	for (int i = 0; i < 2; i++) {
		for (int j = 0; j < 2; j++) {
			printf("%d\t",matrixC[i][j]);
		}
		printf("\n");
	}
	
	return 0;
}

```

### Task 8

```
#include <stdio.h>

int main() {
	
	int zeroCount = 0, evenCount = 0, oddCount = 0, posCount = 0, negCount = 0;
	
	int myArray[3][3];
	
	for (int i = 0; i < 3; i++) {
		for (int j = 0; j < 3; j++) {
			printf("Enter element of row %d column %d\n", i+1, j+1);
			scanf("%d", &myArray[i][j]);
		}
	}
	
	for (int i = 0; i < 3; i++) {
		for (int j = 0; j < 3; j++) {
	
			if (myArray[i][j] % 2 == 0) {
				evenCount += 1;
			} else {
				oddCount += 1;
			}
			if (myArray[i][j] == 0) {
				zeroCount += 1;
			} else if (myArray[i][j] > 0) {
				posCount += 1;
			} else {
				negCount += 1;
			}
			
		}
	}
	
	printf("\nZero count is %d", zeroCount);
	printf("\nPositive number count is %d", posCount);
	printf("\nNegative number count is %d", negCount);
	printf("\nEven number count is %d", evenCount);
	printf("\nOdd number count is %d", oddCount);
	
	return 0;
}

```

### Task 9

```
#include <stdio.h>

int main() {
	
	int myArray[3][3];
	int myArrayRotate[3][3];
	
	for (int i = 0; i < 3; i++) {
		for (int j = 0; j < 3; j++) {
			printf("Enter element of row %d column %d\n", i+1, j+1);
			scanf("%d", &myArray[i][j]);
		}
	}
	
	for (int i = 0; i < 3; i++) {
		for (int j = 0; j < 3; j++) {
			myArrayRotate[j][i] = myArray[i][j];
		}
	}
	
	int temp;
	
	for (int i = 0; i < 3; i++) {
	
		temp = myArrayRotate[i][0];
		myArrayRotate[i][0] = myArrayRotate[i][2];
		myArrayRotate[i][2] = temp;
		
	}
	
	for (int i = 0; i < 3; i++) {
		for (int j = 0; j < 3; j++) {
			if (myArrayRotate[i][j] != myArray[i][j]) {
				printf("\nValue not same\n");
			}
		}
	}
	
	for (int i = 0; i < 3; i++) {
		for (int j = 0; j < 3; j++) {
			printf("%d\t", myArrayRotate[i][j]);
		}
		printf("\n");
	}
	
	
	return 0;
}

```

### Task 10

```
#include <stdio.h>

int main() {
	
	int n;
	printf("Enter number of rows for pascal triangle: ");
	scanf("%d", &n);
	
	for (int i = 0; i < n; i++) {
		
		for (int space = 0; space < n - i - 1; space++) {
			printf("  ");
		}
		
		int value = 1;
		
		for (int j = 0; j <= i; j++) {
			printf("%4d", value);
			value = value * (i-j) / (j+1);
		}
		printf("\n");
	}
	
	return 0;
}

```


