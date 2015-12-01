/*
Title: Shared Local Windows Admin Password
Description: Search engine meta data about the finding
*/

- LAST UPDATED DATE: 2015/11/25
- LAST UPDATED BY: @mubix

## Summary

A local Windows Administrator account shares a password with one or more other accounts on another computer. 

## Capabilities and Risk

- Lateral code execution and access to all systems with same local admin password

## Detection

Once an admin password (or its hash) is discovered, it can be tried on other computers.
?? Other than dumping hashes and trying it out yourself, I'm lost on this one

## Remediation

Local Administrator accounts on different computers should not use the same password. The following recommendations can be used to help reduce or eliminate the risk.
- Use Microsoft's LAPS or alternative local account randomization tool to randomize the local account passwords.
- Disable the local Administrator (RID 500) account. Or simply do not enable the account as it has been disabled by default since Windows Vista 
- Enable LocalAccountTokenFilterPolicy registry key as detailed in the references


## References

- Pass the Hash: https://en.wikipedia.org/wiki/Pass_the_hash
- Microsoft LAPS: https://www.microsoft.com/en-us/download/details.aspx?id=46899

## Exploitation

There are two methos of exploiting common passwords: remote authentication attempts and passing the hash.

### Remote Authentication Attempts

If a local administrator password is obtained, it can be used to query remote services running on other systems. Common services include Remote Desktop, administrative shares, Windows Management Instermentation (WMI), ...

### Dumping hashes from exploited machine then using the hash to access other machines on the network
If a local administrator password hash is obtained, it can be tried on remote computers through pass the hash techniques.
```
```
