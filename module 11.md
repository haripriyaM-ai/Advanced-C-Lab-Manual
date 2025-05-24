# EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
## Aim:
To write a C program to create a function to find the greatest number

## Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
## Program:
```
#include <stdio.h>

int max_of_four(int n1, int n2, int n3, int n4) {
    if (n1 >= n2 && n1 >= n3 && n1 >= n4)
        return n1;
    else if (n2 >= n1 && n2 >= n3 && n2 >= n4)
        return n2;
    else if (n3 >= n1 && n3 >= n2 && n3 >= n4)
        return n3;
    else
        return n4;
}

int main() {
    int n1, n2, n3, n4, greater;
    printf("Enter four integers: ");
    scanf("%d %d %d %d", &n1, &n2, &n3, &n4);
    greater = max_of_four(n1, n2, n3, n4);
    printf("The greatest number is: %d\n", greater);
    return 0;
}
```
## Output:
![Screenshot 2025-05-20 125658](https://github.com/user-attachments/assets/a1699ee0-314f-4f2c-8af5-ee4c3c79b172)

## Result:
Thus, the program  that create a function to find the greatest number is verified successfully.


 
# EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS
## Aim:
To write a C program to print the maximum values for the AND, OR and XOR comparisons

## Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
## Program:
```
#include <stdio.h>

void calculate_the_max(int n, int k) {
    int a = 0, o = 0, x = 0; 

    for (int i = 1; i < n; i++) {
        for (int j = i + 1; j <= n; j++) {
            int and_val = i & j;
            int or_val = i | j;
            int xor_val = i ^ j;

            if (and_val < k && and_val > a)
                a = and_val;
            if (or_val < k && or_val > o)
                o = or_val;
            if (xor_val < k && xor_val > x)
                x = xor_val;
        }
    }

    printf("Maximum AND value: %d\n", a);
    printf("Maximum OR value: %d\n", o);
    printf("Maximum XOR value: %d\n", x);
}

int main() {
    int n, k;

    printf("Enter values for n and k: ");
    scanf("%d %d", &n, &k);

    calculate_the_max(n, k);

    return 0;
}
```
## Output:
![Screenshot 2025-05-20 125831](https://github.com/user-attachments/assets/64215f01-2d8f-4847-9b15-2c6be8ec9a9c)

## Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.


 
# EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
## Aim:
To write a C program to write the logic for the requests

## Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
## Program:
```
#include <stdio.h>
#include <stdlib.h>

int main() {
    int noshel, noque;
    scanf("%d %d", &noshel, &noque);

    int **shelarr = malloc(noshel * sizeof(int *));
    int *nobookarr = calloc(noshel, sizeof(int));  

    for (int i = 0; i < noshel; i++) {
        shelarr[i] = NULL;
    }

    for (int q = 0; q < noque; q++) {
        int type;
        scanf("%d", &type);

        if (type == 1) {
            // Add book
            int x, y;
            scanf("%d %d", &x, &y); // x = shelf number, y = pages in book

            nobookarr[x]++;
            shelarr[x] = realloc(shelarr[x], nobookarr[x] * sizeof(int));
            shelarr[x][nobookarr[x] - 1] = y;

        } else if (type == 2) {
            // Query book
            int x, y;
            scanf("%d %d", &x, &y); // x = shelf number, y = book index
            printf("Answer: %d\n", shelarr[x][y]);

        } else if (type == 3) {
            // Query number of books on shelf x
            int x;
            scanf("%d", &x);
            printf("Answer: %d\n", nobookarr[x]);
        }
    }

    for (int i = 0; i < noshel; i++) {
        free(shelarr[i]);
    }
    free(shelarr);
    free(nobookarr);

    return 0;
}

```
## Output:
![Screenshot 2025-05-20 130248](https://github.com/user-attachments/assets/9b96ef38-2651-4e63-b6e8-5ade042c0735)


## Result:
Thus, the program to write the logic for the requests is verified successfully.


 
# EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
## Aim:
To write a C program print the sum of the integers in the array.

## Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.



## Program:
```
#include <stdio.h>

int main() {
    int n, sum = 0;
    scanf("%d", &n);

    int a[n];
    for (int i = 0; i < n; i++) {
        scanf("%d", &a[i]);
        sum += a[i];
    }

    printf("Sum: %d\n", sum);
    return 0;
}
```
## Output:
![Screenshot 2025-05-20 130510](https://github.com/user-attachments/assets/62e9375d-5910-4c89-aabd-34e161c5bebd)

 


## Result:
Thus, the program prints the sum of the integers in the array is verified successfully.


 
# EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A SENTENCE



## Aim:

To write a C program that counts the number of words in a given sentence.

## Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.



## Program:
```
#include <stdio.h>
#include <ctype.h>

int main() {
    char sentence[1000];
    int count = 0;
    int in_word = 0;

    fgets(sentence, sizeof(sentence), stdin);

    for (int i = 0; sentence[i] != '\0'; i++) {
        if (!isspace(sentence[i])) {
            if (in_word == 0) {
                count++;
                in_word = 1;
            }
        } else {
            in_word = 0;
        }
    }

    printf("Number of words: %d\n", count);
    return 0;
}
```
## Output:
![Screenshot 2025-05-20 130653](https://github.com/user-attachments/assets/85f208a4-fa0f-4eab-95bd-15722c790bf1)



## Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.




