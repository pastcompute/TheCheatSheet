## Apache Web Server Tasks

### Serve a directory (simple)

*Tested on Debian Jessie*

0. Serve as URL `http://example.com/SomePath` unrestricted with traversal of symbolic links, disabled `.htaccess`
1. Create a file `/etc/apache2/sites-available/somefile`
2. Add the following
```
<Directory /path/to/filesystem/directory/>
        Options Indexes FollowSymLinks
        AllowOverride None
        Require all granted
</Directory>
Alias "/SomePath" "/path/to/filesystem/directory/"
```
