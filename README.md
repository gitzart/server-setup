# server-setup
An Amazon ec2 server with Apache web server to host Flask apps

# IP Address
* IP - 34.204.77.34
* DNS - [http://ec2-34-204-77-34.compute-1.amazonaws.com/](http://ec2-34-204-77-34.compute-1.amazonaws.com/)

# Installed Software
* apache2
* postgresql
* libapache2-mod-wsgi-py3
* pip3

And all the software defined in [requirements.txt](https://github.com/gitzart/catalog/blob/master/requirements.txt) of the [catalog](https://github.com/gitzart/catalog) app.

# Configurations
### SSH
* SSH listens on port `2200`
* Password based remote access is disabled.
* Special folder `.ssh` and special file `authorized_keys` are created and given proper permissions.

### Access
* `root` user access is disabled.
* New `sudo-enabled user` is added with SSH remote access.

### Firewall
* Default SSH port is changed to `2200` from `22`
* Only `SSH, WWW, NTP` ports are enabled.

### Repository
* [Catalog](https://github.com/gitzart/catalog) app hosted on this server is placed in

```
$ cd ~/repos/catalog
```

### Virtual Host File
* Server configuration of [catalog](https://github.com/gitzart/catalog) app is defined in the default file.

```
$ sudo cat /etc/apache2/sites-enabled/000-default.conf
```

### Database
* Postgresql is installed and new `non-superuser user` and new `database with utf-8 encoding` are created for [catalog](https://github.com/gitzart/catalog) app.
* Only `localhost` connection is allowed.

### Timezone
* UTC is set as the default timezone.
