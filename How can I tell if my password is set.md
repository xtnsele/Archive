How can I tell if my password is set?

**Run the below syntax**

passwd --status username
From man passwd:

Display account status information. The status information consists of 7 fields. The first field is the user's login name. The second field indicates if the user account has a locked password (L), has no password (NP), or has a usable password (P). The third field gives the date of the last password change. The next four fields are the minimum age, maximum age, warning period, and inactivity period for the password. These ages are expressed in days.


[https://unix.stackexchange.com/questions/184970/how-can-i-tell-if-my-password-is-set ](https://unix.stackexchange.com/questions/184970/how-can-i-tell-if-my-password-is-set )