docker-ubuntu-vnc-desktop
=========================

Docker image to provide HTML5 VNC interface to access ROS melodic on Ubuntu 17.10 with the LXDE desktop environment.

Quick Start
-------------------------

Run the docker image and open port `6080`

```
docker run -it --rm -p 6080:80 wxwilcke/vnc-ros-melodic-full
```

Browse http://127.0.0.1:6080/

Alternatively, run the supplied docker-compose config

```
docker-compose up
```

Connect with VNC Viewer and protect by VNC Password
------------------

Forward VNC service port 5900 to host by

```
docker run -it --rm -p 6080:80 -p 5900:5900 wxwilcke/vnc-ros-melodic-full
```

Now, open the vnc viewer and connect to port 5900. If you would like to protect vnc service by password, set environment variable `VNC_PASSWORD`, for example

```
docker run -it --rm -p 6080:80 -p 5900:5900 -e VNC_PASSWORD=mypassword wxwilcke/vnc-ros-melodic-full
```

A prompt will ask password either in the browser or vnc viewer.


Troubleshooting and FAQ
==================

1. boot2docker connection issue, https://github.com/fcwu/docker-ubuntu-vnc-desktop/issues/2
2. Screen resolution is fitted to browser's window size when first connecting to the desktop. If you would like to change resolution, you have to re-create the container


License
==================

See the LICENSE file for details.

Contribution
==================

This build script is forked from https://github.com/ct2034/docker-ubuntu-vnc-desktop and includes an upgrade to Ubuntu 17.10 and ROS Melodic
