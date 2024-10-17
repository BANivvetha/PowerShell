`Select-String` is a powerful cmdlet in PowerShell that searches for text patterns in files or input streams, similar to the Unix `grep` command. It supports regular expressions and provides detailed information about matches.

### Basic Syntax
```powershell
Select-String -Path <string> -Pattern <string> [-Options <string>]
```

### Common Parameters

- **-Path**: Specifies the path to the file or files to search.
- **-Pattern**: Specifies the text or regular expression pattern to search for.
- **-Recurse**: Searches recursively through all files in a directory.
- **-CaseSensitive**: Makes the search case-sensitive.
- **-SimpleMatch**: Performs a simple string match rather than a regex search.
- **-AllMatches**: Returns all matches in a single line.

### Examples

#### 1. **Search for a Pattern in a File**
```powershell
Select-String -Path "C:\Temp\example.txt" -Pattern "searchTerm"
```
This command will return all lines in `example.txt` that contain the term "searchTerm."

#### 2. **Search Recursively in All Files in a Directory**
```powershell
  Get-ChildItem -Path C:\Test\*.txt  -Recurse | Select-String -Pattern "search"
```
This command searches for "searchTerm" in all files within the `C:\Temp` directory and its subdirectories.

#### 3. **Using Regular Expressions**
```powershell
Select-String -Path "C:\Temp\example.txt" -Pattern "\d{3}-\d{2}-\d{4}"
```
This command searches for a pattern matching a Social Security Number format (e.g., 123-45-6789).

#### 4. **Display Only the Matching Lines**
```powershell
Select-String -Path "C:\Temp\example.txt" -Pattern "searchTerm" | ForEach-Object { $_.Line }
```
This command extracts only the matching lines from the output.

#### 5. **Count Matches**
You can count the number of matches by piping the output to `Measure-Object`:
```powershell
Select-String -Path "C:\Temp\example.txt" -Pattern "searchTerm" | Measure-Object | Select-Object -ExpandProperty Count
```

#### 6. **Case-Sensitive Search**
```powershell
Select-String -Path "C:\Temp\example.txt" -Pattern "searchTerm" -CaseSensitive
```
This command performs a case-sensitive search for "searchTerm."

#### 7. **Finding Multiple Patterns**
```powershell
Select-String -Path "C:\Temp\example.txt" -Pattern "term1", "term2"
```
This command searches for both "term1" and "term2" in the specified file.

### Conclusion

`Select-String` is an essential cmdlet for searching through text data in PowerShell. Whether you're looking for specific strings or patterns, it provides a flexible and powerful way to perform searches efficiently.
