# EX-26-AREA-OF-RECTANGLE-USING- POINTER
## AIM
To write a C Program to find area of rectangle using pointer.

## ALGORITHM
1.	Start the program.
2.	Read two numbers.
3.	Calculate the area of rectangle using the formula area=(x)(*y)
4.	Display the result.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>

int main() {
    float length, width;
    float *ptrLength, *ptrWidth, area;

    // Pointers to store length and width
    ptrLength = &length;
    ptrWidth = &width;

    // Input the length and width of the rectangle
    printf("Enter the length of the rectangle: ");
    scanf("%f", ptrLength);  // Using pointer to read length

    printf("Enter the width of the rectangle: ");
    scanf("%f", ptrWidth);   // Using pointer to read width

    // Calculate the area of the rectangle using the pointers
    area = (*ptrLength) * (*ptrWidth);  // Dereferencing the pointers to calculate area

    // Display the result
    printf("The area of the rectangle is: %.2f\n", area);

    return 0;
}

```
## OUTPUT
![image](https://github.com/user-attachments/assets/58cf7fbf-fc9b-49f8-b06a-a00c0c327320)
		       	


## RESULT
Thus the program to find area of rectangle using pointer has been executed successfully
 
 


# EX-27-DYNAMIC-MEMORY-ALLOCATION
## AIM
To write a C Program to print 'WELCOME' using malloc() and free().

## ALGORITHM
1.	Start the program.
2.	Read a string variable.
3.	Allocate memory using malloc().
4.	Display the string.
5.	Remove the allocated memory using free().
6.	Stop the program.

## PROGRAM
```
#include <stdio.h>
#include <stdlib.h>  // For malloc() and free()

int main() {
    // Dynamically allocate memory to store the string "WELCOME"
    char *str = (char *)malloc(8 * sizeof(char));  // 7 characters + 1 for null terminator '\0'

    // Check if malloc returned NULL (memory allocation failed)
    if (str == NULL) {
        printf("Memory allocation failed!\n");
        return 1;  // Exit if memory allocation fails
    }

    // Copy "WELCOME" into the allocated memory
    str[0] = 'W';
    str[1] = 'E';
    str[2] = 'L';
    str[3] = 'C';
    str[4] = 'O';
    str[5] = 'M';
    str[6] = 'E';
    str[7] = '\0';  // Null terminator

    // Print the string
    printf("String: %s\n", str);

    // Free the dynamically allocated memory
    free(str);

    return 0;
}

```
## OUTPUT

![image](https://github.com/user-attachments/assets/5ce1296d-c240-4101-a764-2bd88dc15e19)


## RESULT
Thus the program to print 'WELCOME' using malloc() and free() has been executed successfully
 
.



# EX-28-STUDENT-INFORMATION-USING-STRUCTURE

## AIM

To write a C Program to store the student information and display it using structure.

## ALGORITHM

1.	Start the program.
2.	Create a student structure with name, roll number and marks as members.
3.	Using structure variable read the structure members and print them.
4.	Stop the program.

## PROGRAM
```
#include <stdio.h>
#include <string.h>

// Define a structure to store student information
struct Student {
    char name[50];  // To store the student's name
    int rollNo;     // To store the student's roll number
    float marks;    // To store the student's marks
};

int main() {
    struct Student student;  // Declare a variable of type struct Student

    // Input the student's information
    printf("Enter student name: ");
    fgets(student.name, sizeof(student.name), stdin);
    student.name[strcspn(student.name, "\n")] = '\0';  // Remove the newline character at the end of the name

    printf("Enter roll number: ");
    scanf("%d", &student.rollNo);

    printf("Enter marks: ");
    scanf("%f", &student.marks);

    // Display the stored information
    printf("\n--- Student Information ---\n");
    printf("Name: %s\n", student.name);
    printf("Roll Number: %d\n", student.rollNo);
    printf("Marks: %.2f\n", student.marks);

    return 0;
}

```

## OUTPUT
![image](https://github.com/user-attachments/assets/60b00db3-4062-4d8c-a68e-3085885133d0)


## RESULT

Thus the program to store the student information and display it using structure has been executed successfully
 
 


# EX-29-EMPLOYEE-STRUCTURE-SALARY-CALCULATION

## AIM

To write a C Program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure.

## ALGORITHM

1.	Start the program.
2.	Create an employee structure with name, id and salary details as members.
3.	Using structure variable read the structure members.
4.	Calculate the gross salary and print the details.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>

// Define a structure to store employee information
struct Employee {
    char name[50];          // To store employee's name
    float basicSalary;      // Basic salary of the employee
    float hra;              // House Rent Allowance
    float specialAllowance; // Special Allowance
    float grossSalary;      // To store the gross salary (calculated)
};

// Function to calculate gross salary
void calculateGrossSalary(struct Employee *emp) {
    emp->grossSalary = emp->basicSalary + emp->hra + emp->specialAllowance;
}

int main() {
    struct Employee employees[3];  // Array to store data for 3 employees

    // Input data for 3 employees
    for (int i = 0; i < 3; i++) {
        printf("Enter details for Employee %d:\n", i + 1);

        // Input employee name
        printf("Enter name: ");
        getchar(); // To clear the newline left by previous scanf
        fgets(employees[i].name, sizeof(employees[i].name), stdin);
        employees[i].name[strcspn(employees[i].name, "\n")] = '\0';  // Remove trailing newline from name

        // Input basic salary, HRA, and special allowance
        printf("Enter basic salary: ");
        scanf("%f", &employees[i].basicSalary);

        printf("Enter house rent allowance (HRA): ");
        scanf("%f", &employees[i].hra);

        printf("Enter special allowance: ");
        scanf("%f", &employees[i].specialAllowance);

        // Calculate gross salary
        calculateGrossSalary(&employees[i]);
    }

    // Display the details and gross salary of all employees
    printf("\n--- Employee Details and Gross Salary ---\n");
    for (int i = 0; i < 3; i++) {
        printf("\nEmployee %d:\n", i + 1);
        printf("Name: %s\n", employees[i].name);
        printf("Basic Salary: %.2f\n", employees[i].basicSalary);
        printf("House Rent Allowance (HRA): %.2f\n", employees[i].hra);
        printf("Special Allowance: %.2f\n", employees[i].specialAllowance);
        printf("Gross Salary: %.2f\n", employees[i].grossSalary);
    }

    return 0;
}

```

 ## OUTPUT

 ![image](https://github.com/user-attachments/assets/acc5dd0e-86a8-4175-ba7c-3a3d48bd8f9f)


## RESULT

Thus the C program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure
 




# EX – 30 -STUDENTS MARK -TOTAL &AVERAGE USING STRUCURE

## AIM
Create a C program to calculate the total and average of student using structure.

## ALGORITHM 

Step 1: Start the program.
Step 2: Define a struct student with:
•	name: a character array (size 10) for the student's name (not used in the logic).
•	rollno: an integer for the student's roll number (also unused).
•	subject[5]: an array to store marks of 5 subjects.
•	total: an integer to store total marks.
Step 3: Declare an array s[2] of type struct student for 2 students. Also declare variables n, i, and j for input 
             and iteration.
Step 4: Input Loop (i = 0 to 1):
•	Read an integer n (but it's not used later — possibly intended for roll number or placeholder).
•	Loop j = 0 to 4:
o	Read 5 subject marks into s[i].subject[j].
Step 5: Total Marks Calculation Loop (i = 0 to 1):
•	Initialize s[i].total to 0.
•	Loop j = 0 to 4:
o	Add each subject mark to s[i].total.
Step 6: Override Total (Hardcoded):
•	Set s[0].total = 374;
•	Set s[1].total = 383;
           This step overwrites the computed totals. It seems like testing or hardcoded totals — unnecessary if you’re 
                 already calculating them.
Step 7: Output Loop (i = 0 to 1):
•	Print s[i].total for each student.
Step 8: End the program.

## PROGRAM
```
#include <stdio.h>

// Defining the structure for a student
struct Student {
    char name[50];
    int marks[5];  // Assuming there are 5 subjects
    float total;
    float average;
};

// Function to calculate total and average
void calculate(struct Student *s) {
    s->total = 0;
    for (int i = 0; i < 5; i++) {
        s->total += s->marks[i];
    }
    s->average = s->total / 5;
}

int main() {
    struct Student student;  // Declare a variable of type Student
    
    // Input student details
    printf("Enter the student's name: ");
    fgets(student.name, sizeof(student.name), stdin);
    
    // Input marks for 5 subjects
    printf("Enter marks for 5 subjects:\n");
    for (int i = 0; i < 5; i++) {
        printf("Subject %d: ", i + 1);
        scanf("%d", &student.marks[i]);
    }
    
    // Calculate total and average
    calculate(&student);
    
    // Output the results
    printf("\nStudent's Name: %s", student.name);
    printf("Total Marks: %.2f\n", student.total);
    printf("Average Marks: %.2f\n", student.average);
    
    return 0;
}

```

## OUTPUT
![image](https://github.com/user-attachments/assets/cfab84c1-13f7-4d52-b8bd-58057c34bd25)

 

## RESULT

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	


