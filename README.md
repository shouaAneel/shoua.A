#include <stdio.h>
#include <math.h>

// Complex number structure
typedef struct {
    double real;
    double imaginary;
} ComplexNumber;

// Function declarations
void modulusOperation();
void complexNumberOperations();
void algebraicOperations();
void exponentialAndLogarithmicOperations();
void trigonometricOperations();
void arithmeticOperations();

int main() {
    int choice;

    do {
        // Display menu
        printf("\nScientific Calculator Menu:\n");
        printf("1. Modulus Operation\n");
        printf("2. Complex Number Operations\n");
        printf("3. Algebraic Operations\n");
        printf("4. Exponential and Logarithmic Operations\n");
        printf("5. Trigonometric Operations\n");
        printf("6. Arithmetic Operations\n");
        printf("0. Exit\n");

        // User choice
        printf("Enter your choice: ");
        scanf("%d", &choice);

        // Perform operations based on user choice
        switch (choice) {
            case 1:
                modulusOperation();
                break;
            case 2:
                complexNumberOperations();
                break;
            case 3:
                algebraicOperations();
                break;
            case 4:
                exponentialAndLogarithmicOperations();
                break;
            case 5:
                trigonometricOperations();
                break;
            case 6:
                arithmeticOperations();
                break;
            case 0:
                printf("Exiting the calculator. Goodbye!\n");
                break;
            default:
                printf("Invalid choice. Please enter a valid option.\n");
        }
    } while (choice != 0);

    return 0;
}

// Function definitions

void modulusOperation() {
    double num;
    printf("Enter a number: ");
    scanf("%lf", &num);

    double modulus = fabs(num);
    printf("Modulus: %.2lf\n", modulus);
}

void complexNumberOperations() {
    ComplexNumber num1, num2, result;
    int op;

    printf("Enter the real and imaginary parts of the first complex number: ");
    scanf("%lf %lf", &num1.real, &num1.imaginary);

    printf("Enter the real and imaginary parts of the second complex number: ");
    scanf("%lf %lf", &num2.real, &num2.imaginary);

    printf("Complex Number Operations:\n");
    printf("1. Addition\n");
    printf("2. Subtraction\n");
    printf("Enter the operation: ");
    scanf("%d", &op);

    switch (op) {
        case 1:
            result.real = num1.real + num2.real;
            result.imaginary = num1.imaginary + num2.imaginary;
            printf("Result: %.2lf + %.2lfi\n", result.real, result.imaginary);
            break;
        case 2:
            result.real = num1.real - num2.real;
            result.imaginary = num1.imaginary - num2.imaginary;
            printf("Result: %.2lf + %.2lfi\n", result.real, result.imaginary);
            break;
        default:
            printf("Invalid operation.\n");
    }
}

void algebraicOperations() {
    // Placeholder for algebraic operations
    printf("Algebraic Operations: Not implemented in this example.\n");
}

void exponentialAndLogarithmicOperations() {
    double num, result;
    int op;

    printf("Enter a number: ");
    scanf("%lf", &num);

    printf("Exponential and Logarithmic Operations:\n");
    printf("1. Exponential (e^x)\n");
    printf("2. Natural Logarithm (log_e)\n");
    printf("Enter the operation: ");
    scanf("%d", &op);

    switch (op) {
        case 1:
            result = exp(num);
            printf("Result: %.4lf\n", result);
            break;
        case 2:
            if (num > 0) {
                result = log(num);
                printf("Result: %.4lf\n", result);
            } else {
                printf("Error! Logarithm of a non-positive number is undefined.\n");
            }
            break;
        default:
            printf("Invalid operation.\n");
    }
}

void trigonometricOperations() {
    double angle, result;
    int op;

    printf("Enter an angle in degrees: ");
    scanf("%lf", &angle);

    printf("Trigonometric Operations:\n");
    printf("1. Sine\n");
    printf("2. Cosine\n");
    printf("3. Tangent\n");
    printf("Enter the operation: ");
    scanf("%d", &op);

    switch (op) {
        case 1:
            result = sin(angle * M_PI / 180.0);
            printf("Result: %.4lf\n", result);
            break;
        case 2:
            result = cos(angle * M_PI / 180.0);
            printf("Result: %.4lf\n", result);
            break;
        case 3:
            result = tan(angle * M_PI / 180.0);
            printf("Result: %.4lf\n", result);
            break;
        default:
            printf("Invalid operation.\n");
    }
}

void arithmeticOperations() {
    double num1, num2, result;
    int op;

    printf("Enter two numbers: ");
    scanf("%lf %lf", &num1, &num2);

    printf("Arithmetic Operations:\n");
    printf("1. Addition\n");
    printf("2. Subtraction\n");
    printf("3. Multiplication\n");
    printf("4. Division\n");
    printf("Enter the operation: ");
    scanf("%d", &op);

    switch (op) {
        case 1:
            result = num1 + num2;
            printf("Result: %.2lf\n", result);
            break;
        case 2:
            result = num1 - num2;
            printf("Result: %.2lf\n", result);
            break;
        case 3:
            result = num1 * num2;
            printf("Result: %.2lf\n", result);
            break;
        case 4:
            if (num2 != 0) {
                result = num1 / num2;
                printf("Result: %.2lf\n", result);
            } else {
                printf("Error! Division by zero is not allowed.\n");
            }
            break;
        default:
            printf("Invalid operation.\n");
    }
}
