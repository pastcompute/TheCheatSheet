
Task | Commands / steps
------------ | -------------
Activate admin account on Windows 7 Home | `net user administrator /active:yes`
Check volume shadow copy usage and list snapshots | `vssadmin list shadowstorage`<br/>`vssadmin list shadows`
Delete a shadow copy (restore point) | `vssadmin delete shadows /for=c: /shadow=`**ID**&#07;` `
Disable system restore and delete all copies |`sc config srservice start= disabled`<br/>`Reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SystemRestore" /v DisableSR /t REG_DWORD /d 1 /f`<br/>`net stop srservice`
Re-enable system restore | `sc config srservice start= Auto`<br/>`net start srservice`<br/>`Reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SystemRestore" /v DisableSR /t REG_DWORD /d 0 /f`
