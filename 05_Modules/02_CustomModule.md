Creating a custom PowerShell module involves defining functions and saving them in a `.psm1` file. Here’s a step-by-step guide to creating and importing a simple custom module:

### Step 1: Create a Custom Module

1. **Open a Text Editor**: You can use any text editor, such as Notepad or Visual Studio Code.

2. **Define Your Functions**: Write your functions in the text editor. Here’s an example of a module that contains two simple functions.

   ```powershell
   # MyCustomModule.psm1

   function Get-Greeting {
       param (
           [string]$Name = "World"
       )
       "Hello, $Name!"
   }

   function Get-Square {
       param (
           [int]$Number
       )
       return $Number * $Number
   }
   ```

3. **Save the Module**: Save the file with the `.psm1` extension. For example, save it as `MyCustomModule.psm1`.

### Step 2: Create a Module Manifest (Optional)

Creating a module manifest is optional but recommended for more complex modules. It provides metadata about the module.

1. Open PowerShell.
2. Use the `New-ModuleManifest` cmdlet to create a manifest:

   ```powershell
   New-ModuleManifest -Path C:\Path\To\Your\Module\MyCustomModule.psd1 -RootModule MyCustomModule.psm1 -ModuleVersion 1.0 -Author "Your Name"
   ```

### Step 3: Import the Module

1. **Open PowerShell**: Launch PowerShell.

2. **Import the Module**: Use the `Import-Module` cmdlet to import your custom module:

   ```powershell
   Import-Module C:\Path\To\Your\Module\MyCustomModule.psm1
   ```

3. **Verify the Module is Imported**: Check if the module is loaded:

   ```powershell
   Get-Module
   ```

### Step 4: Use the Functions

Now that the module is imported, you can use the functions defined in it.

```powershell
# Call the Get-Greeting function
Get-Greeting -Name "Alice"  # Output: Hello, Alice!

# Call the Get-Square function
Get-Square -Number 5  # Output: 25
```

### Step 5: Unload the Module (Optional)

If you want to unload the module, you can use:

```powershell
Remove-Module MyCustomModule
```

### Summary

You’ve created a custom PowerShell module, imported it, and used its functions. You can expand this module by adding more functions as needed. If you have any questions or need further assistance, feel free to ask!
