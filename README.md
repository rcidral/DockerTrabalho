# Trabalho Docker ELK


## Configurar rede: 
Entrar como root
```
$ su
```
Obter endereço ip
```
$ curl ifconfig.me 
```
Alterar configurações da placa de rede
```
$ vi /etc/sysconfig/network-scripts/ifcfg-enp0s3 
```
Alterar e inserir parâmetros
```
BOOTPROTO=static 

IPADDR=000.000.000.000 

NETMASK=255.255.255.0 
```
Alterar hostname
```
$ vi /etc/hostname 
```
Novo nome
```
oracle-linux.localdomain 
```
```
$ vi /etc/sysconfig/network 
```
```
NETWORKING=yes 

HOSTNAME=oracle-linux 

GATEWAY=10.0.2.2     
```


## Configurar de SSH: 
Bloquear acesso root via ssh
```
$ vi /etc/ssh/sshd_config 
```
Alterar parâmetro
```
PermitRootLogin no 
```
```
$ systemctl restart sshd    
```


## Instalar Docker: 
```
$ sudo yum update sudo yum install -y yum-utils 
```
```
$ sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo 
```
```
$ sudo yum update sudo yum install docker-ce docker-ce-cli containerd.io 
```
```
$ sudo systemctl start docker 
```
```
$ sudo systemctl enable docker 
```
Reinicialização do sistema
```
$ shutdown -r now 
```
```
$ systemctl status docker 
```
```
$ sudo docker run hello-world 
```
```
$ sudo groupadd docker 
```
```
$ sudo usermod -aG docker nome_do_usuário 
```
```
$ newgrp docker 
```


## Instalar imagem ELK: 
```
$ docker pull sebp/elk 
```
```
$ docker images 
```
```
$ docker run -d --restart unless-stopped -p 5601:5601 -p 9200:9200 -p 5044:5044 -it id_imagem
```
```
$ docker ps 
```
```
$ docker rename id_container elk 
```
