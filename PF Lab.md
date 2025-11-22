### Task 1

```

#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>

int sumRecursive(long long n) {
	if (n == 0) {
		return 0;
	}

	return ((n % 10) + sumRecursive(n / 10));
}

int main () {

	long long num;
	printf("\nEnter a long number to sum the digits of: ");
	scanf("%lld", &num);

	printf("Sum is %d", sumRecursive(num));

	return 0;
}

```

### Task 2

```
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>


int main() {
	

	struct catalog
	{
		char title[50];
		char author[50];
		int pageCount;
		float price;
	} myCatalog;

	printf("\nEnter title of book: ");
	fgets(myCatalog.title, sizeof(myCatalog.title), stdin);
	printf("\nEnter author's name: ");
	fgets(myCatalog.author, sizeof(myCatalog.author), stdin);
	printf("\nEnter amount of pages of the book: ");
	scanf("%d", &myCatalog.pageCount);
	printf("\nEnter price: ");
	scanf("%f", &myCatalog.price);

	printf("\nTitle: %s", myCatalog.title);
	printf("\nAuthor: %s", myCatalog.author);
	printf("\nPage count: %d", myCatalog.pageCount);
	printf("\nPrice: %.2f", myCatalog.price);

	return 0;
}

```

### Task 3

```
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>
void clearInputBuffer() {
	int c;
	while ((c = getchar()) != '\n' && c != EOF);
}

int i = 0;
struct flightManagement
{
	int flight_number;
	char departure_city[50];
	char destination_city[50];
	char date[30];
	int available_seats;
};

struct flightManagement allFlights[10];

void displayDetails() {
	for (int j = 0; j < i; j++) {
		printf("\nFlight number is %d", allFlights[j].flight_number);
		printf("\nFlight departure city is %s", allFlights[j].departure_city);
		printf("\nFlight destination city is %s", allFlights[j].destination_city);
		printf("\nFlight date is %s", allFlights[j].date);
		printf("\nFlight available seats are %d", allFlights[j].available_seats);
		printf("\n\n");
	}
}

void bookSeat() {
	int flightnum;
	printf("\nEnter flight number of the flight you want to book:");
	scanf("%d", &flightnum);
	for (int i = 0; i < 10; i++) {
		if (allFlights[i].flight_number == flightnum) {
			allFlights[i].available_seats--;
		}
	}
}
int main() {



	int userCh, userCh2;


	do {
		printf("\nEnter 1 to add flights\nEnter 2 to book a seat\nEnter 3 to display all flights\n");
		scanf("%d", &userCh);

		switch (userCh) {
		case 1:
			do {
				printf("\nEnter flight number: ");
				scanf("%d", &allFlights[i].flight_number);
				clearInputBuffer();
				printf("\nEnter departure city: ");
				fgets(allFlights[i].departure_city, sizeof(allFlights[i].departure_city), stdin);
				printf("\nEnter destination city: ");
				fgets(allFlights[i].destination_city, sizeof(allFlights[i].destination_city), stdin);
				printf("\nEnter date of flight: ");
				fgets(allFlights[i].date, sizeof(allFlights[i].date), stdin);
				printf("\nEnter available seats: ");
				scanf("%d", &allFlights[i].available_seats);
				i++;
				printf("\nDo you want to add another flight? (1 for yes, 0 for no): ");
				scanf("%d", &userCh2);

			} while (userCh2 != 0);

			break;

		case 2:
			bookSeat();
			break;

		case 3:
			displayDetails();
			break;
		}

		printf("\nDo you want to continue? (1 for yes, 0 for no): ");
		scanf("%d", &userCh2);

	} while (userCh2 != 0);
	return 0;
}

```

### Task 4

```
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>

#define PI 3.14159265358979323846

int main () {

	float area, radius, circumference;
	printf("\nEnter radius: ");
	scanf("%f", &radius);

	area = PI * radius * radius;
	printf("\nArea is %.2f", area);
	circumference = 2 * PI * radius;
	printf("\nCircumference is %.2f", circumference);

	return 0;
}

```

### Task 5

```
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>

void reverse(char str[], int start, int end) {
	if (start >= end) {
		return;
	}
	char temp = str[start];
	str[start] = str[end];
	str[end] = temp;

	reverse(str, start + 1, end - 1);
}

int main () {
	char message[100];
	printf("\nEnter encoded message: ");
	fgets(message, sizeof(message), stdin);
	message[strcspn(message, "\n")] = '\0';
	printf("\nMessage before decoding is %s", message);
	reverse(message, 0, strlen(message) - 1);
	printf("\nDecoded message is %s", message);
	return 0;
}


```

### Task 6

```
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>

float expCalc(float base, int exp) {

	if (exp == 0) {
		return 1;
	}
	else if (exp == 1) {
		return base;
	}

	return base * expCalc(base, exp - 1);
}

int main () {
	float base;
	int exponent;
	printf("\nEnter base:");
	scanf("%f", &base);
	printf("\nEnter positive integer exponent:");
	scanf("%d", &exponent);
	printf("\nResult is %f", expCalc(base, exponent));

	return 0;
}

```

### Task 7

```
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>



int main () {
	
	struct Dept {
		char name[50];
		char DeptNum[20];
	};

	struct student {
		char id[20];
		char name[50];
		float CGPA;
		struct Dept department;
	};

	struct student Student1;

	strcpy(Student1.id, "535sdf32");
	strcpy(Student1.name, "Muhammad Faraz");
	Student1.CGPA = 3.63;
	strcpy(Student1.department.name, "Computer Science");
	strcpy(Student1.department.DeptNum, "ad242a");
	
	printf("\nStudent1's id: %s", Student1.id);
	printf("\nStudent1's name: %s", Student1.name);
	printf("\nStudent1's CGPA: %f", Student1.CGPA);
	printf("\nStudent1's department's name: %s", Student1.department.name);
	printf("\nStudent1's department's number: %s", Student1.department.DeptNum);

	return 0;
}

```

### Task 8

```
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>



int main () {
	
	struct employee {
		char id[20];
		char name[50];
		float salary;
		char position[30];
	};

	struct employee arr[5];

	for (int i = 0; i < 5; i++) {
		printf("%d", i + 1);
		printf("\nEnter ID of employee %d: ", i + 1);
		fgets(arr[i].id, sizeof(arr[i].id), stdin);
		printf("\nEnter name of employee %d: ", i + 1);
		fgets(arr[i].name, sizeof(arr[i].name), stdin);
		printf("\nEnter salary of employee %d: ", i + 1);
		scanf("%f", &arr[i].salary);
		getchar();
		printf("\nEnter position of employee %d: ", i + 1);
		fgets(arr[i].position, sizeof(arr[i].position), stdin);
	}
	float max = 0;
	int index = 0;
	for (int i = 0; i < 5; i++) {
		if (max < arr[i].salary) {
			max = arr[i].salary;
			index = i;
		}
	}
	printf("\nEmployee with name %s has the highest salary: %.2f", arr[index].name, arr[index].salary);

	return 0;
}

```

### Task 9

```
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>

void track() {
	static int count = 0;
	count++;
	printf("\nFunction 'track' has been called %d times.", count);
}

int main () {
	track();
	track();
	track();
	return 0;
}

```

### Task 10

```
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>
int movieCount = 0;
struct Movie {
	char title[50];
	char genre[50];
	char director[50];
	int release_year;
	float rating;
};

struct Movie movies[10];
void addMovie() {
	if (movieCount >= 10) {
		printf("\nNo more movies can be added");
		return;
	}
	printf("\nMax movies to be added is 10: ");
	printf("\nEnter title of movie: ");
	getchar();
	fgets(movies[movieCount].title, sizeof(movies[movieCount].title), stdin);
	printf("\nEnter genre of movie: ");
	fgets(movies[movieCount].genre, sizeof(movies[movieCount].genre), stdin);
	printf("\nEnter director of movie: ");
	fgets(movies[movieCount].director, sizeof(movies[movieCount].director), stdin);
	printf("\nEnter release year of movie: ");
	scanf("%d", &movies[movieCount].release_year);
	printf("\nEnter rating of movie: ");
	scanf("%f", &movies[movieCount].rating);
	movieCount++;
}

void searchByGenre() {
	int found = 0;
	char search[50];
	printf("\nEnter genre to search, if a movie with matching genre is present, its title will be printed: ");
	getchar();
	fgets(search, sizeof(search), stdin);
	for (int i = 0; i < movieCount; i++) {
		if (strcmp(search, movies[i].genre) == 0) {
			printf("\n%s", movies[i].title);
			found = 1;
		}
	}
	if (found == 0) {
		printf("\nNo movies of this genre");
	}
}

void displayMovies() {
	for (int i = 0; i < movieCount; i++) {
		printf("\nMovie %d", i + 1);
		printf("\nTitle; %s", movies[i].title);
		printf("\nGenre: %s", movies[i].genre);
		printf("\nDirector: %s", movies[i].director);
		printf("\nRelease year: %d", movies[i].release_year);
		printf("\nRating: %f", movies[i].rating);
	}
	printf("\n");
}

int main () {
	int userCh;
	do {
		
		printf("\nMenu\n1. Add movie\n2. Search by genre\n3. Display all movies\n4. Exit\nSelect your choice: ");
		scanf("%d", &userCh);
		switch (userCh) {
			case 1:
				addMovie();
				break;

			case 2:
				searchByGenre();
				break;

			case 3:
				displayMovies();
				break;
		}

	} while (userCh != 4);


	return 0;
}

```
