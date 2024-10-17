PowerShell supports various data types that you can use in your scripts. Here’s an overview of some common data types along with examples for each:

### 1. **String**

Strings are sequences of characters.

**Example:**
```powershell
# Define a string
$name = "Alice"
Write-Host "Hello, $name!"  # Output: Hello, Alice!
```

### 2. **Integer**

Integers are whole numbers without a decimal point.

**Example:**
```powershell
# Define an integer
$age = 30
Write-Host "Age: $age"  # Output: Age: 30
```

### 3. **Float**

Floats (or doubles) are numbers that can have decimal points.

**Example:**
```powershell
# Define a float
$price = 19.99
Write-Host "Price: $price"  # Output: Price: 19.99
```

### 4. **Boolean**

Booleans represent truth values: `$true` or `$false`.

**Example:**
```powershell
# Define a boolean
$isAdmin = $true
if ($isAdmin) {
    Write-Host "User is an admin."  # Output: User is an admin.
}
```

### 5. **Array**

Arrays are collections of items.

**Example:**
```powershell
# Define an array
$colors = @("Red", "Green", "Blue")
Write-Host "First color: $($colors[0])"  # Output: First color: Red
```

### 6. **HashTable**

HashTables are collections of key-value pairs.

**Example:**
```powershell
# Define a hashtable
$person = @{
    Name = "Alice"
    Age = 30
}
Write-Host "Name: $($person['Name']), Age: $($person['Age'])"  # Output: Name: Alice, Age: 30
```

### 7. **DateTime**

DateTime represents date and time values.

**Example:**
```powershell
# Define a DateTime
$today = Get-Date
Write-Host "Today's date: $today"  # Output: Today's date: <current date and time>
```

### 8. **Object**

Objects are instances of .NET classes and can have properties and methods.

**Example:**
```powershell
# Create a simple object
$car = New-Object PSObject -Property @{
    Make  = "Toyota"
    Model = "Camry"
    Year  = 2020
}
Write-Host "Car: $($car.Make) $($car.Model), Year: $($car.Year)"  # Output: Car: Toyota Camry, Year: 2020
```

### Summary

PowerShell provides a rich set of data types to work with, enabling you to handle different kinds of data in your scripts. Understanding these data types is essential for effective scripting and automation.

