# Install and start Xvfb and a vnc client to run GUI programs
# WARNING: Xvfb doesn't use the GPU!!!

FROM ubuntu

# xvfb as X11 server
# x11vnc as VNC client
# fluxbox as window manager
RUN apt-get update && apt-get install -y x11vnc xvfb fluxbox
ADD entrypoint /usr/bin/entrypoint
RUN chmod a+x /usr/bin/entrypoint

CMD ["echo No command given!"]
ENTRYPOINT ["entrypoint"]