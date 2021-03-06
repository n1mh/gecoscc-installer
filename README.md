# gecoscc-installer

This script installs and configure [__GECOS Control Center__](https://gecos-team.github.io). At the end of this process you will have a complete and modern solution for corporate workstation management.

## Minimum requirements

In order to get __GECOS Control Center__ installed, your server must have:

* 64-bits architecture
* 4 GB of RAM memory on Red Hat servers and 2 GB on CentOS
* 5 GB of free disk space in `/opt`
* An FQDN
* Internet access

This installer has been tested in [CentOS](https://centos.org) 6.x minimal (64bits) and [Red Hat Enterprise Linux](https://redhat.com) 6.x 64bits (base install). In case your operating system is Red Hat, you should have your suscription updated.

## Installation instructions

![Installer Screenshot](./gecoscc-installer-01.png)

1. From your `root` account (or some other user with privileges), download the installer from [`http://bit.ly/gecoscc-installer`](http://bit.ly/gecoscc-installer).
~~~
curl -L http://bit.ly/gecoscc-installer > gecoscc-installer.sh
~~~

2. Edit the installer and change the variables `ORGANIZATION_NAME`, `ADMIN_USER_NAME` and `ADMIN_EMAIL`.
~~~
ORGANIZATION="Your Organization"
ADMIN_USER_NAME="superuser"
ADMIN_EMAIL="gecos@guadalinex.org"
~~~

3. Run the installer.
~~~
bash gecoscc-installer.sh
~~~

4. You have to install all the components in the menu, in the order specified:
	1. CHEF
	2. MONGODB
	3. NGINX
	4. CC

 Please, note that after installing every piece of software, `gecoscc-installer.sh` will exit to the command line and you will have to run the script again.

5. After installing __GECOS Control Center__ you should restart the server:
~~~
shutdown -r now 'restarting after install gecosCC'
~~~

## Configuration

1. Run the installer again, create an administrator user (`USER` option in the menu) and make it superuser (`SET_SUPERUSER` in the menu).
~~~
bash gecoscc-installer.sh
~~~

2. Select `USER` to create your first superuser but remember that you can create more admins from the web interface. This command will show some messages with important data like your superadmin password. Do not forget to write them down!

3. Now you should be able to log in into your brand new __GECOS Control Center__, using your favorite web browser. Just point it to your server's name or IP address.

## Catalogues

Once you reach into your Control Center you may populate your system installing policies, printers and packages. This catalogues are optional but it is strongly recommended to install at least a policies catalogue for a better user experience.

Run the installer, once more.
~~~
bash gecoscc-installer.sh
~~~

Execute the options that feed the system with:
1. `POLICIES`. It will download and install last version of workstation policies.
2. `PRINTERS`. It will download and install a catalogue with +4000 printer models.
3. `PACKAGES`. It will download and install a huge catalogue of software to install in your workstations.

You can repeat these steps as many times as you need in order to keep your __GECOS Control Center__ updated.


## Logging in

![Installer Screenshot](./gecoscc-installer-02.png)

Just point your web browser to your server's IP address and log in with your superuser information.
