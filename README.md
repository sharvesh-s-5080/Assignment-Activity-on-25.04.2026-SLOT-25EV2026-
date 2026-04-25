# Assignment-Activity-on-25.04.2026-SLOT-25EV2026
1. Write a C program to traverse a 2D matrix and print the values until a negative number is found. Use break statement.
   program:
 ```
          #include <stdio.h>

          int main() {
              int matrix[3][3] = {
                  {1, 2, 3},
                  {4, -5, 6},
                  {7, 8, 9}
              };
          
              for (int i = 0; i < 3; i++) {
                  for (int j = 0; j < 3; j++) {
                      if (matrix[i][j] < 0) {
                          return 0; // Simplest way to stop the entire program
                      }
                      printf("%d ", matrix[i][j]);
                  }
                  printf("\n");
              }
          
              return 0;
          }
   ```
2. Write a C program to print the numbers from 1 to 100 but avoid printing multiples of 3 and number containing digit 5(5,15,25,35,..). Use continue in the program.
```
#include <stdio.h>

int main() {
    for (int i = 1; i <= 100; i++) {
        // Skip multiples of 3
        if (i % 3 == 0) {
            continue;
        }

        // Skip numbers containing the digit 5
        if (i % 10 == 5 || i / 10 == 5) {
            continue;
        }

        printf("%d ", i);
    }

    return 0;
}
```
3. Write a C program that performs division of two user inputs and uses goto  to handle errors like division by zero or invalid input by redirecting control for re-entry.
```
#include <stdio.h>

int main() {
    float num1, num2, result;

input_start: // Label for goto redirection
    printf("\nEnter two numbers for division (e.g., 10 2): ");

    // Check if input is valid (numeric)
    if (scanf("%f %f", &num1, &num2) != 2) {
        printf("Error: Invalid input. Please enter numbers only.\n");
        while (getchar() != '\n'); // Clear input buffer
        goto input_start;
    }

    // Check for division by zero
    if (num2 == 0) {
        printf("Error: Division by zero is not allowed.\n");
        goto input_start;
    }

    result = num1 / num2;
    printf("Result: %.2f / %.2f = %.2f\n", num1, num2, result);

    return 0;
}
```

4. Write a C program for a number guessing game where the loop continues for wrong guesses, breaks on a correct guess, and exits the program using return if the user enters -1.
```
#include <stdio.h>

int main() {
    int target = 42;
    int guess;

    while (1) {
        printf("Guess (or -1 to quit): ");
        scanf("%d", &guess);

        if (guess == -1) {
            return 0; // Exit program
        }

        if (guess == target) {
            printf("Correct!\n");
            break; // Exit loop
        }

        printf("Wrong guess, try again.\n");
    }

    return 0;
}
```
5. Write a C program that iterates through an array and, within a loop, uses continue  to skip negative elements, break when a zero is encountered, and return to exit the program if an element greater than 100 is found, then print the resulting behavior for the array {10, -5, 20, 0, 150, 30}.
```
#include <stdio.h>

int main() {
    int arr[] = {10, -5, 20, 0, 150, 30};
    int n = 6;

    for (int i = 0; i < n; i++) {
        // Exit program if element > 100
        if (arr[i] > 100) {
            printf("\nFound %d: Exiting program via return.\n", arr[i]);
            return 0; 
        }

        // Break loop if element is 0
        if (arr[i] == 0) {
            printf("\nFound 0: Breaking loop.\n");
            break;
        }

        // Skip negative elements
        if (arr[i] < 0) {
            continue;
        }

        // Print valid elements
        printf("%d ", arr[i]);
    }

    printf("Loop finished.\n");
    return 0;
}
```
