# Password Policy

Something important to keep our computer as secure as possible is to implement a strong password policy. The reqirements for this project are: 

- At least 10 characters long
- It must contain an uppercase letter, a lowercase letter, and a number
- It must not contain more than 3 consecutive identical characters.

In order to do that, we will have to install ``libpam-pwquality`` with the good old command ``sudo apt-get install libpam-pwquality``. Once it is installed, we will edit the file where the password policies are stored at: ``common-password``. We edit it with executing the command ``nano /etc/pam.d/common-password``. In this file we go to the first line and will add the following rules:

- ``minlen = 10`` &rarr; sets the minimum length of the password to be 10 characters
- ``lcredit = -1`` &rarr; Requires at least one lowercase character
- ``ucredit = -1`` &rarr; Requires at least one uppercase character
- ``dcredit = -1`` &rarr; Requires at least one digit
- ``retry = 3`` &rarr; Maximum number of attemnts
- ``maxrepeat = 3`` &rarr; Allows no more than 3 times the same character

