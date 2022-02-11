# install docker in ubuntu vm

The following steps can be used to install docker and use it without sudo in Ubuntu 20.04 server edition.
For other/newer Ubuntu version adjust the repository accordingly as these specific commands apply to the 20.04 (Focal) version

## Command set

```shell
sudo apt update

sudo apt install -y apt-transport-https ca-certificates curl software-properties-common

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"

sudo apt update

apt-cache policy docker-ce

sudo apt install -y docker-ce docker-compose

sudo systemctl status docker

sudo usermod -aG docker ${USER}
```

logout or exit the session

```shell
docker volume create portainer_data

docker run -d -p 8000:8000 -p 9443:9443 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce
```

## Version

1.0.0

## License

[MIT](LICENSE)
