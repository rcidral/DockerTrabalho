# DockerTrabalho

Comandos para alteração do teclado: 

sudo localectl list-keymaps sudo localectl set-keymap br-abnt2 

Configuração de rede: 

su curl ifconfig.me 

vi /etc/sysconfig/network-scripts/ifcfg-enp0s3 

BOOTPROTO=static 

IPADDR=000.000.000.000 

NETMASK=255.255.255.0 

vi /etc/hostname oracle-linux.localdomain 

ip route 

vi /etc/sysconfig/network 

NETWORKING=yes 

HOSTNAME=oracle-linux 

GATEWAY=10.0.2.2     


Configuração de SSH: 

vi /etc/ssh/sshd_config 

PermitRootLogin no 

systemctl restart sshd    


Comandos para instalação do Docker: 

sudo yum update sudo yum install -y yum-utils 

sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo 

sudo yum update sudo yum install docker-ce docker-ce-cli containerd.io 

sudo systemctl start docker 

sudo systemctl enable docker 

shutdown -r now 

systemctl status docker 

sudo docker run hello-world 

sudo groupadd docker 

sudo usermod -aG docker nome_do_usuário 

newgrp docker 


Comandos para instalação da imagem ELK: 

docker pull sebp/elk 

docker images 

docker run -d --restart unless-stopped -p 5601:5601 -p 9200:9200 -p 5044:5044 -it id_imagem

docker ps 

docker rename id_container elk 


