Loops in PowerShell scripts allow you to repeat actions multiple times, making them essential for automating repetitive tasks. Here are the main types of loops in PowerShell along with examples:

### 1. **For Loop**

The `for` loop is used when you know how many times you want to iterate.

**Example:**
```powershell
# Print numbers 1 to 5
for ($i = 1; $i -le 5; $i++) {
    Write-Host "Number: $i"
}
```

### 2. **ForEach Loop**

The `foreach` loop is used to iterate over each item in a collection (like an array or a list).

**Example:**
```powershell
# Define an array of names
$names = @("Alice", "Bob", "Charlie")

# Print each name
foreach ($name in $names) {
    Write-Host "Hello, $name!"
}
```

### 3. **While Loop**

The `while` loop continues to execute as long as the specified condition is true.

**Example:**
```powershell
# Initialize a counter
$count = 1

# Loop while count is less than or equal to 5
while ($count -le 5) {
    Write-Host "Count: $count"
    $count++
}
```

### 4. **Do-While Loop**

The `do-while` loop executes at least once and then continues as long as the condition is true.

**Example:**
```powershell
# Initialize a counter
$count = 1

# Loop until count exceeds 5
do {
    Write-Host "Count: $count"
    $count++
} while ($count -le 5)
```

### 5. **Do-Until Loop**

The `do-until` loop executes until the specified condition becomes true.

**Example:**
```powershell
# Initialize a counter
$count = 1

# Loop until count equals 5
do {
    Write-Host "Count: $count"
    $count++
} until ($count -gt 5)
```

### Summary

- **For Loop**: Use when the number of iterations is known.
- **ForEach Loop**: Use for iterating over a collection.
- **While Loop**: Use when the number of iterations is unknown and depends on a condition.
- **Do-While Loop**: Similar to `while`, but guarantees at least one execution.
- **Do-Until Loop**: Executes until a condition is true.

# Advanced SysAdmin Level Examples
Here are some PowerShell loop examples specifically designed for system administrators. These examples illustrate how to automate common administrative tasks using loops.

### 1. **Batch User Creation**

This script creates multiple user accounts based on a predefined list of usernames.

```powershell
# Define an array of usernames
$usernames = @("User1", "User2", "User3")

# Loop through each username
foreach ($username in $usernames) {
    # Check if the user already exists
    if (-not (Get-LocalUser -Name $username -ErrorAction SilentlyContinue)) {
        # Create the new user account
        $password = "P@ssw0rd" | ConvertTo-SecureString -AsPlainText -Force
        New-LocalUser -Name $username -Password $password -FullName "$username User" -Description "Created for testing"
        Write-Host "User $username created."
    } else {
        Write-Host "User $username already exists."
    }
}
```

### 2. **Monitoring Disk Space**

This script checks the disk space on all drives and alerts if any drive falls below a specified threshold.

```powershell
# Define threshold (in GB)
$threshold = 10

# Get disk space information
$drives = Get-PSDrive -PSProvider FileSystem

foreach ($drive in $drives) {
    $freeSpaceGB = [math]::round($drive.Free / 1GB, 2)

    if ($freeSpaceGB -lt $threshold) {
        Write-Host "Warning: Drive $($drive.Name) has only $freeSpaceGB GB free space."
    } else {
        Write-Host "Drive $($drive.Name) is healthy with $freeSpaceGB GB free space."
    }
}
```

### 3. **Restarting Services Based on Status**

This script checks a list of services and restarts any that are stopped.

```powershell
# Define an array of service names
$services = @("wuauserv", "Spooler", "bits")

foreach ($serviceName in $services) {
    # Get the service status
    $service = Get-Service -Name $serviceName -ErrorAction SilentlyContinue
    
    if ($service) {
        if ($service.Status -eq 'Stopped') {
            Start-Service -Name $serviceName
            Write-Host "Service $serviceName was stopped and has been started."
        } elseif ($service.Status -eq 'Running') {
            Write-Host "Service $serviceName is already running."
        } else {
            Write-Host "Service $serviceName is in status: $($service.Status)."
        }
    } else {
        Write-Host "Service $serviceName not found."
    }
}
```

### 4. **Exporting Active Directory Users to CSV**

This script retrieves user information from Active Directory and exports it to a CSV file, iterating through users in batches.

```powershell
# Import the Active Directory module
Import-Module ActiveDirectory

# Define the output file path
$outputPath = "C:\Temp\ADUsers.csv"

# Get user information in batches
$users = Get-ADUser -Filter * -Property DisplayName, EmailAddress

if ($users) {
    $users | Select-Object DisplayName, EmailAddress | Export-Csv -Path $outputPath -NoTypeInformation
    Write-Host "Active Directory users exported to $outputPath."
} else {
    Write-Host "No users found in Active Directory."
}
```

### 5. **System Uptime Monitoring**

This script checks the system uptime and logs a message if it exceeds a certain threshold.

```powershell
# Get the last boot time
$lastBootTime = (Get-CimInstance -ClassName Win32_OperatingSystem).LastBootUpTime
$uptime = [Management.ManagementDateTimeConverter]::ToDateTime($lastBootTime)

# Calculate the uptime duration
$uptimeDuration = (Get-Date) - $uptime

# Define threshold (in days)
$thresholdDays = 30

if ($uptimeDuration.Days -ge $thresholdDays) {
    Write-Host "Warning: System uptime exceeds $thresholdDays days."
} else {
    Write-Host "System uptime is within acceptable limits."
}
```

### Summary

These examples demonstrate how loops can be effectively used to automate administrative tasks, from user management to monitoring system health. By integrating loops with conditional statements, you can create powerful scripts that enhance efficiency and ensure compliance. 
