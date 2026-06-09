FROM ubuntu:22.10
RUN sed -i 's|archive.ubuntu.com|old-releases.ubuntu.com|g' /etc/apt/sources.list && \
    sed -i 's|security.ubuntu.com|old-releases.ubuntu.com|g' /etc/apt/sources.list
RUN apt-get update && apt-get install -y openssh-client openssh-server
# Crear usuario prueba con contraseña prueba
RUN useradd -m prueba && echo "prueba:prueba" | chpasswd
RUN mkdir -p /var/run/sshd
RUN apt-get update && apt-get install -y openssh-client openssh-server tcpdump
EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]