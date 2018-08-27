# Package managers

```
Brief (to be removed)

apt-get (for Debian)
yum (for Fedora)
brew (for mac)
```
Every Linux distro comes with its own package management system, which is a program that allows you to download other programs off the Internet through the command line. This is incredibly important for installing 3rd party software on your Linux computer, for example OpenOffice, vim, or git. All software is verified securely before being put on any package management systems, which is one of the reasons why Linux is such a secure operating system in general.

The default package manager for most Debian-based distros (Ubuntu included) is `apt-get`. For Fedora-based distros (for example centOS) the default package manager is `yum`.

Installing a program with either of these is easy. Type:

```
sudo apt-get install <package>
```
or 
```
sudo yum install <package>
```
to install the necessary package. If you need to install a program on Linux, 99% of the time it will be available on the default package manager.

See `man apt-get` or `man yum` for more commands, including how to update and delete packages.
