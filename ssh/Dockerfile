# What this does:
# - install SSH server and client software
# - ssh-client: copy the SSH keys from the user to the container's SSH location
# - ssh-server: install the users public SSH key as trusted key and start the SSH server
# 
# Setup: the user that does `docker run` must run `ssh-keygen` and generate a pair of SSH keys with default names and without password
# 
# How to run: `docker run -v ~/.ssh:/ssh ...`
# when connecting with the SSH client do `ssh -o StrictHostKeyChecking=no` so it doesn't require user input

FROM ubuntu
RUN apt update && \
    apt-key adv --keyserver keyserver.ubuntu.com --recv-keys F42ED6FBAB17C654 && \ 
    apt install -y ssh openssh-server && \
    mkdir /var/run/sshd && /usr/sbin/sshd

COPY ssh-client ssh-server /usr/bin
RUN chmod a+x /usr/bin/ssh-client && \
    chmod a+x /usr/bin/ssh-server

CMD ssh-client && ssh-server