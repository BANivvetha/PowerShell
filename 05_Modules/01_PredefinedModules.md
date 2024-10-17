PowerShell includes several built-in modules that provide a wide range of functionalities. Here are some of the key built-in modules:

1. **Microsoft.PowerShell.Management**: Contains cmdlets for managing Windows resources, such as files, services, and event logs.

2. **Microsoft.PowerShell.Utility**: Provides a variety of utility functions, including string manipulation, formatting, and working with data.

3. **Microsoft.PowerShell.Security**: Offers cmdlets related to security features, such as managing certificates and security policies.

4. **Microsoft.PowerShell.Diagnostics**: Contains cmdlets for working with system diagnostics, such as event logs and performance counters.

5. **Microsoft.PowerShell.Host**: Provides functionality for interacting with the PowerShell host environment, including console input and output.

6. **Microsoft.PowerShell.Providers**: Contains cmdlets that support different data stores, such as the file system, registry, and certificates.

7. **Microsoft.PowerShell.PackageManagement**: Facilitates package management across various package providers (like NuGet, MSI, etc.).

8. **Microsoft.PowerShell.Compatibility**: Helps with compatibility features for running older scripts or cmdlets.

You can list all the modules available in your PowerShell session using:

```powershell
Get-Module -ListAvailable
```

To learn more about a specific module, you can use:

```powershell
Get-Command -Module ModuleName
```

And for detailed help, use:

```powershell
Get-Help ModuleName
```

Here are some examples of built-in PowerShell modules along with practical use cases for each:

### 1. **Microsoft.PowerShell.Management**

**Example: Managing Files and Folders**
```powershell
# List all files in a directory
Get-ChildItem -Path C:\Temp

# Create a new directory
New-Item -Path C:\Temp\NewFolder -ItemType Directory

# Remove a file
Remove-Item -Path C:\Temp\OldFile.txt
```

### 2. **Microsoft.PowerShell.Utility**

**Example: String Manipulation and Data Formatting**
```powershell
# Convert a string to uppercase
$string = "hello world"
$string.ToUpper()  # Output: HELLO WORLD

# Format numbers
$number = 1234567.89
"{0:N2}" -f $number  # Output: 1,234,567.89
```

### 3. **Microsoft.PowerShell.Security**

**Example: Managing Certificates**
```powershell
# Get installed certificates in the LocalMachine store
Get-ChildItem -Path Cert:\LocalMachine\My

# Export a certificate to a file
$cert = Get-ChildItem -Path Cert:\LocalMachine\My | Select-Object -First 1
Export-Certificate -Cert $cert -FilePath C:\Temp\MyCertificate.cer
```

### 4. **Microsoft.PowerShell.Diagnostics**

**Example: Working with Event Logs**
```powershell
# Get the last 5 entries from the Application event log
Get-EventLog -LogName Application -Newest 5

# Clear the System event log
Clear-EventLog -LogName System
```

### 5. **Microsoft.PowerShell.Host**

**Example: Working with the PowerShell Host**
```powershell
# Get the version of the PowerShell host
$host.Version

# Write output to the console
Write-Host "Hello, PowerShell!"
```

### 6. **Microsoft.PowerShell.Providers**

**Example: Working with Different Data Stores**
```powershell
# List all drives (file system, registry, etc.)
Get-PSDrive

# Access the registry
Get-ChildItem -Path HKLM:\Software
```

### 7. **Microsoft.PowerShell.PackageManagement**

**Example: Managing Packages**
```powershell
# List available package providers
Get-PackageProvider -ListAvailable

# Install a package (example: NuGet)
Install-Package -Name PackageName
```

### 8. **Microsoft.PowerShell.ComputerManagement**

**Example: Managing System Services**
```powershell
# Get the status of services
Get-Service

# Start a specific service
Start-Service -Name "wuauserv"  # Windows Update Service
```

These examples illustrate how you can leverage built-in PowerShell modules for various tasks, from file management to system diagnostics. If you want to explore any specific module further, just let me know!
