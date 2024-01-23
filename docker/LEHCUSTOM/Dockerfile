# Use an official Ubuntu base image
FROM ubuntu:latest

# Install SSH
RUN apt-get update && apt-get install -y openssh-server
RUN mkdir /var/run/sshd

# Add a user
RUN useradd -rm -d /home/ubuntu -s /bin/bash -g root -G sudo -u 1000 ubuntu
RUN  echo 'ubuntu:ubuntu' | chpasswd

RUN apt-get update -y
RUN apt-get install nano -y

# SSH configuration
RUN sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config

# Expose the SSH port
EXPOSE 22

# Run SSH server
CMD ["/usr/sbin/sshd", "-D"]
