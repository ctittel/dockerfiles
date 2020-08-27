# Install and start Xvfb and a vnc client to run GUI programs
# WARNING: Xvfb doesn't use the GPU!!!
# the VNC client runs on port 5900 by default and uses no password
# How to use:
# - publish the VNC port to the host with `docker run -p 5900:5900`
# - forward the VNC port to whatever computer the vnc client runs on, e.g. with `ssh -N -T -L 5900:localhost:5900 user@remotehost &`
# - start the vnc client: `vncviewer localhost:5900`

FROM ubuntu

# xvfb as X11 server
# x11vnc as VNC client
# fluxbox as window manager
RUN apt-get update && apt-get install -y x11vnc xvfb fluxbox
ADD entrypoint /usr/bin/entrypoint
RUN chmod a+x /usr/bin/entrypoint

CMD ["echo No command given!"]
ENTRYPOINT ["entrypoint"]