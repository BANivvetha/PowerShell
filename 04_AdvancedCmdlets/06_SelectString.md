In PowerShell, `Select-String` is a powerful cmdlet used to search for text patterns in files or strings—essentially like `grep` in Unix/Linux. Here's how to use it effectively:

---

## 📌 Basic Syntax:

```powershell
Select-String -Pattern "search_text" -Path "file_path"
```

---

## 🔍 Examples:

### 1. **Search in a File**

```powershell
Select-String -Pattern "error" -Path "C:\Logs\app.log"
```

* Finds all lines in `app.log` that contain the word "error".

### 2. **Search in Multiple Files**

```powershell
Select-String -Pattern "fail" -Path "C:\Logs\*.log"
```

* Searches for "fail" in all `.log` files in the `C:\Logs` directory.

### 3. **Use a Regex Pattern**

```powershell
Select-String -Pattern "error\d+" -Path "log.txt"
```

* Matches lines with patterns like `error1`, `error23`, etc.

### 4. **Search a String Instead of a File**

```powershell
"PowerShell is powerful" | Select-String -Pattern "power"
```

* Searches the input string for the word "power".

### 5. **Only Return the Matching Text**

```powershell
Select-String -Pattern "\d{3}-\d{2}-\d{4}" -Path "data.txt" | ForEach-Object { $_.Matches }
```

* Extracts SSN-like patterns from a file.

---

## 🧾 Key Properties of Output:

Each result from `Select-String` returns a **MatchInfo** object, with useful properties like:

* `.Line`: the full line that matched
* `.LineNumber`: line number in the file
* `.Filename`: the file name
* `.Matches`: the actual match(es)

Example:

```powershell
$results = Select-String -Pattern "error" -Path "app.log"
$results[0].Line
$results[0].LineNumber
```

---


