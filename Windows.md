## Basic

Task | Commands / steps | Tested
------------ | ------------- | ----
Reboot | `shutdown /r` | Windows 7

## Management

Task | Commands / steps | Tested
------------ | ------------- | ----
Activate admin account on Windows 7 Home | `net user administrator /active:yes` | Windows 7
List and check volume shadow copy usage | `vssadmin list shadowstorage`<br/>`vssadmin list shadows` | Windows 7
Delete a shadow copy | `vssadmin delete shadows /for=c: /shadow=`*ID* | Windows 7
Delete indiviual shadow copies | `wmic /interactive:on shadowcopy delete` | Windows 7
Disable system restore and delete all copies |`sc config srservice start= disabled`<br/>`Reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SystemRestore" /v DisableSR /t REG_DWORD /d 1 /f`<br/>`net stop srservice` | Windows 7
Re-enable system restore | `sc config srservice start= Auto`<br/>`net start srservice`<br/>`Reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SystemRestore" /v DisableSR /t REG_DWORD /d 0 /f` | Windows 7
