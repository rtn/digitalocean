# ANSIBLE FREEBSD EXAMPLE
 
# IMPORTANT NOTES
- If the remote host is FreeBSD, ansible expect python to be in Linux location /usr/bin/python.  So a symlink is needed on the remote host or ansible will fail with a message cannot locate python. To create the symlink, ssh to the remote host and do "ln -s /usr/local/bin/python2.7 /usr/bin/python" as root user or sudo with super user privilege.
