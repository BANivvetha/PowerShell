PowerShell provides a variety of cmdlets for performing file operations. Here’s a list of common file-related cmdlets along with examples for each operation:

### Common File Operations Cmdlets

#### 1. **New-Item**
   - **Description**: Creates a new file.
   - **Example**:
     ```powershell
     New-Item -Path "C:\Temp\example.txt" -ItemType File
     ```

#### 2. **Remove-Item**
   - **Description**: Deletes a specified file.
   - **Example**:
     ```powershell
     Remove-Item -Path "C:\Temp\example.txt"
     ```

#### 3. **Copy-Item**
   - **Description**: Copies a file to a new location.
   - **Example**:
     ```powershell
     Copy-Item -Path "C:\Temp\example.txt" -Destination "C:\Temp\Backup\example.txt"
     ```

#### 4. **Move-Item**
   - **Description**: Moves a file to a new location.
   - **Example**:
     ```powershell
     Move-Item -Path "C:\Temp\example.txt" -Destination "C:\Temp\Archived\example.txt"
     ```

#### 5. **Get-Content**
   - **Description**: Reads the content of a file.
   - **Example**:
     ```powershell
     Get-Content -Path "C:\Temp\example.txt"
     ```

#### 6. **Set-Content**
   - **Description**: Writes or replaces the content in a file.
   - **Example**:
     ```powershell
     Set-Content -Path "C:\Temp\example.txt" -Value "This is new content."
     ```

#### 7. **Add-Content**
   - **Description**: Appends content to a file.
   - **Example**:
     ```powershell
     Add-Content -Path "C:\Temp\example.txt" -Value "This content is appended."
     ```

#### 8. **Clear-Content**
   - **Description**: Clears the content of a file without deleting it.
   - **Example**:
     ```powershell
     Clear-Content -Path "C:\Temp\example.txt"
     ```

#### 9. **Test-Path**
   - **Description**: Checks if a specified file exists.
   - **Example**:
     ```powershell
     Test-Path -Path "C:\Temp\example.txt"
     ```

#### 10. **Get-Item**
   - **Description**: Retrieves information about a specific file.
   - **Example**:
     ```powershell
     Get-Item -Path "C:\Temp\example.txt"
     ```

#### 11. **Get-ChildItem**
   - **Description**: Lists all files in a specified directory.
   - **Example**:
     ```powershell
     Get-ChildItem -Path "C:\Temp"
     ```

#### 12. **Export-Csv**
   - **Description**: Exports data to a CSV file (often used with data from other cmdlets).
   - **Example**:
     ```powershell
     Get-Process | Export-Csv -Path "C:\Temp\Processes.csv" -NoTypeInformation
     ```

#### 13. **Import-Csv**
   - **Description**: Imports data from a CSV file into PowerShell.
   - **Example**:
     ```powershell
     $data = Import-Csv -Path "C:\Temp\Processes.csv"
     ```

### Conclusion

These cmdlets facilitate a range of file operations in PowerShell, from creating and deleting files to reading and writing content. Understanding and using these commands will enhance your ability to automate file management tasks efficiently!
