# Prog_120_W24_L8_Array_ForLoop

## For Loops

Sure, here's a breakdown of `for` loops in C# with code snippet examples:

1. **Basic `for` loop**: The basic `for` loop consists of three parts: initialization, condition, and iterator.

```csharp
for (int i = 0; i < 5; i++)
{
    Console.WriteLine(i);
}
```

- **Initialization (`int i = 0`)**: This part is executed only once at the beginning of the loop. It initializes the loop control variable (`i` in this case).
- **Condition (`i < 5`)**: This part is evaluated before each iteration of the loop. If the condition is `true`, the loop body is executed. If it's `false`, the loop terminates.
- **Iterator (`i++`)**: This part is executed after each iteration of the loop. It updates the loop control variable. In this case, it increments `i` by 1.

2. **Using a `for` loop to iterate over an array**:

```csharp
int[] numbers = { 1, 2, 3, 4, 5 };

for (int i = 0; i < numbers.Length; i++)
{
    Console.WriteLine(numbers[i]);
}
```

In this example, the loop iterates over each element of the `numbers` array and prints its value.

3. **Nested `for` loops**:

```csharp
for (int i = 0; i < 3; i++)
{
    for (int j = 0; j < 3; j++)
    {
        Console.WriteLine($"({i}, {j})");
    }
}
```

Nested loops are `for` loops inside another `for` loop. In this example, there are two nested loops, and each iteration of the outer loop triggers all iterations of the inner loop.

4. **Using `break` and `continue` statements**:

```csharp
for (int i = 0; i < 5; i++)
{
    if (i == 2)
        continue; // Skip the rest of the loop body for i = 2

    Console.WriteLine(i);

    if (i == 3)
        break; // Terminate the loop when i = 3
}
```

- **`continue` statement**: When encountered, it skips the rest of the loop body for the current iteration and moves to the next iteration.
- **`break` statement**: When encountered, it immediately terminates the loop.

5. **Using `for` loop with multiple loop variables**:

```csharp
for (int i = 0, j = 10; i < 5 && j > 5; i++, j--)
{
    Console.WriteLine($"i: {i}, j: {j}");
}
```

In this example, the loop has two loop control variables, `i` and `j`. Both are initialized, checked against conditions, and incremented/decremented in the same loop header.

These are some basic examples demonstrating the usage of `for` loops in C#. They provide a powerful mechanism for iterating over collections and executing repetitive tasks.

### Real - World Practice

1. **Processing Items in a Collection**:
   In many applications, you might need to process each item in a collection. For example, you might need to calculate the total price of items in a shopping cart.

```csharp
List<double> prices = new List<double> { 10.99, 5.99, 8.50, 19.99 };
double totalPrice = 0;

for (int i = 0; i < prices.Count; i++)
{
    totalPrice += prices[i];
}

Console.WriteLine($"Total Price: ${totalPrice}");
```

2. **Generating Reports or Summaries**:
   You might need to generate reports or summaries based on data stored in arrays or lists.

```csharp
string[] daysOfWeek = { "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday" };

for (int i = 0; i < daysOfWeek.Length; i++)
{
    Console.WriteLine($"Day {i + 1}: {daysOfWeek[i]}");
}
```

3. **Data Validation**:
   When validating user input, you might need to check each character in a string or each element in an array.

```csharp
string userInput = "12345";
bool isValid = true;

for (int i = 0; i < userInput.Length; i++)
{
    if (!char.IsDigit(userInput[i]))
    {
        isValid = false;
        break; // Exit loop early if non-digit character found
    }
}

Console.WriteLine($"Is user input valid? {isValid}");
```

4. **File Processing**:
   When processing files, such as reading lines from a text file, you might use a `for` loop to iterate over each line.

```csharp
string[] lines = File.ReadAllLines("data.txt");

for (int i = 0; i < lines.Length; i++)
{
    Console.WriteLine($"Line {i + 1}: {lines[i]}");
}
```

5. **Matrix Operations**:
   In scientific or mathematical applications, `for` loops are commonly used for matrix operations.

```csharp
int[,] matrix = { { 1, 2, 3 }, { 4, 5, 6 }, { 7, 8, 9 } };
int sum = 0;

for (int row = 0; row < matrix.GetLength(0); row++)
{
    for (int col = 0; col < matrix.GetLength(1); col++)
    {
        sum += matrix[row, col];
    }
}

Console.WriteLine($"Sum of all elements in the matrix: {sum}");
```

These are just a few examples of real-world scenarios where `for` loops are commonly used in C#. They demonstrate the versatility and usefulness of `for` loops in various programming tasks.

---

## Arrays

C# arrays are used to store a fixed-size sequential collection of elements of the same type. The elements in an array are accessed using an integer index. Arrays in C# can be of any data type, including primitive types like integers and characters, or reference types like objects. They provide a convenient way to work with collections of data, allowing for efficient storage and retrieval.

Here's a basic overview of creating and using arrays in C#, along with some code snippet examples:

1. **Declaring an Array**: To declare an array in C#, you specify the data type of the elements followed by square brackets `[]` and the array name.

```csharp
// Declare an integer array with 5 elements
int[] numbers;
```

2. **Initializing an Array**: You can initialize an array when declaring it or later using the `new` keyword followed by the array's data type and the number of elements in square brackets.

```csharp
// Declare and initialize an array of integers with 3 elements
int[] numbers = new int[3];
```

3. **Initializing with Values**: You can also initialize an array with specific values.

```csharp
// Initialize an array of integers with specific values
int[] numbers = new int[] { 1, 2, 3, 4, 5 };
```

4. **Accessing Array Elements**: Array elements are accessed using an integer index, starting from 0.

```csharp
// Accessing array elements
int firstElement = numbers[0]; // Accessing the first element
int thirdElement = numbers[2]; // Accessing the third element
```

5. **Array Length**: You can get the length of an array using the `Length` property.

```csharp
// Getting the length of an array
int length = numbers.Length;
```

6. **Iterating Through an Array**: You can use loops like `for` or `foreach` to iterate through array elements.

```csharp
// Iterating through an array using a for loop
for (int i = 0; i < numbers.Length; i++)
{
    Console.WriteLine(numbers[i]);
}

// Iterating through an array using foreach loop
foreach (int num in numbers)
{
    Console.WriteLine(num);
}
```

7. **Multidimensional Arrays**: C# also supports multidimensional arrays.

```csharp
// Declaring and initializing a 2D array
int[,] matrix = new int[2, 3] { { 1, 2, 3 }, { 4, 5, 6 } };

// Accessing elements of a 2D array
int element = matrix[1, 2]; // Accessing the element at row 1, column 2
```

Arrays in C# provide a powerful and flexible way to work with collections of data, making them a fundamental part of the language.

### Real-World Practice


1. **Employee Management System**:
   In an employee management system, you might use arrays to store employee information such as names, IDs, and salaries. Here's a simplified example:

```csharp
class Program
{
    static void Main(string[] args)
    {
        string[] employeeNames = new string[5];
        int[] employeeIDs = new int[5];
        double[] employeeSalaries = new double[5];

        // Populate arrays with employee information
        for (int i = 0; i < employeeNames.Length; i++)
        {
            Console.WriteLine($"Enter name of employee {i + 1}: ");
            employeeNames[i] = Console.ReadLine();

            Console.WriteLine($"Enter ID of employee {i + 1}: ");
            employeeIDs[i] = int.Parse(Console.ReadLine());

            Console.WriteLine($"Enter salary of employee {i + 1}: ");
            employeeSalaries[i] = double.Parse(Console.ReadLine());
        }

        // Display employee information
        Console.WriteLine("\nEmployee Information:");
        for (int i = 0; i < employeeNames.Length; i++)
        {
            Console.WriteLine($"Name: {employeeNames[i]}, ID: {employeeIDs[i]}, Salary: {employeeSalaries[i]}");
        }
    }
}
```

2. **Inventory Management**:
   In an inventory management system, arrays can be used to store product information such as names, quantities, and prices.

```csharp
class Program
{
    static void Main(string[] args)
    {
        string[] productNames = new string[5];
        int[] quantities = new int[5];
        double[] prices = new double[5];

        // Populate arrays with product information
        for (int i = 0; i < productNames.Length; i++)
        {
            Console.WriteLine($"Enter name of product {i + 1}: ");
            productNames[i] = Console.ReadLine();

            Console.WriteLine($"Enter quantity of product {i + 1}: ");
            quantities[i] = int.Parse(Console.ReadLine());

            Console.WriteLine($"Enter price of product {i + 1}: ");
            prices[i] = double.Parse(Console.ReadLine());
        }

        // Display product information
        Console.WriteLine("\nProduct Information:");
        for (int i = 0; i < productNames.Length; i++)
        {
            Console.WriteLine($"Product: {productNames[i]}, Quantity: {quantities[i]}, Price: {prices[i]}");
        }
    }
}
```

3. **Data Analysis**:
   Arrays are commonly used in data analysis applications to store and process large datasets.

```csharp
class Program
{
    static void Main(string[] args)
    {
        double[] temperatures = { 25.3, 27.8, 24.5, 26.2, 28.1, 23.9 };

        // Calculate average temperature
        double sum = 0;
        foreach (double temp in temperatures)
        {
            sum += temp;
        }
        double averageTemperature = sum / temperatures.Length;

        Console.WriteLine($"Average Temperature: {averageTemperature}");
    }
}
```

These examples demonstrate how arrays in C# can be used in real-world scenarios such as employee management, inventory management, and data analysis. Arrays provide a convenient and efficient way to store and manipulate collections of data in C#.

Certainly! Here are a few practice exercises to help you become more comfortable with `for` loops in C#:

### Exercise 1: Print Even Numbers
Write a program that prints all even numbers from 1 to 20 using a `for` loop.

### Exercise 2: Reverse Print
Write a program that prints numbers from 10 to 1 in reverse order using a `for` loop.

### Exercise 3: Multiplication Table
Write a program that generates the multiplication table for a given number. Ask the user to enter a number and then print its multiplication table up to 10.

### Exercise 4: Factorial Calculation
Write a program to calculate the factorial of a given number using a `for` loop. The factorial of a number n is the product of all positive integers less than or equal to n.

### Exercise 5: Count Characters
Write a program that counts the number of occurrences of a specific character in a given string. Use a `for` loop to iterate over each character in the string.

### Exercise 6: Sum of Digits
Write a program that calculates the sum of digits of a given positive integer. For example, if the input is 123, the output should be 6 (1 + 2 + 3).

### Exercise 7: Prime Number Checker
Write a program that checks whether a given number is prime or not. Use a `for` loop to iterate over potential divisors of the number.

### Exercise 8: Fibonacci Series
Write a program that prints the Fibonacci series up to a specified number of terms. The Fibonacci series is a sequence of numbers where each number is the sum of the two preceding ones, starting from 0 and 1.

### Exercise 9: Pattern Printing
Write a program to print the following pattern using nested `for` loops:

```
1
1 2
1 2 3
1 2 3 4
1 2 3 4 5
```

### Exercise 10: Pascal's Triangle
Write a program to print the first n lines of Pascal's triangle. Pascal's triangle is a triangular array of binomial coefficients.

These exercises cover a range of scenarios where `for` loops can be used effectively. Feel free to start with simpler exercises and gradually move to more complex ones as you gain confidence. Happy coding!