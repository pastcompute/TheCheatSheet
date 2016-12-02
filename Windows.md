## Simple tasks

Task | Commands / steps | Tested
------------ | ------------- | ----
Reboot | `shutdown /r` | Windows 7
Run administrator command prompt| 1. right click on All Programs > Accessories > Command Prompt <br/>2. select Run as administrator | Windows 7

## System Management

Task | Commands / steps | Tested
------------ | ------------- | ----
Activate admin account on Windows 7 Home | `net user administrator /active:yes` | Windows 7
List and check volume shadow copy usage | `vssadmin list shadowstorage`<br/>`vssadmin list shadows` | Windows 7
Delete a shadow copy | `vssadmin delete shadows /for=c: /shadow=`*ID* | Windows 7
Delete indiviual shadow copies | `wmic /interactive:on shadowcopy delete` | Windows 7
Disable system restore and delete all copies |`sc config srservice start= disabled`<br/>`Reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SystemRestore" /v DisableSR /t REG_DWORD /d 1 /f`<br/>`net stop srservice` | Windows 7
Re-enable system restore | `sc config srservice start= Auto`<br/>`net start srservice`<br/>`Reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SystemRestore" /v DisableSR /t REG_DWORD /d 0 /f` | Windows 7

## Networking

Task | Commands / steps | Tested
------------ | ------------- | ----
Change MTU value | 1. Open Administrator command prompt<br/>2. Type the command netsh and wait for prompt<br/>3. Type the command interface and wait for prompt<br/>4. Type the command ipv4 and wait for prompt<br/>5. Type the command set subinterface "Local Area Connection" mtu=xxxx store=persistent | Windows 10

## Cygwin

Task | Commands / steps | Tested
------------ | ------------- | ----
Reset permissions where Cygwin mucked something up | `icacls "some_dir" /q /c /t /reset` | Windows 7
Use rsync from Cygwin without breaking things | `rsync -rlt -v from/ to/`<br/>*recursive, times, links only.*</br>*-a === -rlptgoD  + permissions group owner devices specials*
