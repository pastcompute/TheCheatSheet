# General

Task | Commands / Steps | Tested
------------ | ------------- | ----
Rotate a PDF | `pdftk 12111601.PDF cat 1-endsouth output 2.pdf` | Debian Jessie<sup>[1](#f1)</sup>
Manually check sysctl.d/ file | Run `sysctl -p /etc/sysctl.d/99-somefile`
Syntax error in sysctl.d/ file | There are no single or double quotes, spaces in line are spaces! Unlike the command line version
Sysctl network settings not working | UFW can interfere. Change setting in /etc/default/ufw as per http://serverfault.com/a/418038
Change MTU on a network manager connection|`nmcli con modify  'Wired connection 1' 802-3-ethernet.mtu 140 ; nmcli con reload`



# Debian

Task | Commands / Steps | Tested
------------ | ------------- | ----
Prepare an amd64 debian for i386 packages | `dpkg --add-architecture i386`<br/>`apt-get update`<br/>`apt-get install lsb` | Debian Jessie
Prepare i386 system from amd64 | `fakeroot  /usr/sbin/debootstrap --foreign --verbose --arch i386 stable target-dir http://path/to/pub/debian`<br/>`FIXME stage 2` | Debian Jessie




--

<a name="f1"><sup>(1)</sup></a> Prerequisite: ```apt-get install pdftk```
