# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M6
# IAPR-6- Module 6 - FoC
## 11. Implementation of the concept of pointer to function.
## 12. Implementation of programs using structure and union.
## 13. Implementation of programs for different storage classes.
# Ex.No:26
  Develop a C program using static storage class in function with parameter and without return to display the incremental float values as indicated in the following output.
| Input | Output                                       |
|-------|----------------------------------------------|
| 1     | 101.25&nbsp;&nbsp;201.50&nbsp;&nbsp;301.75&nbsp;&nbsp;402.00&nbsp;&nbsp;502.75 |
# Date :
# Aim:
To develop a C program using the static storage class in a function with a parameter and without a return value to display the required output.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3:
  a. Declare an integer variable `input` to store the user’s number.  
  b. Inside the function `display(int n)`, declare a static float variable `base` and initialize it to 100.25.
### Step 4:
  Read an integer from the user and store it in `input`.
### Step 5:
  Call the function `display(input)` five times.
### Step 6:
  Inside the `display` function, for each call:  
  a. Calculate the sum of `base` and `n`.  
  b. Display the value.  
  c. Increase the value of `base` by 100.25.
### Step 7:
  Repeat Step 6 for all function calls.
### Step 8:
  Stop
# Program:
```
#include <stdio.h>

// Step 3b: Function with parameter and static variable
void display(int n) {
    static float base = 100.25;  // static variable retains its value across calls
    float sum;

    // Step 6a: Calculate sum
    sum = base + n;

    // Step 6b: Display value
    printf("%.2f\t", sum);

    // Step 6c: Increment base
    base += 100.25;
}

int main() {
    int input;

    // Step 4: Read integer from user
    printf("Enter an integer: ");
    scanf("%d", &input);

    // Step 5: Call display() five times
    for (int i = 0; i < 5; i++) {
        display(input);
    }

    printf("\n");
    return 0;
}

}
```
# Output:

<img width="381" height="183" alt="image" src="https://github.com/user-attachments/assets/a61e7fb4-dcbb-4280-a5ff-e27b76718a91" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M6
# IAPR-6- Module 6 - FoC
# Ex.No:27
  Implement a C program to perform arithmetic operations (addition, subtraction, multiplication, division) on two integers using function pointers. The user should input two numbers and select the desired operation from a menu.
# Date : 
# Aim:
  To implement a C program that uses function pointers to perform arithmetic operations (add, subtract, multiply, divide) on two integers based on user choice.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3:
  Declare four functions to perform arithmetic operations:  
  - `add(int a, int b)`  
  - `subtract(int a, int b)`  
  - `multiply(int a, int b)`  
  - `divide(int a, int b)`
### Step 4:
  Declare a function pointer `int (*operation)(int, int)` to point to any of the arithmetic functions.
### Step 5:
  Input two integers from the user (`num1` and `num2`).
### Step 6:
  Display a menu for the user to choose an operation:  
  - Add  
  - Subtract  
  - Multiply  
  - Divide
### Step 7:
  Read the user’s choice.
### Step 8:
  Use a switch statement to assign the function pointer `operation` to the appropriate function based on the user’s choice.  
  - **Step 8.1:** If the choice is 4 (divide), check if the second number is zero. If yes, display an error and terminate.  
  - **Step 8.2:** If the choice is invalid, display an error and terminate.
### Step 9:
  Call the function using the function pointer and store the result in a variable `result`.
### Step 10:
  Display the result.
### Step 11:
  Stop
# Program:
```
#include <stdio.h>

// Step 3: Arithmetic functions
int add(int a, int b) {
    return a + b;
}

int subtract(int a, int b) {
    return a - b;
}

int multiply(int a, int b) {
    return a * b;
}

int divide(int a, int b) {
    return a / b;  // integer division
}

int main() {
    int num1, num2, choice, result;
    int (*operation)(int, int);  // Step 4: Function pointer

    // Step 5: Input two integers
    printf("Enter two integers: ");
    scanf("%d %d", &num1, &num2);

    // Step 6: Display menu
    printf("\nChoose an operation:\n");
    printf("1. Add\n");
    printf("2. Subtract\n");
    printf("3. Multiply\n");
    printf("4. Divide\n");
    printf("Enter your choice: ");
    scanf("%d", &choice);

    // Step 8: Assign function pointer
    switch (choice) {
        case 1:
            operation = add;
            break;
        case 2:
            operation = subtract;
            break;
        case 3:
            operation = multiply;
            break;
        case 4:
            if (num2 == 0) {
                printf("Error: Division by zero is not allowed.\n");
                return 1; // terminate program
            }
            operation = divide;
            break;
        default:
            printf("Invalid choice!\n");
            return 1; // terminate program
    }

    // Step 9: Call function via pointer
    result = operation(num1, num2);

    // Step 10: Display result
    printf("Result = %d\n", result);

    return 0;
}
```
# Output:

<img width="298" height="249" alt="image" src="https://github.com/user-attachments/assets/e2e17c02-a195-435c-9cc2-91405c54bd16" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.

# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M6
# IAPR-6- Module 6 - FoC
# Ex.No:28
  Develop a C program to store details of n employees (employee number, name, and salary) using structures, and display the employee(s) with the highest salary.
# Date : 
# Aim:
  To develop and implement a C program that uses a structure to store employee details (employee number, name, and salary) and determine the employee(s) with the highest salary.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3:
  Define a structure `employee` with the following members:  
  - `eno` (employee number)  
  - `ename` (employee name)  
  - `salary` (employee salary)
### Step 4:
  Declare an array of structures to store details of multiple employees.
### Step 5:
  Input the number of employees, `n`.
### Step 6:
  For each employee (`i = 0` to `n-1`), do the following:  
  - **Step 6.1:** Input employee number.  
  - **Step 6.2:** Input employee name (allow spaces).  
  - **Step 6.3:** Input employee salary.  
  - **Step 6.4 (Optional):** Print the entered details for verification.
### Step 7:
  Initialize a variable `high` with the salary of the first employee.
### Step 8:
  For each employee (`i = 1` to `n-1`), do the following:  
  - **Step 8.1:** Compare employee salary with `high`.  
  - **Step 8.2:** If the salary is greater than `high`, update `high` with this salary.
### Step 9:
  Print the details of employee(s) whose salary matches `high`:  
  - **Step 9.1:** Loop through all employees.  
  - **Step 9.2:** If employee salary equals `high`, print employee number, name, and salary.
### Step 10:
  Stop
# Program:
```
#include <stdio.h>

// Step 3: Define structure
struct employee {
    int eno;           // employee number
    char ename[50];    // employee name
    float salary;      // employee salary
};

int main() {
    struct employee emp[50];  // Step 4: Array of structures
    int n, i;
    float high;

    // Step 5: Input number of employees
    printf("Enter the number of employees: ");
    scanf("%d", &n);

    // Step 6: Input employee details
    for (i = 0; i < n; i++) {
        printf("\nEnter details of employee %d:\n", i + 1);
        printf("Employee Number: ");
        scanf("%d", &emp[i].eno);
        printf("Employee Name: ");
        scanf(" %[^\n]", emp[i].ename);  // allows spaces in name
        printf("Employee Salary: ");
        scanf("%f", &emp[i].salary);
    }

    // Step 7: Initialize high with first employee's salary
    high = emp[0].salary;

    // Step 8: Find highest salary
    for (i = 1; i < n; i++) {
        if (emp[i].salary > high) {
            high = emp[i].salary;
        }
    }

    // Step 9: Print employees with highest salary
    printf("\nEmployee(s) with the highest salary:\n");
    for (i = 0; i < n; i++) {
        if (emp[i].salary == high) {
            printf("Employee Number: %d\n", emp[i].eno);
            printf("Employee Name  : %s\n", emp[i].ename);
            printf("Employee Salary: %.2f\n\n", emp[i].salary);
        }
    }

    return 0;
}
```
# Output:
<img width="451" height="768" alt="image" src="https://github.com/user-attachments/assets/0b102b35-9acf-4b06-ba68-84278e7f63f2" />

<img width="446" height="143" alt="image" src="https://github.com/user-attachments/assets/9fc9718f-b370-410b-859c-548e913d0232" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M6
# IAPR-6- Module 6 - FoC
# Ex.No:29
  Create the C program to calculate the present age of a person by passing structure as a reference.
# Date : 
# Aim:
  To create a C program that uses a structure to store the current date and birth date, and to calculate the person’s present age in years, months, and days by passing the structure as a reference.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3:
  Define a structure named `date` with members to store:  
  - Current date (`c_date`, `c_month`, `c_year`)  
  - Birth date (`b_date`, `b_month`, `b_year`)  
  - Calculated age (`cal_date`, `cal_month`, `cal_year`)
### Step 4:
  Initialize a structure variable with the current date and birth date values.
### Step 5:
  Pass the structure variable to a function `findAge()` by reference.
### Step 6:
  Inside `findAge()`:  
  - a. Declare an integer array `month[]` to store the number of days in each month.  
  - b. If the birth date is greater than the current date:  
     - Add the number of days of the previous month to the current date.  
     - Decrease the current month by 1.  
  - c. If the birth month is greater than the current month:  
     - Decrease the current year by 1.  
     - Add 12 to the current month.  
  - d. Calculate the age in days, months, and years by subtracting the corresponding birth values from the current values.
### Step 7:
  Return the structure pointer containing the calculated age.
### Step 8:
  Display the calculated age (years, months, and days) in the `main` function.
### Step 9:
  Stop
# Program:
```
#include <stdio.h>

// Step 3: Define structure
struct date {
    int c_date, c_month, c_year;   // current date
    int b_date, b_month, b_year;   // birth date
    int cal_date, cal_month, cal_year; // calculated age
};

// Step 5: Function to calculate age
void findAge(struct date *d) {
    int month[] = {31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31};

    // Step 6b: Adjust days if birth date > current date
    if (d->b_date > d->c_date) {
        d->c_date += month[d->c_month - 2]; // add days of previous month
        d->c_month -= 1;
    }

    // Step 6c: Adjust months if birth month > current month
    if (d->b_month > d->c_month) {
        d->c_year -= 1;
        d->c_month += 12;
    }

    // Step 6d: Calculate age
    d->cal_date = d->c_date - d->b_date;
    d->cal_month = d->c_month - d->b_month;
    d->cal_year = d->c_year - d->b_year;
}

int main() {
    struct date d;

    // Step 4: Input current date and birth date
    printf("Enter current date (DD MM YYYY): ");
    scanf("%d %d %d", &d.c_date, &d.c_month, &d.c_year);

    printf("Enter birth date (DD MM YYYY): ");
    scanf("%d %d %d", &d.b_date, &d.b_month, &d.b_year);

    // Step 5: Call function by reference
    findAge(&d);

    // Step 8: Display calculated age
    printf("\nPresent Age: %d years %d months %d days\n", d.cal_year, d.cal_month, d.cal_date);

    return 0;
}
```
# Output:

<img width="380" height="157" alt="image" src="https://github.com/user-attachments/assets/abfb0a0c-9782-4841-bfce-1b43d47b1a56" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M6
# IAPR-6- Module 6 - FoC
# Ex.No:30
  Build a C program to demonstrate the use of a pointer to a union. Store an integer value in a union, access it using a union pointer, and display it as both an integer and a character.
# Date : 
# Aim:
  To build a program in C that uses a pointer to a union to store an integer value and display it in both integer and character format.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3:
  Define a union `abc` with the following members:  
  - `int a`  
  - `char b`
### Step 4:
  Declare a union variable `var` of type `abc`.
### Step 5:
  Declare a pointer `ptr` of type `union abc*`.
### Step 6:
  Assign the address of `var` to `ptr`.
### Step 7:
  Store an integer value (e.g., 90) in `var.a`.
### Step 8:
  Access and print the value of `a` using the pointer `ptr` in integer format.
### Step 9:
  Access and print the same value using the pointer `ptr` in character format.
### Step 10:
  Stop
# Program:
```
#include <stdio.h>

// Step 3: Define union
union abc {
    int a;
    char b;
};

int main() {
    union abc var;          // Step 4: Declare union variable
    union abc *ptr;         // Step 5: Declare pointer to union

    ptr = &var;             // Step 6: Assign address of var to ptr

    var.a = 90;             // Step 7: Store integer value in union

    // Step 8: Access integer value using pointer
    printf("Integer format: %d\n", ptr->a);

    // Step 9: Access same value in character format
    printf("Character format: %c\n", ptr->b);

    return 0;
}
```
# Output:

<img width="313" height="177" alt="image" src="https://github.com/user-attachments/assets/a8e7500e-0508-4ff9-b6da-22f2d12315c0" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.
