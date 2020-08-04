# Installing Odoo 13 on Ubuntu 18.04

Settings > Softwares and Updates > Ubuntu Software: Download From: Server for United States
```
$ sudo apt-get update
```

Run "Software Updater"
```
$ sudo apt-get install git
```

User creation:
```
$ apt-get update && apt-get upgrade # Install system updates
$ apt-get install sudo # Make sure 'sudo' is installed
```

The next set of commands will create an odoo user:
```
$ sudo useradd -m -g sudo -s /bin/bash odoo # Create an 'odoo' user with sudo powers
$ sudo passwd odoo # Ask and set a password for the new user
```

Now we can log in as the new user and set up Odoo.
```
$ whoami
odoo
$ echo $HOME
/home/odoo
```

Install PostgreSQL Server
```
$ sudo apt-get install postgresql -y
```

Create Database user for Odoo
```
$ sudo su postgres
$ cd
$ createuser -s odoo
$ exit
$
$ sudo -u postgres psql
```

Show roles and databases in PostgreSQL
```
postgres=# SELECT rolname FROM pg_roles;
postgres=# \l
```

Change postgres user default password
```
postgres=# \password
Enter new password: postgres
Enter it again:postgres
```