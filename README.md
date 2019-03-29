# hexo page runtime environment for docker

nginx 1.10

hexo page

## TODO

upgrade openssl to latest

enabled http2

## USAGE

```
#login linux

# Install docker,Taking CentOS as an example
yum upgrade -y
yum install -y docker git

service docker start

curl -L "https://github.com/docker/compose/releases/download/1.23.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

chmod +x /usr/local/bin/docker-compose

ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose

docker-compose --version

# create certificate folder
mkdir -p ~/opt/conf/nginx/certificate
cd ~/opt/conf/nginx/certificate

# Upload certificate
# rz www_0x8c.pem
# rz www_0x8c.key

mkdir -p ~/opt/root
cd ~/opt/root
git clone -b gh-pages https://github.com/Demired/Demired.github.io.git

# create log folder
mkdir -p ~/opt/log/nginx/t_0x8c ~/opt/log/nginx/www_0x8c


cd ~
git clone https://github.com/Demired/hexo-docker.git
cd hexo-docker
docker-compose up -d
```
