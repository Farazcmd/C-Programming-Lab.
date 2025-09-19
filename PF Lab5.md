# Task 1


```
#include <stdio.h>

int main() {
	
	float step1, step2, step3, step4;
	int a, b;
	printf("Enter integer a: ");
	scanf("%d", &a);
	printf("\nEnter integer b: ");
	scanf("%d", &b);
	
	printf("\nExpression is a + b * (a - b) / 2");
	step1 = float(a)-b;
	printf("\nFirst step is (a-b) and result is %.2f", step1);
	step2 = float(step1) / 2;
	printf("\nSecond step is (a-b)/2 and result is %.2f", step2);
	step3 = float(b) * step2;
	printf("\nThird step is b * (a-b)/2 and result is %.2f", step3);
	step4 = a + step3;
	printf("\nFourth step is a + b * (a - b) / 2 and result is %f", step4);
	return 0;
}
```

# Task 2

```
#include <stdio.h>

int main() {
	

	int x, y;
	printf("Enter integer x: ");
	scanf("%d", &x);
	printf("\nEnter integer y: ");
	scanf("%d", &y);
	
	printf("%d", (x>5) && (y<10));
	
	printf("\n%d", (x==10) || (y==5));
	
	printf("\n%d", !(x==y));
	return 0;
}
```

# Task 3

```
#include <stdio.h>
#include <math.h>

int main() {
	
	int num;
	printf("Enter number: ");
	scanf("%d", &num);
	
	printf("The square root of this number is %f", sqrt(num));

	return 0;
}
```

# Task 4

```
#include <stdio.h>

int main() {
	
	int m, n;
	printf("Enter number1: ");
	scanf("%d", &m);
	printf("Enter number2: ");
	scanf("%d", &n);
	
	(m>=n) ? (m==n) ? printf("Equal numbers") : printf("%d is greater than %d", m, n) : printf("%d is greater than %d", n, m) ;

	return 0;
}
```
