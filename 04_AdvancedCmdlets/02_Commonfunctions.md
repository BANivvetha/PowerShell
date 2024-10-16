PowerShell provides a wide range of functions and methods that can be used with various variable types. Here’s a list of commonly used functions and methods for different variable types, along with examples for clarity.

### Commonly Used Functions for Variables in PowerShell

#### 1. String Functions

- **Length**: Returns the length of the string.
  
    ```powershell
    $string = "Hello, World!"
    $length = $string.Length
    Write-Host "Length: $length"  # Outputs: 13
    ```

- **Substring**: Extracts a substring.
  
    ```powershell
    $sub = $string.Substring(7, 5)  # From index 7, length 5
    Write-Host "Substring: $sub"  # Outputs: World
    ```

- **Replace**: Replaces a specified substring.
  
    ```powershell
    $newString = $string.Replace("World", "PowerShell")
    Write-Host $newString  # Outputs: Hello, PowerShell!
    ```

- **Split**: Splits a string into an array based on a delimiter.
  
    ```powershell
    $words = $string.Split(", ")
    Write-Host "First Word: $($words[0])"  # Outputs: Hello
    ```

- **Trim**: Removes leading and trailing whitespace.
  
    ```powershell
    $trimmed = "   Hello   ".Trim()
    Write-Host "Trimmed: '$trimmed'"  # Outputs: 'Hello'
    ```

#### 2. Integer Functions

- **Max/Min**: Returns the maximum or minimum of two integers.
  
    ```powershell
    $maxValue = [math]::Max(5, 10)
    Write-Host "Max: $maxValue"  # Outputs: 10
    ```

- **Increment/Decrement**: Adjusts integer values.
  
    ```powershell
    $age = 30
    $age++  # Increment
    Write-Host "Age: $age"  # Outputs: 31
    ```

- **Square Root**: Calculates the square root.
  
    ```powershell
    $sqrtValue = [math]::Sqrt(16)
    Write-Host "Square Root: $sqrtValue"  # Outputs: 4
    ```

#### 3. Double Functions

- **Round**: Rounds a double to the nearest integer.
  
    ```powershell
    $price = 19.99
    $roundedPrice = [math]::Round($price)
    Write-Host "Rounded Price: $roundedPrice"  # Outputs: 20
    ```

- **Floor/Ceiling**: Rounds down/up to the nearest integer.
  
    ```powershell
    $floorValue = [math]::Floor($price)
    $ceilingValue = [math]::Ceiling($price)
    Write-Host "Floor: $floorValue, Ceiling: $ceilingValue"  # Outputs: Floor: 19, Ceiling: 20
    ```

- **Add/Subtract**: Standard arithmetic operations.
  
    ```powershell
    $newPrice = $price + 5.00
    Write-Host "New Price: $newPrice"  # Outputs: 24.99
    ```

#### 4. Boolean Functions

- **Negation**: Inverts a boolean value.
  
    ```powershell
    $isTrue = $true
    $isFalse = -not $isTrue
    Write-Host "Is False: $isFalse"  # Outputs: False
    ```

- **Logical Operations**: AND, OR operations.
  
    ```powershell
    $isStudent = $true
    $hasID = $false
    $canEnroll = $isStudent -and $hasID  # Logical AND
    Write-Host "Can Enroll: $canEnroll"  # Outputs: False
    ```

#### 5. Array Functions

- **Length**: Returns the number of elements in the array.
  
    ```powershell
    $colors = @("Red", "Green", "Blue")
    $colorCount = $colors.Length
    Write-Host "Number of Colors: $colorCount"  # Outputs: 3
    ```

- **Sort**: Sorts the array.
  
    ```powershell
    $sortedColors = $colors | Sort-Object
    Write-Host "Sorted Colors: $sortedColors"  # Outputs: Blue, Green, Red
    ```

- **Add**: Adds an element to the array.
  
    ```powershell
    $colors += "Yellow"
    Write-Host "Updated Colors: $colors"  # Outputs: Red, Green, Blue, Yellow
    ```

- **ForEach**: Iterates over each item.
  
    ```powershell
    foreach ($color in $colors) {
        Write-Host "Color: $color"
    }
    ```

#### 6. Hash Table Functions

- **Add**: Adds a new key-value pair.
  
    ```powershell
    $person = @{
        Name = "Alice"
        Age = 30
    }
    $person['City'] = "New York"
    ```

- **Remove**: Removes a key-value pair.
  
    ```powershell
    $person.Remove('Age')
    Write-Host "Updated Person: $($person)"
    ```

- **ContainsKey**: Checks if a specific key exists.
  
    ```powershell
    $exists = $person.ContainsKey('Name')
    Write-Host "Contains 'Name': $exists"  # Outputs: True
    ```

- **Keys/Values**: Retrieves all keys or values.
  
    ```powershell
    $keys = $person.Keys
    $values = $person.Values
    Write-Host "Keys: $keys"  # Outputs: Name, City
    Write-Host "Values: $values"  # Outputs: Alice, New York
    ```

### Summary

PowerShell provides a rich set of functions and methods to manipulate and operate on various variable types. Understanding these functions enables you to write more efficient and effective scripts. If you have any specific use cases or further questions, feel free to ask!
