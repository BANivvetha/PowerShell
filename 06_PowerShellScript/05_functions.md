Functions in PowerShell are reusable blocks of code that perform a specific task. They help you organize your scripts, reduce redundancy, and improve maintainability. Here’s an overview of how to create and use functions in PowerShell, along with examples.

### Defining a Function

You define a function using the `function` keyword, followed by the function name and a script block enclosed in curly braces.

**Basic Syntax:**
```powershell
function FunctionName {
    # Function code goes here
}
```

### Example 1: Simple Function

Here’s a simple function that outputs a greeting.

```powershell
function Greet {
    param (
        [string]$Name
    )
    Write-Host "Hello, $Name!"
}

# Call the function
Greet -Name "Alice"  # Output: Hello, Alice!
```

### Example 2: Function with Default Parameter

This function uses a default value for a parameter.

```powershell
function Greet {
    param (
        [string]$Name = "World"
    )
    Write-Host "Hello, $Name!"
}

# Call the function without parameters
Greet  # Output: Hello, World!
```

### Example 3: Function Returning a Value

You can return values from a function using the `return` keyword or by simply placing the value at the end of the function.

```powershell
function Get-Square {
    param (
        [int]$Number
    )
    return $Number * $Number
}

# Call the function and store the result
$result = Get-Square -Number 5
Write-Host "The square of 5 is $result."  # Output: The square of 5 is 25.
```

### Example 4: Function with Error Handling

This function demonstrates how to handle errors within a function.

```powershell
function Divide-Numbers {
    param (
        [double]$Numerator,
        [double]$Denominator
    )

    if ($Denominator -eq 0) {
        Write-Host "Error: Cannot divide by zero."
        return
    }

    return $Numerator / $Denominator
}

# Call the function
$result = Divide-Numbers -Numerator 10 -Denominator 2
Write-Host "Result: $result"  # Output: Result: 5

$result = Divide-Numbers -Numerator 10 -Denominator 0
# Output: Error: Cannot divide by zero.
```

### Summary

Functions in PowerShell are powerful tools for creating reusable and organized code. They can take parameters, return values, and handle errors, making them essential for effective scripting. By using functions, you can significantly improve the clarity and maintainability of your PowerShell scripts.

# Advance System Admin Level example
Sure! Here’s a complete PowerShell script designed for system administrators. This script includes functions for user management, disk space monitoring, and service status checking. Each function is modular, making it easy to reuse and maintain.

### PowerShell Script: AdminUtility.ps1

```powershell
# AdminUtility.ps1

# Function to create a new user
function New-User {
    param (
        [string]$Username,
        [string]$Password = "P@ssw0rd",
        [string]$FullName = "New User"
    )
    
    # Check if the user already exists
    if (-not (Get-LocalUser -Name $Username -ErrorAction SilentlyContinue)) {
        $SecurePassword = $Password | ConvertTo-SecureString -AsPlainText -Force
        New-LocalUser -Name $Username -Password $SecurePassword -FullName $FullName -Description "Created for admin tasks"
        Write-Host "User '$Username' created successfully."
    } else {
        Write-Host "User '$Username' already exists."
    }
}

# Function to check disk space
function Check-DiskSpace {
    param (
        [int]$ThresholdGB = 10
    )
    
    $drives = Get-PSDrive -PSProvider FileSystem

    foreach ($drive in $drives) {
        $freeSpaceGB = [math]::round($drive.Free / 1GB, 2)

        if ($freeSpaceGB -lt $ThresholdGB) {
            Write-Host "Warning: Drive $($drive.Name) has only $freeSpaceGB GB free space."
        } else {
            Write-Host "Drive $($drive.Name) is healthy with $freeSpaceGB GB free space."
        }
    }
}

# Function to check and restart services
function Restart-ServiceIfStopped {
    param (
        [string[]]$ServiceNames
    )

    foreach ($serviceName in $ServiceNames) {
        $service = Get-Service -Name $serviceName -ErrorAction SilentlyContinue
        
        if ($service) {
            if ($service.Status -eq 'Stopped') {
                Start-Service -Name $serviceName
                Write-Host "Service '$serviceName' was stopped and has been started."
            } elseif ($service.Status -eq 'Running') {
                Write-Host "Service '$serviceName' is already running."
            } else {
                Write-Host "Service '$serviceName' is in status: $($service.Status)."
            }
        } else {
            Write-Host "Service '$serviceName' not found."
        }
    }
}

# Main script execution
Write-Host "Starting Administrative Utility Script..."

# Example usage of the New-User function
New-User -Username "TestUser1"

# Example usage of the Check-DiskSpace function
Check-DiskSpace -ThresholdGB 10

# Example usage of the Restart-ServiceIfStopped function
Restart-ServiceIfStopped -ServiceNames @("wuauserv", "Spooler", "bits")

Write-Host "Administrative Utility Script completed."
```

### Script Breakdown

1. **New-User Function**: Creates a new local user if the username does not already exist. The password can be customized, and it defaults to "P@ssw0rd."

2. **Check-DiskSpace Function**: Checks available disk space on all drives and warns if free space is below a specified threshold (default is 10 GB).

3. **Restart-ServiceIfStopped Function**: Checks the status of specified services and restarts any that are stopped. It also reports the status of each service.

4. **Main Script Execution**: 
   - Calls the `New-User` function to create a user named "TestUser1."
   - Calls the `Check-DiskSpace` function to check disk space.
   - Calls the `Restart-ServiceIfStopped` function to check and potentially restart specified services.

### Usage

1. **Save the Script**: Save the script as `AdminUtility.ps1`.

2. **Run the Script**: Open PowerShell as an administrator, navigate to the directory where the script is saved, and run it:

   ```powershell
   Set-ExecutionPolicy RemoteSigned  # If not already set
   .\AdminUtility.ps1
   ```

This script provides a good foundation for system administration tasks and can be expanded or modified to fit specific needs. If you have any questions or need further customization, let me know!
