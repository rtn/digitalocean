# ANSIBLE FREEBSD EXAMPLE
**Use At Your Own Risk!**

This is my learning exercise and a work-in-progress sandbox.  Hoever, what is here can be used as an example or sample of how to achive basic play. Most likely you'll have to tweak quite a few things to work for you.
 
Project is on a FreeBSD controller machine to controll FreeBSD remote host on Digital Ocean.


# IMPORTANT NOTES
- This is not an endorcement or advertisement for Digital Ocean; is is a cloud service I have at my disposal that I find simle to deploy and manage securely.
- Target is a web server on the $5/month droplet.  It is important you change tuning paramenters to optimize the host resource available ie RAM and type of disk.
- If the remote host is FreeBSD, ansible expect python to be in Linux location /usr/bin/python.  So a symlink is needed on the remote host or ansible will fail with a message cannot locate python. To create the symlink, ssh to the remote host and do "ln -s /usr/local/bin/python2.7 /usr/bin/python" as root user or sudo with super user privilege. Others suggested setting python env, but it was not clear whether on the ansible config or the remote hosts. Some suggested setting ansible config variable ansibl_python_interpreter variable, but I didn't get this to work.  Symbolic link thus far is the solution I am able to get a remote FreeBSD host to work.
- Setup ssh key w/o pass-phrase and define it for your remote hosts in ~/.ssh/config on the control machine.
- Recommend hardening sshd_config to remote root login and add `AllowUsers freebsd`

group_vars/do_grp1.yml.
