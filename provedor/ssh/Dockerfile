FROM ubuntu:latest

# Instala os pacotes necessários e configura o SSH
RUN apt-get update && \
    apt-get install -y openssh-server iputils-ping telnet && \
    mkdir /var/run/sshd && \
    echo 'PermitRootLogin yes' >> /etc/ssh/sshd_config && \
    echo 'PasswordAuthentication yes' >> /etc/ssh/sshd_config

# Add User
RUN useradd -m bob
RUN useradd -m patrick
RUN useradd -m julia
RUN useradd -m redes
# Set user passord
RUN echo "bob:redes"|chpasswd
RUN echo "patrick:redes"|chpasswd
RUN echo "julia:redes"|chpasswd
RUN echo "redes:redes"|chpasswd


# Expõe a porta 22 para SSH
EXPOSE 22

# Inicia o serviço SSH quando o container for iniciado
CMD ["/usr/sbin/sshd", "-D"]