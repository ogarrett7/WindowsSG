## Table of Contents 
1. reg commands
2. PowerShell cmdlets for registry
3. navigate regedit.exe
4. navigate gpedit.msc

### 1. reg commands

Users can perform a variety of tasks, including creating, deleting, and modifying registry keys and values. This is particularly useful for batch operations or automated scripts.

Common Commands:

|Command               |          Description                |
|:------------------------------------------|:-----------------------------------------------------------------------------|
|`reg query`    |   Retrieve registry data from specified keys or values.      |
|`reg add`    |      Add a new registry key or value.      |
|`reg delete`    |    Delete a specified registry key or value.      |
|`reg export` and `reg import`    |    Backup and restore registry data from a file.      |


### 2. PowerShell cmdlets for registry

With cmdlets like `Get-Item`, `Set-Item`, and `Remove-Item`, users can interact with registry keys and values programmatically, providing more flexibility than traditional tools.

Common Cmdlets:

|Command               |          Description                |  Example
|:------------------------------------------|:-----------------------------------------|:------------------------------------|
|`Get-ItemProperty`    |    Retrieve registry values from specified registry keys.    |Example: Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name DevicePath    |
|`Set-ItemProperty`    |Modify existing registry values.    |    Example: Set-ItemProperty -Path "C:\temp\mytestfile.txt" -Name IsReadOnly -Value $true    |
|`New-Item`    |    Create new registry keys.    |     Example: New-Item -Path "HKCU:\Software\MyNewApplication"    |
|`Remove-Item`     |   Delete specified registry keys.    |    Example: Remove-Item -Path C:\Path\To\Your\File.txt    |

### 3. Navigate regedit.exe

This graphical interface is built into Windows, providing a user-friendly way to navigate the complex structure of the Windows Registry.

A good way to think of the registry is to compare it to a grocery store. If you have a list of ingredients you need for a recipe you go to the grocery store. If a computer needs to complete a task it goes to the registry for the configuration files it needs. The aisles in the grocery store can be compared to the keys/folders in the registry and the actual ingredients are the configuration files. 

Task:

Open regedit.exe 
Navigate to the folder that is read everytime the system starts, where some malicious files are often hidden. Note this path as it is one you will likely use a lot. Some PE questions will come from this location.

### 4. Navigate Group Policy Editor (gpedit.msc)

 System administrators can enforce settings across multiple machines within a network, ensuring compliance with organizational policies.

Open gpedit.msc
Note some differences between the Computer Configuration folder and User Configuration folder. A folder that they both have in common is the Administrative Templates. In this foler you can see all of the available policies. It is important to note that we cannot create new policies here, we can only edit the ones that already exist in Windows. If you want to create new group policies, you will need to use the Group Policy Management GUI in your Active Directory (AD box). 
Open the Group Policy Management GUI.
Note the domain you are a part of. Inside of this domain is where you can set group policies for your domain users. 

