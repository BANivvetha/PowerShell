In PowerShell, Active Directory (AD) cmdlets that use the "Get" verb are essential for retrieving information about various AD objects, such as users, groups, computers, and organizational units. Here’s a list of common "Get" AD cmdlets along with examples of how to use them:

### Common "Get" AD Cmdlets

#### 1. **Get-ADUser**
   - **Description**: Retrieves information about user accounts in Active Directory.
   - **Example**:
     ```powershell
     Get-ADUser -Identity "jdoe"
     ```

#### 2. **Get-ADGroup**
   - **Description**: Retrieves information about Active Directory groups.
   - **Example**:
     ```powershell
     Get-ADGroup -Identity "HR Managers"
     ```

#### 3. **Get-ADComputer**
   - **Description**: Retrieves information about computer accounts in Active Directory.
   - **Example**:
     ```powershell
     Get-ADComputer -Identity "Computer01"
     ```

#### 4. **Get-ADOrganizationalUnit**
   - **Description**: Retrieves information about organizational units (OUs) in Active Directory.
   - **Example**:
     ```powershell
     Get-ADOrganizationalUnit -Identity "OU=Sales,DC=example,DC=com"
     ```

#### 5. **Get-ADGroupMember**
   - **Description**: Retrieves the members of an Active Directory group.
   - **Example**:
     ```powershell
     Get-ADGroupMember -Identity "HR Managers"
     ```

#### 6. **Get-ADUser -Filter**
   - **Description**: Retrieves all user accounts that match a specific filter.
   - **Example**:
     ```powershell
     Get-ADUser -Filter { Department -eq "Sales" }
     ```

#### 7. **Get-ADComputer -Filter**
   - **Description**: Retrieves all computer accounts that match a specific filter.
   - **Example**:
     ```powershell
     Get-ADComputer -Filter { OperatingSystem -like "*Windows 10*" }
     ```

#### 8. **Get-ADDomain**
   - **Description**: Retrieves information about the Active Directory domain.
   - **Example**:
     ```powershell
     Get-ADDomain
     ```

#### 9. **Get-ADForest**
   - **Description**: Retrieves information about the Active Directory forest.
   - **Example**:
     ```powershell
     Get-ADForest
     ```

#### 10. **Get-ADReplicationPartner**
   - **Description**: Retrieves replication partner information for domain controllers.
   - **Example**:
     ```powershell
     Get-ADReplicationPartner -Identity "DC01"
     ```

### Conclusion

These "Get" cmdlets are crucial for querying and retrieving information from Active Directory. Mastering them will significantly enhance your ability to manage and automate tasks related to user accounts, groups, and other AD objects!
