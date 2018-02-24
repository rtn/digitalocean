# ANSIBLE FREEBSD EXAMPLE
** Use At Your Own Risk **
This is only meant to be an example and most likely you'll have to tweak quite a few things to work for you case.
 
Project is on a FreeBSD controller machine to controll FreeBSD remote host on Digital Ocean.


# IMPORTANT NOTES
- If the remote host is FreeBSD, ansible expect python to be in Linux location /usr/bin/python.  So a symlink is needed on the remote host or ansible will fail with a message cannot locate python. To create the symlink, ssh to the remote host and do "ln -s /usr/local/bin/python2.7 /usr/bin/python" as root user or sudo with super user privilege. Others suggested setting python env, but it was not clear whether on the ansible config or the remote hosts. Some suggested setting ansible config variable ansibl_python_interpreter variable, but I didn't get this to work.  Symbolic link thus far is the solution I am able to get a remote FreeBSD host to work.
