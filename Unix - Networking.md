## Apache Web Server Tasks

### Serve a directory (simple)

*Tested on Debian Jessie*

** Goal: serve directory as URL `http://example.com/SomePath` unrestricted with traversal of symbolic links, disabled `.htaccess` **

0. Assumes default configuration from `apache2` package installation
1. Create a file `/etc/apache2/sites-available/somefile`
2. Add the following:

        <Directory /path/to/filesystem/directory/>
        Options Indexes FollowSymLinks
        AllowOverride None
        Require all granted
        </Directory>
        Alias "/SomePath" "/path/to/filesystem/directory/"```
3. Run commands:

        a2ensite somefile
        service apache2 reload

### Samba (Windows Networking) Tasks

*Tested on Debian Jessie*

** Goal: serve directory as //SOMEHOST/Share with anonymous guest read browse access **

0. Assumes default configuration from `samba` package installation
1. Edit the file /etc/samba/smb.conf
2. Set section `[global]` entry `workgroup`
3. Add new section:

        [Share]
        path = /path/to/filesystem/directory
        browseable = yes
        read only = yes
        guest ok = yes
        force user = nobody

4. Run commands:

        service samba reload
