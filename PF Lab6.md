## PF Lab 6 tasks

### Task 5

```
#include <stdio.h>

int main() {
    
    int num;
    printf("Enter course number 1, 2, or 3: ");
    scanf("%d", &num);
    char grade;
    switch (num) {
        
        case 1:
            printf("\nEnter grade for this course: ");
            scanf(" %c", &grade);
            switch (grade) {
                case 'A':
                    printf("\nYou performed excellent. ");
                    break;
                case 'B':
                    printf("\nYou performed good.");
                    break;
                case 'C':
                    printf("\nYou performed mediocre.");
                    break;
                case 'D':
                    printf("\nYou performed bad.");
                case 'F':
                    printf("\nYou failed. ");
                    break;
                default:
                    printf("\nInvalid input.");
                    break;
            }
            break;
            
        case 2:
            printf("\nEnter grade for this course: ");
            scanf(" %c", &grade);
            switch (grade) {
                case 'A':
                    printf("\nYou performed excellent. ");
                    break;
                case 'B':
                    printf("\nYou performed good.");
                    break;
                case 'C':
                    printf("\nYou performed mediocre.");
                    break;
                case 'D':
                    printf("\nYou performed bad.");
                case 'F':
                    printf("\nYou failed. ");
                    break;
                default:
                    printf("\nInvalid input.");
                    break;
            }
            break;
            
        case 3:
            printf("\nEnter grade for this course: ");
            scanf(" %c", &grade);
            switch (grade) {
                case 'A':
                    printf("\nYou performed excellent. ");
                    break;
                case 'B':
                    printf("\nYou performed good.");
                    break;
                case 'C':
                    printf("\nYou performed mediocre.");
                    break;
                case 'D':
                    printf("\nYou performed bad.");
                case 'F':
                    printf("\nYou failed. ");
                    break;
                default:
                    printf("\nInvalid input.");
                    break;
            }
            break;
            
        default:
            printf("\nInvalid input");
    }

    return 0;
}
```

### Task 6

```
#include <stdio.h>

int main() {
    
    int num1, num2, num3;
    printf("Enter first number: ");
    scanf("%d", &num1);
    printf("Enter second number: ");
    scanf("%d", &num2);
    printf("Enter third number: ");
    scanf("%d", &num3);
    
    (num1 > num2) ? (num1 > num3) ? printf("First number is largest") : printf("Third number is largest") : (num2 > num3) ? printf("Second number is largest") : printf("Third number is largest");
    
    return 0;
}
```

### Task 7

```
#include <stdio.h>

int main() {
    
    int a, b;
    printf("Enter first number: ");
    scanf("%d", &a);
    printf("\nEnter second number: ");
    scanf("%d", &b);
 
    printf("\nSum of a and b is: %d", a + b);
    printf("\nDifference between a and b is: %d", a - b);
    printf("\nProduct of a and b is: %d", a * b);
    printf("\nQuotient of a and b is: %f", (float)a / b);
    printf("\nRemainder when a is divided by b is: %d", a % b);
    
    return 0;
}
```

### Task 8

```
#include <stdio.h>

int main() {
    
    int a, b;
    printf("Enter first number: ");
    scanf("%d", &a);
    printf("\nEnter second number: ");
    scanf("%d", &b);
    
    printf("\n1 is for true and 0 is for false");
    printf("\na == b? %d", a==b);
    printf("\na > b? %d", a > b);
    printf("\na < b %d", a < b);
    printf("\na != b %d", a != b);
    printf("\na >= b? %d", a >= b);
    printf("\na <= b? %d", a <= b);    
    return 0;
}
```

### Task 9

```
#include <stdio.h>

int main() {
    
    int a, b;
    printf("Enter first number: ");
    scanf("%d", &a);
    printf("\nEnter second number: ");
    scanf("%d", &b);
    
    printf("\n1 is for true and 0 is for false");
    printf("\na & b = %d", a & b);
    printf("\na | b? = %d", a | b);
    printf("\n~a = %d", ~a);
    printf("\na << 1 = %d", a << 1);
    printf("\na >> 1 = %d", a >> 1);    
    return 0;
}
```

### Task 10

```
#include <stdio.h>

int main() {
    
    int x, y, z;
    printf("Enter first number: ");
    scanf("%d", &x);
    printf("\nEnter second number: ");
    scanf("%d", &y);
    printf("\nEnter third number: ");
    scanf("%d", &z);
    
    if (x > z) {
        if (x > y) {
            printf("\nFirst number is largest.");
        } else {
            printf("\nSecond number is largest.");
        }
    }   else {
        if (y > z) {
            printf("\nSecond number is largest.");
        } else {
            printf("\nThird number is largest.");
        }
    }

    return 0;
}
```
