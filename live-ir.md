# Useful commands in Live Incident Response
## 1. System Information
### CMD
```cmd
winver
systeminfo
wmic os get <property>
```
### PowerShell
```powershell
Get-ComputerInfo
```

## 2. Environment Variables
### CMD
```cmd
set
reg query "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\Environment"
reg query "HKEY_CURRENT_USER\Environment"
```

## 3. Hotfixes
### CMD
```cmd
systeminfo | findstr KB
wmic qfe list
```
### PowerShell
```powershell
Get-HotFix
```

## 4. Drivers
### CMD
```cmd
driverquery
```
### PowerShell
```powershell
Get-WmiObject Win32_PnpSignedDriver
Get-WmiObject Win32_PnpSignedDriver | select DeviceName, DriverVersion
```
### GUI
- [NirSoft-InstalledDriversList](https://www.nirsoft.net/utils/installed_drivers_list.html)


## 5. Shadow Copies
### CMD
```cmd
wmic path Win32_ShadowCopy get DeviceObject, InstallDate
vssadmin list shadows
```
### GUI
- [NirSoft-ShadowCopyView](https://www.nirsoft.net/utils/shadow_copy_view.html)


## 6. Users and Groups
### Local Users and Groups
#### CMD
```cmd
net users
net user <username>
net localgroup
net localgroup <groupname>
```
### Domain Users and Groups
#### CMD
```cmd
net users /DOMAIN
net user <username> /DOMAIN
net localgroup /DOMAIN
net localgroup <groupname> /DOMAIN
net group /DOMAIN
net group <groupname> /DOMAIN
```





