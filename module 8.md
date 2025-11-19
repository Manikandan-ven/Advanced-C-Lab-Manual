
EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER Aim: To write a C program print the lowercase English word corresponding to the number Algorithm:

Start
Initialize an integer variable n.
Input Validation
Switch Statement cases.
Case 5: Print "seventy one"
Case 6: Print "seventy two"
Case 13: Print "seventy three"
...
Case 13: Print "seventy nine"
Default: Print "Greater than 13"
Exit the program.
Program:

```

#include <stdio.h>

int main() {
    int n;

    // Step 1 & 2: Input number
    printf("Enter a number: ");
    scanf("%d", &n);

    // Step 3: Switch statement to print corresponding word
    switch(n) {
        case 5:
            printf("seventy one\n");
            break;
        case 6:
            printf("seventy two\n");
            break;
        case 7:
            printf("seventy three\n");
            break;
        case 8:
            printf("seventy four\n");
            break;
        case 9:
            printf("seventy five\n");
            break;
        case 10:
            printf("seventy six\n");
            break;
        case 11:
            printf("seventy seven\n");
            break;
        case 12:
            printf("seventy eight\n");
            break;
        case 13:
            printf("seventy nine\n");
            break;
        default:
            printf("Greater than 13\n");
    }

    return 0; // Step 4: Exit program
}
```

Output:

<img width="477" height="191" alt="image" src="https://github.com/user-attachments/assets/cc77e02d-a095-4343-8072-74579d2dfb96" />


Result: Thus, the program is verified successfully


EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
Program:
```
#include <stdio.h>
#include <string.h>

int main() {
    char a[50];
    int count[4] = {0, 0, 0, 0}; // To store frequency of digits 0 to 3
    int i;

    // Step 2: Input a string of digits
    printf("Enter a string of digits (0-3): ");
    scanf("%s", a);

    int len = strlen(a);

    // Step 3 & 4: Count frequency of each digit
    for(i = 0; i < len; i++) {
        if(a[i] >= '0' && a[i] <= '3') {
            count[a[i] - '0']++;
        }
    }

    // Step 4 & 5: Print frequency of digits 0 to 3
    printf("Frequency of digits 0 to 3:\n");
    for(i = 0; i < 4; i++) {
        printf("%d ", count[i]);
    }
    printf("\n");

    return 0; // Step 6: End
}

```


Output:




<img width="640" height="296" alt="image" src="https://github.com/user-attachments/assets/2211aec9-912d-4c74-a88e-d33a77e8077f" />





Result:
Thus, the program is verified successfully

EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
Aim:
To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)

3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
Program:
```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// Function to swap two characters
void swap(char *x, char *y) {
    char temp = *x;
    *x = *y;
    *y = temp;
}

// Function to sort a string in lexicographical order
void sortString(char *str) {
    int n = strlen(str);
    for(int i = 0; i < n-1; i++) {
        for(int j = i+1; j < n; j++) {
            if(str[i] > str[j])
                swap(&str[i], &str[j]);
        }
    }
}

// Function to generate all permutations using recursion
void permute(char *str, int l, int r) {
    if(l == r) {
        printf("%s\n", str);
    } else {
        for(int i = l; i <= r; i++) {
            swap(&str[l], &str[i]);
            permute(str, l+1, r);
            swap(&str[l], &str[i]); // backtrack
        }
    }
}

int main() {
    char *s;
    int n;

    // Step 4: Input string
    printf("Enter a string: ");
    char buffer[100];
    scanf("%s", buffer);

    n = strlen(buffer);

    // Step 3: Dynamically allocate memory for string
    s = (char *)malloc((n + 1) * sizeof(char));
    if(s == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }
    strcpy(s, buffer);

    // Step 5: Sort string to start permutations in lexicographical order
    sortString(s);
    printf("All permutations in lexicographical order:\n");
    permute(s, 0, n - 1);

    // Step 6: Free allocated memory
    free(s);

    return 0;
}

```



Output:


<img width="661" height="367" alt="image" src="https://github.com/user-attachments/assets/b5836dcc-53b2-4b52-bb9f-820eb516cbd5" />







Result:
Thus, the program is verified successfully
 
EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.
Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
Program:

```
#include <stdio.h>

int main() {
    int n, i, j, len, min;

    // Step 3: Read the value of n
    printf("Enter a number N: ");
    scanf("%d", &n);

    // Step 4: Calculate the side length of the square
    len = 2 * n - 1;

    // Step 5: Generate the matrix pattern
    for(i = 0; i < len; i++) {
        for(j = 0; j < len; j++) {
            // Step 6: Calculate the minimum distance to borders
            min = i < j ? i : j;
            if(len - 1 - i < min) min = len - 1 - i;
            if(len - 1 - j < min) min = len - 1 - j;

            // Print the corresponding number
            printf("%d ", n - min);
        }
        printf("\n");
    }

    return 0;
}

```

Output:

<img width="497" height="363" alt="image" src="https://github.com/user-attachments/assets/3ab3cd04-2878-4b0f-8748-ca650d93ac5c" />







Result:
Thus, the program is verified successfully

EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

Algorithm:

1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

Program:


#include <stdio.h>

// Step 2: Function definition
int square() {
    int num, result;

    // Step 3: Input number
    printf("Enter a number: ");
    scanf("%d", &num);

    // Calculate square
    result = num * num;

    // Return squared value
    return result;
}

int main() {
    int sq;

    // Step 4: Call function and display result
    sq = square();
    printf("Square of the number is: %d\n", sq);

    return 0; // Step 5: End
}




Output:


<img width="523" height="206" alt="image" src="https://github.com/user-attachments/assets/1fdd9ed4-58f2-45ce-a801-de3ac2dce854" />






Result:
Thus, the program is verified successfully



























