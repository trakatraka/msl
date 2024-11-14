FROM fedora:latest
# user creation
RUN groupadd -r -g 1000 user
RUN useradd -u 1000 -g 1000 -m -s /bin/bash user
# add user to wheel
RUN usermod -a -G wheel user
# tools
RUN echo "installing tools"
RUN dnf install --setopt=install_weak_deps=False -y sqlite git nmap wget yt-dlp vim nano curl passwd sudo screen gcc-c++ make python3 python3-virtualenv iputils netcat tcpdump telnet htop passwd traceroute whois ffmpeg-free
#RUN dnf install -y nodejs
WORKDIR /root
RUN curl -fsSL https://rpm.nodesource.com/setup_23.x -o nodesource_setup.sh
RUN bash nodesource_setup.sh
RUN dnf install -y nodejs
# update packages
RUN dnf update -y