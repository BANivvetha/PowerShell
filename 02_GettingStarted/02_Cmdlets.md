Cmdlets in PowerShell are specialized .NET classes that perform specific functions. They follow a consistent naming convention of `Verb-Noun`. Here’s an overview of some commonly used cmdlets along with examples:

### 1. **Get-Command**
   - **Description**: Retrieves all cmdlets, functions, and scripts available in the session.
   - **Example**:
     ```powershell
     Get-Command
     ```

### 2. **Get-Help**
   - **Description**: Displays help information about cmdlets, functions, and concepts.
   - **Example**:
     ```powershell
     Get-Help Get-Process
     ```

### 3. **Get-Process**
   - **Description**: Retrieves a list of all running processes on the local machine.
   - **Example**:
     ```powershell
     Get-Process
     ```

### 4. **Get-Service**
   - **Description**: Retrieves the status of services on a local or remote machine.
   - **Example**:
     ```powershell
     Get-Service
     ```

### 5. **Stop-Service**
   - **Description**: Stops a running service.
   - **Example**:
     ```powershell
     Stop-Service -Name "wuauserv"  # Stops the Windows Update service
     ```

### 6. **Start-Service**
   - **Description**: Starts a stopped service.
   - **Example**:
     ```powershell
     Start-Service -Name "wuauserv"  # Starts the Windows Update service
     ```

### 7. **Get-ChildItem**
   - **Description**: Lists the contents of a directory (similar to `ls` or `dir`).
   - **Example**:
     ```powershell
     Get-ChildItem -Path C:\  # Lists files and folders in the C: drive
     ```

### 8. **Set-Location**
   - **Description**: Changes the current working directory.
   - **Example**:
     ```powershell
     Set-Location -Path C:\Users  # Changes to the Users directory
     ```

### 9. **Copy-Item**
   - **Description**: Copies an item from one location to another.
   - **Example**:
     ```powershell
     Copy-Item -Path "C:\Source\File.txt" -Destination "C:\Destination\File.txt"
     ```

### 10. **Remove-Item**
   - **Description**: Deletes files or directories.
   - **Example**:
     ```powershell
     Remove-Item -Path "C:\Temp\OldFile.txt"  # Deletes a specific file
     ```

### 11. **Set-Content**
   - **Description**: Writes or replaces the content in a file.
   - **Example**:
     ```powershell
     Set-Content -Path "C:\Temp\example.txt" -Value "Hello, PowerShell!"
     ```

### 12. **Get-Content**
   - **Description**: Retrieves the content of a file.
   - **Example**:
     ```powershell
     Get-Content -Path "C:\Temp\example.txt"  # Displays the content of the file
     ```

### 13. **Export-Csv**
   - **Description**: Exports data to a CSV file.
   - **Example**:
     ```powershell
     Get-Process | Export-Csv -Path "C:\Temp\Processes.csv" -NoTypeInformation
     ```

### 14. **Import-Csv**
   - **Description**: Imports data from a CSV file.
   - **Example**:
     ```powershell
     $processes = Import-Csv -Path "C:\Temp\Processes.csv"
     ```

### 15. **Invoke-WebRequest**
   - **Description**: Sends HTTP requests to web pages or APIs.
   - **Example**:
     ```powershell
     Invoke-WebRequest -Uri "https://www.example.com" -OutFile "C:\Temp\example.html"
     ```

### Conclusion
Cmdlets are the building blocks of PowerShell, allowing you to perform a wide variety of tasks efficiently. Familiarizing yourself with these common cmdlets will help you navigate and automate tasks in your environment effectively!
