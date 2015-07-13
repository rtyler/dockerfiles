# Docker container for running the Zoom beta client in a container
#
# The application doesn't pick up audio properly, so you have to phone into
# your meetings
#
# It also expects that the Zoom installer has been run on the host machine so
# it can be mapped in properly
#
#    docker run -it \
#        --net=host \
#        -v /tmp/.X11-unix:/tmp/.X11-unix \
#        -v $HOME/Zoom:/root/Zoom \
#        -v $HOME/.config/pulse:/root/.config/pulse \
#        -e DISPLAY=unix$DISPLAY \
#        -e PULSE_SERVER="tcp:localhost:4713" \
#        --device /dev/video0 \
#        --device /dev/snd \
#        --name ${NAME} \
#        zoom
#
# Base docker image
FROM ubuntu:precise
MAINTAINER R Tyler Croy <tyler@monkeypox.org>

# Install 32-bit dependencies
RUN apt-get update && apt-get install -y \
            libglib2.0-0:i386 \
            libgles2-mesa:i386 \
            libegl1-mesa:i386 \
            libxcb-shape0:i386 \
            libxcb-shm0:i386 \
            libgl1-mesa-glx:i386 \
            libxi6:i386 \
            libsm6:i386 \
            libfontconfig1:i386 \
            libxrender1:i386 \
            libpulse0:i386 \
            libxcomposite1:i386 \
            libxslt1.1:i386 \
            libgstreamer-plugins-base0.10-0:i386 \
            libssl1.0.0:i386 \
            libxkbcommon0 \
            libwebkit4:i386 \
            firefox # need for SSO login, lol!

