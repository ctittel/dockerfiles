# Make everyone root of the container without making them explicitly root
# not sure if it is working right now, maybe add (root) before NOPASSWD in the sudoers file
# also the sudoers file requires absoulte paths to all commands
# Command: docker run --rm -u $(id -u $USER):$(id -g $USER) -it https://github.com/ctonic/dockerfiles.git#:sudoers
FROM ubuntu
COPY sudoers /etc/sudoers
RUN chown root:root /etc/sudoers && chmod a-rwx /etc/sudoers && chmod ug+r /etc/sudoers