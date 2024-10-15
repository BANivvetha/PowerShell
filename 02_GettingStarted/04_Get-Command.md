The `Get-Command` cmdlet in PowerShell is used to retrieve all cmdlets, functions, aliases, and scripts available in the current session. It helps you discover what commands are available to you. Here’s a detailed look at how to use `Get-Command` along with examples.

### Overview of Get-Command

- **Purpose**: To list available commands in PowerShell.
- **Syntax**:
  ```powershell
  Get-Command [-Name <string>] [-Type <string>] [-Module <string>] [-Verb <string>] [-Noun <string>]
  ```

### Key Parameters

1. **-Name**: Filters the results based on the command name or part of the name.
2. **-Type**: Specifies the type of command (e.g., `Cmdlet`, `Function`, `Alias`, `Script`).
3. **-Module**: Filters results based on the specified module name.
4. **-Verb**: Filters by the verb part of the command name (e.g., `Get`, `Set`).
5. **-Noun**: Filters by the noun part of the command name.

### Basic Usage Examples

#### 1. Get All Commands
To retrieve all available commands in the current session:
```powershell
Get-Command
```

#### 2. Get Cmdlets Only
To list only cmdlets:
```powershell
Get-Command -Type Cmdlet
```

#### 3. Filter by Command Name
To find commands that include "Process":
```powershell
Get-Command -Name *Process*
```

#### 4. Get Functions Only
To list all functions defined in the current session:
```powershell
Get-Command -Type Function
```

#### 5. Filter by Module
To get commands from a specific module (e.g., `Microsoft.PowerShell.Management`):
```powershell
Get-Command -Module Microsoft.PowerShell.Management
```

#### 6. Filter by Verb
To list commands that use the verb "Get":
```powershell
Get-Command -Verb Get
```

#### 7. Filter by Noun
To list commands that use the noun "Service":
```powershell
Get-Command -Noun Service
```

#### 8. Get Aliases
To retrieve all aliases in the current session:
```powershell
Get-Command -Type Alias
```

#### 9. Get Details for a Specific Command
To get detailed information about a specific command (e.g., `Get-Process`):
```powershell
Get-Command Get-Process
```

### Conclusion

The `Get-Command` cmdlet is a powerful tool for discovering available commands in PowerShell. By using its filtering options, you can quickly find the specific cmdlets, functions, or scripts you need, making your PowerShell experience more efficient and productive.
