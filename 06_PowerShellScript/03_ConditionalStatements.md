Conditional statements in PowerShell allow you to execute different code based on certain conditions. The most common conditional statements are `if`, `else`, and `switch`. Here are examples of each:

### 1. **If Statement**

The `if` statement executes a block of code if a specified condition is true.

**Example:**
```powershell
$age = 18

if ($age -ge 18) {
    Write-Host "You are an adult."
}
```

### 2. **If-Else Statement**

The `if-else` statement allows you to specify a block of code to execute if the condition is false.

**Example:**
```powershell
$age = 16

if ($age -ge 18) {
    Write-Host "You are an adult."
} else {
    Write-Host "You are a minor."
}
```

### 3. **If-ElseIf-Else Statement**

This structure allows for multiple conditions to be evaluated in sequence.

**Example:**
```powershell
$score = 75

if ($score -ge 90) {
    Write-Host "Grade: A"
} elseif ($score -ge 80) {
    Write-Host "Grade: B"
} elseif ($score -ge 70) {
    Write-Host "Grade: C"
} else {
    Write-Host "Grade: D"
}
```

### 4. **Switch Statement**

The `switch` statement evaluates a single expression against multiple possible values.

**Example:**
```powershell
$day = "Monday"

switch ($day) {
    "Monday" { Write-Host "Start of the work week." }
    "Wednesday" { Write-Host "Midweek." }
    "Friday" { Write-Host "End of the work week." }
    "Saturday" { Write-Host "Weekend!" }
    "Sunday" { Write-Host "Weekend!" }
    default { Write-Host "Just another day." }
}
```

### Summary

- Use `if` for basic conditional checks.
- Use `else` for alternative actions.
- Use `elseif` for multiple conditions.
- Use `switch` when comparing a single variable against multiple values.

# Advance SysAdmin Level Example

Here are some administrator-level PowerShell examples that incorporate conditional statements to make decisions based on the results of various checks or configurations.

### 1. **Creating a User Account with Conditional Checks**

This script checks if a user already exists before creating a new account.

```powershell
# Define user parameters
$username = "NewUser"
$password = "P@ssw0rd" | ConvertTo-SecureString -AsPlainText -Force
$fullName = "New User"

# Check if the user already exists
if (-not (Get-LocalUser -Name $username -ErrorAction SilentlyContinue)) {
    # Create the new user account
    New-LocalUser -Name $username -Password $password -FullName $fullName -Description "New user account for testing"
    Write-Host "User $username created."
} else {
    Write-Host "User $username already exists."
}
```

### 2. **Checking Disk Space with Conditional Alerts**

This script checks the available disk space on all drives and sends a warning if any drive is below a certain threshold.

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

### 3. **Restarting a Service Based on Status**

This script checks the status of a service and restarts it if it’s stopped.

```powershell
# Define service name
$serviceName = "wuauserv"  # Windows Update Service

# Get the service status
$service = Get-Service -Name $serviceName

if ($service.Status -eq 'Stopped') {
    Start-Service -Name $serviceName
    Write-Host "Service $serviceName was stopped and has been started."
} elseif ($service.Status -eq 'Running') {
    Write-Host "Service $serviceName is already running."
} else {
    Write-Host "Service $serviceName is in status: $($service.Status)."
}
```

### 4. **Exporting Active Directory Users with Conditional Checks**

This script checks if any users exist in Active Directory before exporting to CSV.

```powershell
# Import the Active Directory module
Import-Module ActiveDirectory

# Define the output file path
$outputPath = "C:\Temp\ADUsers.csv"

# Get user information
$users = Get-ADUser -Filter * -Property DisplayName, EmailAddress

if ($users) {
    $users | Select-Object DisplayName, EmailAddress | Export-Csv -Path $outputPath -NoTypeInformation
    Write-Host "Active Directory users exported to $outputPath."
} else {
    Write-Host "No users found in Active Directory."
}
```

### 5. **Monitoring System Uptime with Conditional Alerts**

This script checks if the system uptime is above a certain threshold and alerts accordingly.

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

These scripts demonstrate how to use conditional statements in PowerShell to perform administrative tasks based on certain conditions. This allows for more intelligent and efficient automation. If you have specific scenarios you'd like to explore further or need additional examples, just let me know!
