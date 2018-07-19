**Server putty connect 'Disconnected: No supported** 

Authentication methods available (server sent: publickey)


Turn on Password Authentication
By default, you need to use keys to ssh into your server, but you can turn on password authentication if you do not need that level of security.


**simply** Edit the /etc/ssh/sshd_config file.

Change 
- PasswordAuthentication and 
- ChallengeResponseAuthentication to yes.

**Restart** - ssh /etc/init.d/ssh restart 
        - sudo systemctl restart sshd 



https://askubuntu.com/questions/204400/ssh-public-key-no-supported-authentication-methods-available-server-sent-publ