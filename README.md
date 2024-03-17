// Online C compiler to run C program o#include <stdio.h>
#include<stdio.h>
int main() {
    char operator;
    double num1, num2, result;
    int keepCalculating = 1; // Flag to control whether to continue calculating

    while (keepCalculating) {
        // Prompt user for operator
        printf("Enter operator (+, -, *, /) or 'q' to quit: ");
        scanf(" %c", &operator);

        // Check if user wants to quit
        if (operator == 'q') {
            printf("Exiting calculator.\n");
            break; // Exit the loop
        }

        // Prompt user for two numbers
        printf("Enter two numbers: ");
        scanf("%lf %lf", &num1, &num2);

        // Perform the calculation based on the operator
        switch(operator) {
            case '+':
                result = num1 + num2;
                break;
            case '-':
                result = num1 - num2;
                break;
            case '*':
                result = num1 * num2;
                break;
            case '/':
                if (num2 != 0)
                    result = num1 / num2;
                else {
                    printf("Error! Division by zero.\n");
                    continue; // Skip this iteration and continue with the next iteration of the loop
                }
                break;
            default:
                printf("Error! Invalid operator.\n");
                continue; // Skip this iteration and continue with the next iteration of the loop
        }

        // Display the result
        printf("Result: %lf\n", result);
    }

    return 0;
}
