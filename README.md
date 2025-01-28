# <h2 align=center>Privasea Privanetix Node</h2>
- Buy VPS di : [t.me/skuycloud](t.me/skuycloud)
## Minimum Requirements

| **Requirement**         |
|-------------------------|
| 100GB                   |
| 4GB RAM / 8GB RAM       |
| 6 cores / 4 cores       |


## Guide Install
1. First install Docker (Jika belum install docker, jika sudah gausah install)
```
sudo apt install apt-transport-https ca-certificates curl software-properties-common -y && curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add - && sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable" && sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin -y
```
2. Run docker pull
```
docker pull privasea/acceleration-node-beta:latest
```
3. Buat folder dan masuk ke directory
```
mkdir -p ~/privasea/config && cd ~/privasea
```
4. Get a new wallet keystore
```
docker run --rm -it -v "$HOME/privasea/config:/app/config" privasea/acceleration-node-beta:latest ./node-calc new_keystore
```
5. Pindahkan keystore ke file baru (Ganti *** jadi UTC--2025.... ganti yg bawah ini jadi keystoremu)
```
mv $HOME/privasea/config/UTC--*** $HOME/privasea/config/wallet_keystore
```
6. Pergi ke [Privasea Privanetix Dashboard](https://deepsea-beta.privasea.ai/privanetixNode)
- Connect wallet untuk menerima reward (I will use 1% commission)
7. Jalankan Privasea Privanetix Node, jangan lupa diganti **GANTI_KEYSTORMU_DEPANNYA_UTC-2025** sama **GANTI_PASSWORDMU**, ganti Keystore sama ganti passwordmu yg dibuat tadi di step 4
```
KEYSTORE_PASSWORD=GANTI_KEYSTORMU_DEPANNYA_UTC && docker run -d --name privanetix-node -v "$HOME/privasea/config:/app/config" -e KEYSTORE_PASSWORD=GANTI_PASSWORDMU privasea/acceleration-node-beta:latest
```

8. Sekarang tinggal ikutin **Step Terakhir (Manage my Privanetix node)** ke [Click disini mas](https://www.privasea.ai/privanetix-node)
----------------------
- Trakteer buat buy Kopi : https://trakteer.id/brrrskuy/tip
