Certainly! Here’s a list of commonly used PowerShell cmdlets that do not use the "Get" or "Set" verbs, along with examples of how to use them:

### Common PowerShell Cmdlets (Other than Get and Set)

#### 1. **New-Item**
   - **Description**: Creates a new item, such as a file, folder, or registry key.
   - **Example**:
     ```powershell
     New-Item -Path "C:\Temp\NewFolder" -ItemType Directory
     ```

#### 2. **Remove-Item**
   - **Description**: Deletes files, folders, or other items.
   - **Example**:
     ```powershell
     Remove-Item -Path "C:\Temp\OldFolder" -Recurse
     ```

#### 3. **Copy-Item**
   - **Description**: Copies an item from one location to another.
   - **Example**:
     ```powershell
     Copy-Item -Path "C:\Temp\example.txt" -Destination "C:\Temp\Backup\example.txt"
     ```

#### 4. **Move-Item**
   - **Description**: Moves an item from one location to another.
   - **Example**:
     ```powershell
     Move-Item -Path "C:\Temp\example.txt" -Destination "C:\Temp\Archived\example.txt"
     ```

#### 5. **Start-Process**
   - **Description**: Starts a process, such as an application or script.
   - **Example**:
     ```powershell
     Start-Process -FilePath "notepad.exe"
     ```

#### 6. **Stop-Process**
   - **Description**: Stops a running process by its name or ID.
   - **Example**:
     ```powershell
     Stop-Process -Name "notepad" -Force
     ```

#### 7. **Test-Path**
   - **Description**: Determines whether a specified path exists.
   - **Example**:
     ```powershell
     Test-Path -Path "C:\Temp\example.txt"
     ```

#### 8. **Invoke-Command**
   - **Description**: Executes commands on local or remote computers.
   - **Example**:
     ```powershell
     Invoke-Command -ScriptBlock { Get-Process }
     ```

#### 9. **Export-Csv**
   - **Description**: Exports data to a CSV file.
   - **Example**:
     ```powershell
     Get-Process | Export-Csv -Path "C:\Temp\Processes.csv" -NoTypeInformation
     ```

#### 10. **Import-Csv**
   - **Description**: Imports data from a CSV file.
   - **Example**:
     ```powershell
     $data = Import-Csv -Path "C:\Temp\Processes.csv"
     ```

### Conclusion

These cmdlets provide a wide range of functionality for file manipulation, process management, and data handling in PowerShell. Understanding how to use these commands will greatly enhance your scripting and automation capabilities!
