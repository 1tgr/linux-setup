# Using `docker` without `sudo`
From https://askubuntu.com/a/477554:
```bash
sudo groupadd docker
sudo gpasswd -a $USER docker
newgrp docker
docker run hello-world
```

# HTTP proxy
From https://docs.docker.com/config/daemon/systemd/#httphttps-proxy:
```bash
sudo mkdir -p /etc/systemd/system/docker.service.d
sudo vim /etc/systemd/system/docker.service.d/http-proxy.conf
```
```
[Service]
Environment="HTTP_PROXY=http://proxy.example.com:80/" "HTTPS_PROXY=http://proxy.example.com:80/"
```
```bash
sudo systemctl daemon-reload
sudo systemctl restart docker
systemctl show --property=Environment docker
```
