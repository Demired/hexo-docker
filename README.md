# hexo page runtime environment for docker

nginx 1.10

hexo page

## TODO

upgrade openssl to latest

enabled http2

## USAGE

```
# Taking CentOS as an example

# Signin Linux

# Upgrade system 
yum upgrade -y

# Install docker
yum install -y docker git

service docker start

# Install docker-compose
curl -L "https://github.com/docker/compose/releases/download/1.23.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
chmod +x /usr/local/bin/docker-compose

# Create certificate folder
mkdir -p ~/opt/conf/nginx/certificate
cd ~/opt/conf/nginx/certificate

# Upload certificate
# rz www_0x8c.pem
# rz www_0x8c.key

# Create root folder
mkdir -p ~/opt/root
cd ~/opt/root

# Pull web page
git clone -b gh-pages https://github.com/Demired/Demired.github.io.git

# Create log folder
mkdir -p ~/opt/log/nginx/t_0x8c ~/opt/log/nginx/www_0x8c

cd ~

# Pull docker-compose file and nginx config
git clone https://github.com/Demired/hexo-docker.git

cd hexo-docker

# Launch docker-compose
docker-compose up -d
```
