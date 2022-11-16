# SSH

SSH stands for "Secur Shell", and it's a way to communicate to a computer remotely through an encrypted shell. It usually opperates on port 22, but this assignment requires us to configure it on port 4242.

The SSH server I'll be using is OpenSSH, which is pre-installed on the Debian Image I chose.

Executing ``sudo service ssh status`` reveals information about the server, including in which port it's running 

<img src="https://raw.githubusercontent.com/AlexadeZ17/born2beroot/main/img/Screen%20Shot%202022-11-16%20at%203.54.33%20PM.png?token=GHSAT0AAAAAAB26ALHPVWX3OUWUVTVQMW6EY3U7JHA">

As we can see, SSH is running on port 22, so we need to change it. I order to do so, we will have to edit two files: ``/etc/ssh/ssh_config`` and ``/etc/ssh/sshd_config``

I will first edit ``/etc/ssh/ssh_config``. Since ``vim`` is not installed, I'll be using ``nano``

We have to look for the line that says ``#Port 22`` and change it to ``Port 4242``

<img src="https://raw.githubusercontent.com/AlexadeZ17/born2beroot/main/img/Screen%20Shot%202022-11-16%20at%204.01.29%20PM.png?token=GHSAT0AAAAAAB26ALHOUHOY2DNVAH5JS37QY3U7P3Q">

Once we've done that, we proceed to make those changes on ``etc/ssh/sshd_config``, where we will also look for the line that says ``#Port 22`` and replace it for ``Port 4242``. In this file we also have to change the authentication permissions so that ``root`` can't be access through SSH. To do that, I will change the line ``#PermitRootLogin prohibit-password``, which means that root can't be authenticatet with a password or any keyboard-interactive mean into ``PermitRootLogin no`` which means that root cannot be access through SSH by any means.

<img src="https://raw.githubusercontent.com/AlexadeZ17/born2beroot/main/img/Screen%20Shot%202022-11-16%20at%204.17.51%20PM.png?token=GHSAT0AAAAAAB26ALHP7LA7YVIGA7HP3HNCY3VAEYQ">

Once this changes are made, I will restart the SSH service with ``sudo service ssh restart`` and then check if the port has been changed with ``sudo service ssh status``

<img src="https://raw.githubusercontent.com/AlexadeZ17/born2beroot/main/img/Screen%20Shot%202022-11-16%20at%204.27.50%20PM.png?token=GHSAT0AAAAAAB26ALHOPVNHN6AVTEOETXIOY3VAYWQ">




