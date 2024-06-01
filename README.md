# ANSIBLE FREEBSD EXAMPLE
**Use At Your Own Risk!**

This is my learning exercise and a work-in-progress sandbox.  However, what is here can be used as an example or sample of how to achieve basic play. Most likely you'll have to tweak quite a few things to work for you.
 
The project is on a FreeBSD controller machine to control the FreeBSD remote host on Digital Ocean.


# IMPORTANT NOTES
- This is not an endorsement or advertisement for Digital Ocean; it is a cloud service I have at my disposal that I find simple to deploy and manage securely.
- Target is a web server on the $5/month droplet.  You must change tuning parameters to optimize the host resource available ie RAM and type of disk.
- If the remote host is FreeBSD, ansible expects python to be in Linux location /usr/bin/python.  So a symlink is needed on the remote host or Ansible will fail with a message that cannot locate Python. To create the symlink, ssh to the remote host and do "ln -s /usr/local/bin/python2.7 /usr/bin/python" as root user or sudo with superuser privilege. Others suggested setting Python env, but it was not clear whether on the Ansible config or the remote hosts. Some suggested setting ansible config variable ansibl_python_interpreter variable, but I didn't get this to work.  Symbolic link thus far is the solution I can get a remote FreeBSD host to work.
- Set up the ssh key w/o pass-phrase and define it for your remote hosts in ~/.ssh/config on the control machine.
- Recommend hardening sshd_config to remote root login and add `AllowUsers freebsd`

group_vars/do_grp1.yml.
