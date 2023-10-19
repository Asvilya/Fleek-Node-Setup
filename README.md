# Fleek-Node-Setup
<h1 align="center">Fleek Network</h1>

```console
# Ubuntu 22.04 şart. 
4 CPU 8 RAM
```

#

> user ekleyin
```console
# isim yazan yerleri değişin.
adduser isim
usermod -aG sudo isim
su isim
cd /home/isim
```

<h1 align="center"> Kurulum </h1>

```console
# Güncelle
sudo apt update && sudo apt upgrade -y

sudo fallocate -l 10240M /swapfile
sudo chmod 600 /swapfile
sudo mkswap /swapfile
sudo swapon /swapfile

# rust ve kütüphaneleri yükle seçeneklerde 1'i seçiyoruz:
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
rustup update
```

```console
# Script ile kurulum aşamalar uzun sürebilir, sunucu performansınıza bağlı.
curl https://get.fleek.network | bash
# Yes/No sorularına yes diyoruz

# bize kurulum tamamlanınca Node Public Key ve Consensus Public Key vericek kaydedin.
```

> Bu esnada [buradan](https://faucet.testnet.fleek.network/) token alın fleeke cüzdan açıp

```console
# Servisi başlatalım. Tek Tek girin
sudo systemctl start lightning.service
sudo systemctl stop lightning.service
sudo systemctl restart lightning.service
```

> Mint ettiğiniz yerden bilgileri girip işlemi tamamlayın.

> kontrol komutu: `curl -sS https://get.fleek.network/healthcheck | bash`

![image](https://github.com/ruesandora/Fleek/assets/101149671/c042eef0-f50e-42b3-88e0-2845bf7201f0)
