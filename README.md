# born2beroot 🐧

This project, part of Rank 01 of 42's common core consists on creating our very first web server from scratch, with no graphical envirnment.

The requirements of the project are the following:

- No graphical environment
- Only port 4242 is open, with service SSH and with UFW Firewall activated to only allow connections to that port
- Root SSH connection is not enabled
- A strong password Policy must be implemented
- Create a cronjob that runs a script that shows relevant information about our computer

As a bonus, we also had to:

- Implement wordpress with MariaDB, PHP and ligthttp
- Implement another service, exluding nginx and Apache2

The way the project was evaluated was by answering questions from evaluators in order to asses our understanding of the exercice and the solution. This repo will serve as a manual where I'll be explaining step by step what I did to succesfully pass this project

## Manual

### Common Part

After installing the virtual machine with Virtual Box and opening it, what I did is install sudo, a utility from linux that allows us to execute programs or edit files with other user's permission. In fact, it stands for "substitute user do". It is widely used to make root that substitute and thus, we can also interpret it as "super user do". 🦸

The installation process it's quite simple, since we only have to execute the following command as root:
```shell
apt install sudo
```
Once it is installed we can start using it without using root's account and simply putting ```sudo``` before the command to execute it as super user
