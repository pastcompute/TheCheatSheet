
Task | Commands / steps
------------ | -------------
Activate admin account on Windows 7 Home | `net user administrator /active:yes`
Check volume shadow copy usage and list snapshots | `vssadmin list shadowstorage`<br/>`vssadmin list shadows`
Delete a shadow copy (restore point) | `vssadmin delete shadows /for=c: /shadow=`**ID**&#07;` `
