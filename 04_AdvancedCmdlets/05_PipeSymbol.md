The pipe symbol (`|`) in PowerShell is a powerful feature that allows you to send the output of one command directly as input to another command. This enables you to build complex operations and streamline your scripting process.

### Basic Usage of the Pipe

When you use the pipe, the output of the command on the left side is passed to the command on the right side. Here are some common examples:

#### 1. **Basic Example: Listing Processes**

You can list all running processes and then filter them:

```powershell
Get-Process | Where-Object { $_.CPU -gt 100 }
```

In this example:
- `Get-Process` retrieves a list of all processes.
- `Where-Object` filters the processes to show only those using more than 100 CPU seconds.

#### 2. **Selecting Specific Properties**

You can use the pipe to select specific properties from the output:

```powershell
Get-Service | Select-Object Name, Status
```

Here:
- `Get-Service` retrieves all services.
- `Select-Object` selects only the `Name` and `Status` properties for display.

#### 3. **Sorting Output**

You can sort the output of a command using the pipe:

```powershell
Get-Process | Sort-Object CPU -Descending
```

This command retrieves all processes and sorts them by CPU usage in descending order.

#### 4. **Counting Items**

You can count the number of items returned by a command:

```powershell
Get-EventLog -LogName Application | Measure-Object
```

Here:
- `Get-EventLog` retrieves events from the Application log.
- `Measure-Object` counts the number of events.

### Intermediate Examples

#### 5. **Exporting to a CSV File**

You can pipe output directly into a file format:

```powershell
Get-Process | Select-Object Name, Id, CPU | Export-Csv -Path "C:\Processes.csv" -NoTypeInformation
```

This command retrieves process details and exports them to a CSV file.

#### 6. **Using Multiple Pipes**

You can chain multiple commands together:

```powershell
Get-Service | Where-Object { $_.Status -eq 'Running' } | Sort-Object Name | Select-Object Name, DisplayName
```

This command retrieves running services, sorts them by name, and selects their name and display name.

### Advanced Examples

#### 7. **Creating a Custom Object with Pipe**

You can create custom objects and output them:

```powershell
Get-Process | ForEach-Object {
    [PSCustomObject]@{
        ProcessName = $_.Name
        Id          = $_.Id
        Memory      = $_.WorkingSet / 1MB
    }
} | Sort-Object Memory -Descending
```

This command creates custom objects with process details and sorts them by memory usage.

#### 8. **Filtering by Complex Conditions**

You can use pipes with complex filtering conditions:

```powershell
Get-EventLog -LogName System | Where-Object {
    $_.EventID -eq 6006 -and $_.TimeGenerated -gt (Get-Date).AddDays(-7)
}
```

This command retrieves events from the System log with a specific event ID that occurred in the last week.

### Summary

The pipe symbol in PowerShell is a powerful tool for creating pipelines that connect commands and allow you to process data in a flexible and efficient manner. Understanding how to effectively use the pipe will enhance your ability to write concise and effective PowerShell scripts. If you have specific scenarios in mind or want further examples, feel free to ask!
