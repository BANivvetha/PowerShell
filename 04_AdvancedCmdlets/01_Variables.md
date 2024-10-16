In PowerShell, variables are used to store data that can be referenced and manipulated throughout your scripts. Here’s a detailed overview of how to work with variables in PowerShell, including declaration, scope, types, and examples.

### Declaring Variables

Variables in PowerShell are declared by using the `$` symbol followed by the variable name. You can assign values directly to variables.

#### Example:

```powershell
# Declaring a variable
$message = "Hello, PowerShell!"
Write-Host $message
```

### Variable Naming Conventions

- Variable names can include letters, numbers, and underscores.
- They cannot start with a number.
- It’s common to use camelCase or PascalCase for readability.

### Data Types

PowerShell variables are dynamically typed, meaning you don't need to specify a type when you declare a variable. However, you can explicitly cast variables to specific types if needed.

#### Common Data Types:

- **String**: Text data.
- **Integer**: Whole numbers.
- **Double**: Floating-point numbers.
- **Boolean**: True/False values.
- **Array**: A collection of items.
- **Hash Table**: A collection of key-value pairs.

 Let’s explore the fundamental data types in PowerShell—String, Integer, Double, Boolean, Array, and Hash Table—along with detailed explanations, examples, and relevant functions for each.

### 1. String

**Definition**: A string is a sequence of characters used to represent text.

#### Example:

```powershell
# String variable
$message = "Hello, PowerShell!"
Write-Host $message
```

#### Common String Functions:

- **Length**: Returns the length of the string.

    ```powershell
    $length = $message.Length
    Write-Host "Length: $length"
    ```

- **Substring**: Extracts a substring from a string.

    ```powershell
    $sub = $message.Substring(7, 11)  # From index 7, length 11
    Write-Host "Substring: $sub"
    ```

- **Replace**: Replaces occurrences of a specified string.

    ```powershell
    $newMessage = $message.Replace("PowerShell", "World")
    Write-Host $newMessage  # Outputs: Hello, World!
    ```

- **ToUpper/ToLower**: Converts the string to uppercase or lowercase.

    ```powershell
    Write-Host $message.ToUpper()  # Outputs: HELLO, POWERSHELL!
    ```

### 2. Integer

**Definition**: An integer is a whole number without a fractional component.

#### Example:

```powershell
# Integer variable
$age = 30
Write-Host "Age: $age"
```

#### Common Integer Functions:

- **Add**: Performs addition.

    ```powershell
    $newAge = $age + 5
    Write-Host "New Age: $newAge"
    ```

- **Subtract**: Performs subtraction.

    ```powershell
    $oldAge = $age - 5
    Write-Host "Old Age: $oldAge"
    ```

- **Max/Min**: Returns the maximum or minimum of two integers.

    ```powershell
    $maxValue = [math]::Max($age, $newAge)
    Write-Host "Max Age: $maxValue"
    ```

- **Increment**: Increases the integer by one.

    ```powershell
    $age++
    Write-Host "Incremented Age: $age"
    ```

### 3. Double

**Definition**: A double is a floating-point number that can represent decimal values.

#### Example:

```powershell
# Double variable
$price = 19.99
Write-Host "Price: $price"
```

#### Common Double Functions:

- **Round**: Rounds a double to the nearest integer.

    ```powershell
    $roundedPrice = [math]::Round($price)
    Write-Host "Rounded Price: $roundedPrice"
    ```

- **Floor/Ceiling**: Rounds down or up to the nearest integer.

    ```powershell
    $floorValue = [math]::Floor($price)
    $ceilingValue = [math]::Ceiling($price)
    Write-Host "Floor: $floorValue, Ceiling: $ceilingValue"
    ```

- **Add/Subtract**: Standard arithmetic operations.

    ```powershell
    $newPrice = $price + 5.00
    Write-Host "New Price: $newPrice"
    ```

### 4. Boolean

**Definition**: A boolean represents a true or false value.

#### Example:

```powershell
# Boolean variable
$isStudent = $true
Write-Host "Is Student: $isStudent"
```

#### Common Boolean Functions:

- **Negation**: Inverts the boolean value.

    ```powershell
    $isNotStudent = -not $isStudent
    Write-Host "Is Not Student: $isNotStudent"
    ```

- **Logical Operations**: AND, OR, NOT operations.

    ```powershell
    $hasID = $true
    $canEnroll = $isStudent -and $hasID  # Logical AND
    Write-Host "Can Enroll: $canEnroll"
    ```

### 5. Array

**Definition**: An array is a collection of items, which can be of any data type.

#### Example:

```powershell
# Array variable
$colors = @("Red", "Green", "Blue")
Write-Host "First Color: $($colors[0])"
```

#### Common Array Functions:

- **Length**: Gets the number of elements in the array.

    ```powershell
    $colorCount = $colors.Length
    Write-Host "Number of Colors: $colorCount"
    ```

- **Add**: Adds an element to the array.

    ```powershell
    $colors += "Yellow"
    Write-Host "Updated Colors: $colors"
    ```

- **Sort**: Sorts the array.

    ```powershell
    $sortedColors = $colors | Sort-Object
    Write-Host "Sorted Colors: $sortedColors"
    ```

- **ForEach**: Iterates over each item.

    ```powershell
    foreach ($color in $colors) {
        Write-Host "Color: $color"
    }
    ```
**Example of a Multidimensional Array:**

```powershell
# Multidimensional array
$matrix = @( @(1, 2, 3), @(4, 5, 6), @(7, 8, 9) )

Write-Host "Element at (1,2): $($matrix[1][2])"  # Outputs: 6
```

### 6. Hash Table

**Definition**: A hash table is a collection of key-value pairs, allowing for efficient data retrieval based on keys.

#### Example:

```powershell
# Hash table variable
$person = @{
    Name = "Alice"
    Age = 30
    City = "New York"
}
Write-Host "Name: $($person['Name'])"
```

#### Common Hash Table Functions:

- **Add**: Adds a new key-value pair.

    ```powershell
    $person['Occupation'] = "Engineer"
    ```

- **Remove**: Removes a key-value pair.

    ```powershell
    $person.Remove('City')
    Write-Host "Updated Person: $($person)"
    ```

- **Keys/Values**: Retrieves all keys or values.

    ```powershell
    $keys = $person.Keys
    $values = $person.Values
    Write-Host "Keys: $keys"
    Write-Host "Values: $values"
    ```

- **ContainsKey**: Checks if a specific key exists.

    ```powershell
    $exists = $person.ContainsKey('Name')
    Write-Host "Contains 'Name': $exists"
    ```
### 4. Using Cmdlets to Manage Variables

PowerShell provides cmdlets like `Get-Variable`, `Set-Variable`, and `Remove-Variable` to manage variables dynamically.

**Example of Using Cmdlets:**

```powershell
# Creating a variable dynamically
Set-Variable -Name "dynamicVar" -Value "I am dynamic!"
Write-Host $dynamicVar

# Getting variable information
$varInfo = Get-Variable -Name "dynamicVar"
Write-Host "Variable Name: $($varInfo.Name), Value: $($varInfo.Value)"

# Removing a variable
Remove-Variable -Name "dynamicVar" -ErrorAction SilentlyContinue
```

### Summary

- **String**: Used for text data, supports methods for manipulation and formatting.
- **Integer**: Represents whole numbers, supports arithmetic operations.
- **Double**: Represents floating-point numbers, supports rounding and precision handling.
- **Boolean**: Represents true/false values, supports logical operations.
- **Array**: A collection of items, supports indexing, sorting, and iteration.
- **Hash Table**: A collection of key-value pairs, supports efficient retrieval, addition, and deletion of entries.

Each data type in PowerShell serves a specific purpose and provides various built-in methods and functions to manipulate and use data effectively. If you have more specific questions or need further examples, feel free to ask!

### Special Variables

PowerShell also has several built-in special variables:

- `$_`: Represents the current object in the pipeline.
- `$?`: Contains the success status of the last command.
- `$$`: Contains the process ID of the last background command.
- `$env`: Used to access environment variables.

#### Example of Special Variables:

```powershell
# Using $_ in a pipeline
1..5 | ForEach-Object { Write-Host "Processing number $_" }

# Check the last command's success
if ($?) {
    Write-Host "The last command was successful."
}
```

### Summary

- Variables are declared with a `$` symbol and can store various data types.
- PowerShell uses dynamic typing, allowing flexibility in variable types.
- Variable scope determines where variables can be accessed.
- Special variables provide additional context and functionality.

If you have more questions or need examples on specific topics, feel free to ask!
