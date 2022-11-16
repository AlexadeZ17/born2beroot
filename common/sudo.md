# Sudo

After installing the virtual machine with Virtual Box and opening it, what I did is install sudo, a utility from linux that allows us to execute programs or edit files with other user's permission. In fact, it stands for "substitute user do". It is widely used to make root that substitute and thus, we can also interpret it as "super user do". 🦸

The installation process it's quite simple, since we only have to execute the following command as root:
```shell
apt install sudo
```
It's a good moment now to mention one of the things the project subject asks for, and it's understanding evey command that we execute, so here is a little explanation of what happened here:

#### APT vs apt vs aptitude

- **APT** stands for _Advanced Packaging Tool_. It was introduced by debian as a tool to install packages on our system. It is a low level command-line tool for searching and managing packages 📦.

- **aptitude** is also used to manage packages. This one has a Text-Based user interface 👾 and can emulate most functionalities from **APT**, but it improves them at some point by giving a common tool to install packages, show versions and also look for them, since it implements a good search syntax. More info can be found on debian's [aptitude](https://wiki.debian.org/Aptitude) wiki 📑.

- **apt** is quite the same as aptitude, with the main difference being that it does not provide a user interface ❎ and the only way to interact with it is through the command line. More info can be found on debian's [apt](https://wiki.debian.org/AptCLI) wiki 📑.

We are using **apt** since we don't need all the functionalities that aptitude offers, and also since **apt** is the deffault package manager, we will be using that one.
It takes two arguments: 
1. The first one is the action we want to do, in this case install a package
2. The second one is the name of the package. Since we are installing ``sudo`` we write **sudo**
After typing that and hittin enter, it will start installing ``sudo``

Once it is installed we can start using it without using root's account and simply putting ```sudo``` before the command to execute it as super user.


