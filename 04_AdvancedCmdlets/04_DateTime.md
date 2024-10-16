In PowerShell, you can manipulate date and time using various cmdlets and methods. Below is a detailed overview of how to get and set the system date and time, including examples.

### Getting the Current Date and Time

#### Get-SystemDate

To get the current system date:

```powershell
$currentDate = Get-Date
Write-Host "Current Date: $currentDate"
```

#### Get-SystemTime

To get the current system time:

```powershell
$currentTime = Get-Date -Format "HH:mm:ss"
Write-Host "Current Time: $currentTime"
```

### Setting the System Date and Time

**Note:** Setting the system date and time usually requires administrative privileges.

#### Set-SystemDate

To set the system date, you can use the following command:

```powershell
# Set the date to January 1, 2024
$newDate = Get-Date -Year 2024 -Month 1 -Day 1
Set-Date -Date $newDate
Write-Host "System Date set to: $newDate"
```

#### Set-SystemTime

To set the system time, you can do the following:

```powershell
# Set the time to 14:30 (2:30 PM)
$newTime = Get-Date -Hour 14 -Minute 30 -Second 0
Set-Date -Date $newTime
Write-Host "System Time set to: $newTime"
```

### Working with Date and Time Formats

You can format dates and times in various ways using the `-Format` parameter:

```powershell
$formattedDate = Get-Date -Format "yyyy-MM-dd"
$formattedTime = Get-Date -Format "hh:mm tt"
Write-Host "Formatted Date: $formattedDate"
Write-Host "Formatted Time: $formattedTime"
```

### Additional Functions

#### Calculating Time Differences

You can calculate differences between dates:

```powershell
$date1 = Get-Date "2024-01-01"
$date2 = Get-Date "2024-01-15"
$timeDifference = $date2 - $date1
Write-Host "Difference in days: $($timeDifference.Days) days"
```

#### Adding and Subtracting Time

You can also add or subtract time easily:

```powershell
$futureDate = (Get-Date).AddDays(10)
$pastDate = (Get-Date).AddMonths(-1)
Write-Host "Date 10 days from now: $futureDate"
Write-Host "Date 1 month ago: $pastDate"
```

### Summary

- **Get-Date**: Use to retrieve the current date and time.
- **Set-Date**: Use to set the system date and time.
- Date and time can be formatted using the `-Format` parameter.
- PowerShell allows calculations and adjustments to dates easily.

### Important Notes

- Changing the system date and time usually requires administrative privileges, so you might need to run PowerShell as an administrator.
- Ensure that your scripts handle date and time formats according to your locale and requirements.

If you have further questions or need specific examples, feel free to ask!
