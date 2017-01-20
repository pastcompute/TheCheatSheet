# git

Task | Commands / Steps | Tested
------------ | ------------- | ----
Assign ssh key to a remote | 1. Edit file `~/.ssh/config` (see below for example)<br/>2. Use the aliased hostname in the remote| Debian Jessie<sup>[1](#f1)</sup>

----

## Example files

*~/.ssh/config*

    Host github.com-alias
      Hostname github.com
      User git
      IdentityFile ~/.ssh/id_blah

