To change XAMPP's default localhost directory from htdocs to htdocs/www, follow these steps:
Step 1: Open Apache Configuration

    Open XAMPP Control Panel.
    Click Config next to Apache.
    Select httpd.conf.

Step 2: Modify Document Root

    Find the following lines (usually around line 250):

DocumentRoot "C:/xampp/htdocs"
<Directory "C:/xampp/htdocs">

Change them to:

    DocumentRoot "C:/xampp/htdocs/www"
    <Directory "C:/xampp/htdocs/www">

    Save and close the file.

Step 3: Update VirtualHost (Optional, for better management)

    Open httpd-vhosts.conf:
        Click Config in XAMPP (next to Apache).
        Open httpd-vhosts.conf (found in C:/xampp/apache/conf/extra/).
    Add the following:

    <VirtualHost *:80>
        DocumentRoot "C:/xampp/htdocs/www"
        ServerName localhost
        <Directory "C:/xampp/htdocs/www">
            AllowOverride All
            Require all granted
        </Directory>
    </VirtualHost>

    Save and close the file.

Step 4: Restart Apache

    In the XAMPP Control Panel, stop Apache and then start it again.

Now, when you visit http://localhost, it should point to C:/xampp/htdocs/www
