# Ex-1 IMPLEMENTATION-OF-SYMBOL-TABLE
# Register Number : 212224230064
# Date : 24-04-2026

# AIM :
## To write a C program to implement a symbol table.

# ALGORITHM
1.	Start the program.
2.	Get the input from the user with the terminating symbol ‘$’.
3.	Allocate memory for the variable by dynamic memory allocation function.
4.	If the next character of the symbol is an operator then only the memory is allocated.
5.	While reading, the input symbol and memory address are inserted into the symbol table.
6.	The steps are repeated till ‘$’ is reached.
7.	To reach a variable, enter the variable to be searched and the symbol table has been checked for the corresponding variable, the variable along with its address is displayed as a result.
8.	Stop the program.

# PROGRAM
```.c
#include <stdio.h>
#include <ctype.h>
#define MAX_EXPRESSION_SIZE 100

int main() {
    int i = 0, j = 0, x = 0, n, flag = 0;
    char b[MAX_EXPRESSION_SIZE], d[15], c, srch;

    printf("Enter the Expression terminated by $: ");
    while ((c = getchar()) != '$' && i < MAX_EXPRESSION_SIZE - 1) {
        b[i++] = c;
    }
    b[i] = '\0'; 
    n = i - 1;

    printf("\nGiven Expression: %s\n", b);

    printf("\nSymbol Table\n");
    printf("Symbol\tType\n");

    for (j = 0; j <= n; j++) {
        c = b[j];
        if (isalpha((unsigned char)c)) {
            int alreadyExists = 0;
            for (int k = 0; k < x; k++) {
                if (d[k] == c) {
                    alreadyExists = 1;
                    break;
                }
            }

            if (!alreadyExists) {
                d[x] = c;
                printf("%c\tidentifier\n", c);
                x++;
            }
        }
    }
    while ((c = getchar()) != '\n' && c != EOF);

    printf("\nEnter the symbol to search: ");
    srch = getchar();

    for (i = 0; i < x; i++) {
        if (srch == d[i]) {
            printf("Symbol Found\n");
            flag = 1;
            printf("Address : %p", (void*)&d[i]);
            break;
        }
    }
    if (flag == 0)
        printf("Symbol Not Found\n");

    return 0;
}
```

# OUTPUT

## Symbol Found
<img width="1522" height="868" alt="Screenshot 2026-04-24 090752" src="https://github.com/user-attachments/assets/632d797a-3d0f-44fe-845a-e56643ced8ed" />

## Symbol Not Found
<img width="1524" height="861" alt="image" src="https://github.com/user-attachments/assets/e95c6019-7512-4d53-9305-9d52a3d43b48" />

# RESULT
### The program to implement a symbol table is executed and the output is verified.
