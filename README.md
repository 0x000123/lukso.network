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
- Buat Direktori
```
mkdir lukso-l16-testnet
```

- dan arahkan ke terminal Anda dengan menggunakan cdperintah
```
cd lukso-l16-testnet
```

- Kemudian, instal LUKSO CLI menggunakan skrip instal:
```
sudo curl https://install.l16.lukso.network | sudo bash
```

### Periksa
```
lukso -v
```
> Outputnya harus v.0.4.3 atau lebih tinggi.


## Inisialisasi 
```
sudo lukso network init --chain l16
```

> Perintah ini akan meminta Anda untuk mengatur nama node Anda.

## Mulai 
### Anda dapat memulai simpul Anda dengan:
```
sudo lukso network start
```

### Periksa 
Tunggu 1 jam dan periksa apakah node Anda telah disinkronkan di halaman statistik ini:

- https://stats.execution.l16.lukso.network
Segera setelah memulai node Anda, Anda dapat memeriksa proses sinkronisasi di log Anda .

### Untuk Hentikan
```
sudo lukso network stop
```

## Selanjutnya Menjalankan Validator
``
INFO
Sebelum menjalankan validator pada node Anda, pastikan node Anda berjalan dan bekerja dengan benar. Untuk informasi selengkapnya, periksa halaman Jalankan node .
``

### Penyetelan Validator
```
cd lukso-l16-testnet
sudo lukso network validator setup
```

Ini akan membuat penyimpanan kunci dan dompet transaksi. Tujuan dari dompet transaksi adalah untuk menelepon dan membayar transaksi deposit.

Jika ini adalah pertama kalinya Anda menyiapkan validator, pilih untuk tidak menggunakan Mnemonic yang sudah ada.

Pilih untuk membuat Mnemonic penarikan terpisah.

Mnemonik akan muncul di node_config.yamlfile Anda.

Bukalah ``node_config.yaml``
```
nano node_config.yaml
```

Salin Mnemonik Anda dan simpan di tempat yang aman dan offline.


## Periksa 
Periksa apakah dompet memiliki cukup dana:
```
lukso network validator describe
```

Kunjungi [Faucet](https://faucet.l16.lukso.network/) dan rekatkan alamat publik dompet transaksi ke dalam bidang dan pilih jumlah LYXt yang ingin Anda terima.


## Setor 
``BAHAYA
Jika Anda 100% yakin semuanya benar, Anda dapat menyetor LYXt Anda, Anda akan kehilangan semua LYXt Anda jika Anda melakukan kesalahan``
```
lukso network validator deposit
```

Diperlukan waktu hingga delapan jam sebelum validator Anda aktif, tetapi Anda sudah dapat memulai validator untuk sementara.

Setelah Anda mendepositkan LYXt, pastikan untuk membuat cadangan.
```
lukso network validator backup
```

Simpan file node_recovery.json di tempat yang aman dan offline.

## Mulai 
```
sudo lukso network start
```
```
sudo lukso network validator start
```

Periksa status validator Anda, diperlukan waktu hingga 8 jam sebelum validator Anda aktif
```
lukso network validator describe
```

Pastikan semuanya bekerja dengan benar dengan memeriksa halaman statistik:

- [Statistik eksekusi](https://stats.execution.l16.lukso.network/)
- [Statistik konsensus](https://stats.consensus.l16.lukso.network/)
Anda juga dapat memeriksa [log](https://docs.lukso.tech/networks/l16-testnet/logs-stats-monitoring) Anda .


