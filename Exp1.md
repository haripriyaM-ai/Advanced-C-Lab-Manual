# EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

## Aim:
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

## Algorithm:
1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4.	If e.age <= 6
-	Print "Vaccine Eligibility: No"
Else
-	Print "Vaccine Eligibility: Yes"
5.	Print details (e.age, e.n)
6.	Return 0
 
## Program:

```
#include <stdio.h>
#include <string.h>

struct eligible {
    int age;
    char n[100];
};

int main() {
    int i, num;
    struct eligible e[100];
    printf("Enter the number of persons: ");
    scanf("%d", &num);
    for(i = 0; i < num; i++) {
        printf("\nEnter name of person %d: ", i + 1);
        scanf("%s", e[i].n);
        printf("Enter age of person %d: ", i + 1);
        scanf("%d", &e[i].age);
    }

    printf("\nVaccine Eligibility Report\n");
    for(i = 0; i < num; i++) {
        printf("\nName: %s\n", e[i].n);
        printf("Age: %d\n", e[i].age);
        if(e[i].age > 6) {
            printf("Vaccine Eligibility: Yes\n");
        } else {
            printf("Vaccine Eligibility: No\n");
        }
    }

    return 0;
}
```


## Output:

![Screenshot 2025-05-19 181043](https://github.com/user-attachments/assets/0b807afe-4d14-4ea0-86de-78b16dcf7c21)

## Result:

Thus, the program is verified successfully.
