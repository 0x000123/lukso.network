# Lukso.Network | Run Node
- Twitter : twitter [lukso_io](https://twitter.com/lukso_io/)
- Discord : Dircord [lukso](https://discord.gg/emkwYkvCPm)
- Website : [lukso.network](lukso.network)

## Konfigurasi
Izinkan lalu lintas untuk port yang tercantum di atas.
```
sudo ufw allow 30303/tcp
sudo ufw allow 30303/udp
sudo ufw allow 13000/tcp
sudo ufw allow 12000/udp
```

## Install Dependencies
- Install Curl
```
sudo apt-get -y update
sudo apt-get -y install curl
```

- Install Docker
```
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
```

- Install Docker Compose
```
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
docker-compose --version
```

## Install the LUKSO Command Line Interface (CLI)
