PowerShell provides several cmdlets for managing folders (directories) effectively. Here’s a list of commonly used folder-related cmdlets along with examples:

### Common Folder-Related Cmdlets

#### 1. **New-Item**
   - **Description**: Creates a new folder.
   - **Example**:
     ```powershell
     New-Item -Path "C:\Temp\NewFolder" -ItemType Directory
     ```

#### 2. **Remove-Item**
   - **Description**: Deletes a folder. Use `-Recurse` to delete a folder and its contents.
   - **Example**:
     ```powershell
     Remove-Item -Path "C:\Temp\OldFolder" -Recurse
     ```

#### 3. **Copy-Item**
   - **Description**: Copies a folder and its contents to a new location.
   - **Example**:
     ```powershell
     Copy-Item -Path "C:\Temp\SourceFolder" -Destination "C:\Temp\BackupFolder" -Recurse
     ```

#### 4. **Move-Item**
   - **Description**: Moves a folder and its contents to a new location.
   - **Example**:
     ```powershell
     Move-Item -Path "C:\Temp\OldFolder" -Destination "C:\Temp\NewLocation"
     ```

#### 5. **Get-ChildItem**
   - **Description**: Lists all files and folders in a specified directory.
   - **Example**:
     ```powershell
     Get-ChildItem -Path "C:\Temp"
     ```

#### 6. **Set-Location**
   - **Description**: Changes the current working directory to a specified folder.
   - **Example**:
     ```powershell
     Set-Location -Path "C:\Temp"
     ```

#### 7. **Test-Path**
   - **Description**: Checks if a specified folder exists.
   - **Example**:
     ```powershell
     Test-Path -Path "C:\Temp\MyFolder"
     ```

#### 8. **Clear-Item**
   - **Description**: Deletes all files and subfolders within a specified folder without deleting the folder itself.
   - **Example**:
     ```powershell
     Clear-Item -Path "C:\Temp\MyFolder\*" -Recurse
     ```

#### 9. **Get-Item**
   - **Description**: Retrieves information about a specific folder.
   - **Example**:
     ```powershell
     Get-Item -Path "C:\Temp\MyFolder"
     ```

#### 10. **Remove-Item -Force**
   - **Description**: Forces the deletion of a folder without prompting for confirmation.
   - **Example**:
     ```powershell
     Remove-Item -Path "C:\Temp\UnwantedFolder" -Recurse -Force
     ```

### Conclusion

These cmdlets allow you to create, delete, move, and manage folders and their contents in PowerShell effectively. Familiarizing yourself with these commands will significantly enhance your ability to automate file system management tasks!
