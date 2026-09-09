EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
Aim:
To write a C program print the lowercase English word corresponding to the number
Algorithm:
1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
Program:
```
#include <stdio.h>

int main() {
    int n;

    scanf("%d", &n);

    switch (n) {
        case 1: printf("one"); break;
        case 2: printf("two"); break;
        case 3: printf("three"); break;
        case 4: printf("four"); break;
        case 5: printf("five"); break;
        case 6: printf("six"); break;
        case 7: printf("seven"); break;
        case 8: printf("eight"); break;
        case 9: printf("nine"); break;
        default: printf("Greater than 9");
    }

    return 0;
}
```

Output:


<img width="674" height="100" alt="image" src="https://github.com/user-attachments/assets/be05ebec-dc46-443d-aa45-4e35d0dcfdd1" />







Result:
Thus, the program is verified successfully
 
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

int main() {
    char a[50];
    int i, j, c;

    scanf("%s", a);

    for (i = 0; i <= 9; i++) {
        c = 0;

        for (j = 0; a[j] != '\0'; j++) {
            if (a[j] == i + '0')
                c++;
        }

        printf("%d ", c);
    }

    return 0;
}
```




Output:


<img width="637" height="93" alt="image" src="https://github.com/user-attachments/assets/db575d18-9373-4e83-aa60-83a7a1e2b963" />







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

void swap(char **a, char **b) {
    char *temp = *a;
    *a = *b;
    *b = temp;
}

int compare(const void *a, const void *b) {
    return strcmp(*(char **)a, *(char **)b);
}

void permute(char **s, int l, int n) {
    int i;

    if (l == n) {
        for (i = 0; i < n; i++)
            printf("%s ", s[i]);
        printf("\n");
        return;
    }

    for (i = l; i < n; i++) {
        swap(&s[l], &s[i]);
        permute(s, l + 1, n);
        swap(&s[l], &s[i]);
    }
}

int main() {
    char **s;
    int n, i;

    scanf("%d", &n);

    s = (char **)malloc(n * sizeof(char *));

    for (i = 0; i < n; i++) {
        s[i] = (char *)malloc(50 * sizeof(char));
        scanf("%s", s[i]);
    }

    qsort(s, n, sizeof(char *), compare);

    permute(s, 0, n);

    for (i = 0; i < n; i++)
        free(s[i]);

    free(s);

    return 0;
}
```



Output:


<img width="660" height="268" alt="image" src="https://github.com/user-attachments/assets/f1144514-7fa6-4e1e-8e6f-3c5c59408fde" />








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
    int n, i, j, min, len;

    scanf("%d", &n);

    len = n * 2 - 1;

    for (i = 0; i < len; i++) {
        for (j = 0; j < len; j++) {
            min = i < j ? i : j;

            if (len - 1 - i < min)
                min = len - 1 - i;

            if (len - 1 - j < min)
                min = len - 1 - j;

            printf("%d ", n - min);
        }
        printf("\n");
    }

    return 0;
}
```



Output:



<img width="715" height="215" alt="image" src="https://github.com/user-attachments/assets/2d307497-7568-4fd4-9b29-39519e5b2503" />







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
```
#include <stdio.h>

int square() {
    int n;

    scanf("%d", &n);

    return n * n;
}

int main() {
    int result;

    result = square();

    printf("%d", result);

    return 0;
}
```


Output:


<img width="599" height="96" alt="image" src="https://github.com/user-attachments/assets/2b67f9a6-200a-481d-a0db-e5489f8f3745" />






Result:
Thus, the program is verified successfully



























