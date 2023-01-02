# Examples 

### Get-Help (Find the help of a domain)

The Get-Help cmdlet displays information about PowerShell concepts and commands, including cmdlets, functions, Common Information Model (CIM) commands, workflows, providers, aliases, and scripts.
```powershell
   Get-Help Get-Service
   Get-Help -Name Get-Service
   Get-Service -?
```
### help/man command (Display basic information Pagewise)
```powershell
   help Get-Service
   man Get-Service
```
### Get-help with Detailed(displays parameters,description etc) and Full (displays parameter description, description etc) options
```powershell
Get-Help Get-service -Detailed
Get-Help Get-service -Full
```
### Displays the selected part using Parameter
```powershell
 Get-Help Get-service -Examples
 Get-Help Get-service -Parameter *
 Get-Help Get-service -Parameter InputObject
```
The <b>Examples</b> parameter displays the help file's NAME and SYNOPSIS sections, and all the Examples. You can't specify an Example number because the Examples parameter is a switch parameter.

The <b>Parameter</b> parameter displays only the descriptions of the specified parameters. If you specify only the <b>asterisk (*)</b> wildcard character, it displays the descriptions of all parameters. When Parameter specifies a parameter name such as <b>InputObject</b>, information about that parameter is shown.

### Get-Help with online option(to open help online on default browser)
```powershell
Get-Help Get-service -Online
```
### Get-Help for all topics or topics which contains a word or character
```powershell
Get-Help *
Get-Help *service*
```
### Get-Help for conceptual articles
```powershell
Get-Help about_*
Get-Help about_Mocking
```
### Update-Help (to update help files)
```powershell
 update-help
```
