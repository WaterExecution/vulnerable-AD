<h1 align="center">
  Vulnerable-AD
  <br>
</h1>

Create a vulnerable active directory that's allowing you to test most of active directory attacks in local lab

### Main Features
- Randomize Attacks
- Full Coverage of the mentioned attacks
- you need run the script in DC with Active Directory installed 
- Some of attacks require client workstation
  
### Supported Attacks
- Abusing ACLs/ACEs
- Kerberoasting
- AS-REP Roasting
- Abuse DnsAdmins (...)
- Password in AD User comment
- Password Spraying
- DCSync (...)
- Silver Ticket (...)
- Golden Ticket (...)
- Pass-the-Hash (...)
- Pass-the-Ticket (...)
- SMB Signing Disabled
- Bad WinRM permission
- Anonymous LDAP query
- Public SMB Share
- Zerologon (Check version)

### Improved QOL
- "Fixed" Randomizer
- Password is crackable... within a few days
- Multiple ways to PWN

### Example
```powershell
# if you didn't install Active Directory yet , you can try 
Install-ADDSForest -CreateDnsDelegation:$false -DatabasePath "C:\\Windows\\NTDS" -DomainMode "7" -DomainName "change.me" -DomainNetbiosName "change" -ForestMode "7" -InstallDns:$true -LogPath "C:\\Windows\\NTDS" -NoRebootOnCompletion:$false -SysvolPath "C:\\Windows\\SYSVOL" -Force:$true
# if you already installed Active Directory, just run the script !
 Import-Module .\vulnadplus.ps1;Invoke-VulnAD -UsersLimit 100 -DomainName "change.me"
```
