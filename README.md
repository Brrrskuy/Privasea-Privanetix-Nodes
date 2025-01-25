# <h2 align=center>Privasea Privanetix Node</h2>

## Minimum System Requirements

| **Component**             | **Requirement**                     |
|---------------------------|-------------------------------------|
| **Operating System (OS)** | Ubuntu (Recommended)                |
| **CPU Architecture**      | amd64 (x86 architecture)            |
| **Storage**               | 100GB available storage             |
| **Memory (RAM)**          | 4GB RAM                             |
| **Processor**             | 6 cores                             |


## Guide Install
1. First install `Docker` in your system 
```
sudo apt install apt-transport-https ca-certificates curl software-properties-common -y && curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add - && sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable" && sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin -y
```
2. First pull the docker image using the following command
```
docker pull privasea/acceleration-node-beta:latest
```
3. Create a directory and navigate to it
```
mkdir -p ~/privasea/config && cd ~/privasea
```
4. Run the below command to get a new wallet keystore
- Here you need input a password after running the below command, make sure to remember it for future use and also note down the `node address` as well
```
docker run --rm -it -v "$HOME/privasea/config:/app/config" privasea/acceleration-node-beta:latest ./node-calc new_keystore
```
5. Move the keystore file to a new file (UTC--2025 ganti yg bawah ini jadi keystoremu)
```
mv $HOME/privasea/config/UTC--* $HOME/privasea/config/wallet_keystore
```
6. Now visit this [Privanetix Dashboard](https://deepsea-beta.privasea.ai/privanetixNode)
- Connect a wallet where you will recieve reward and then give the node any name, set up commission (I will use 5%), and then enter the `node address` you note down in above step and then click on **Set up my node** option
7. Now run the below command to start your `Privasea Privanetix Node`, Make sure to replace **ENTER_YOUR_KEYSTORE_PASSWORD** with your **Keystore Password**, you provided in the above steps
```
KEYSTORE_PASSWORD=ENTER_YOUR_KEYSTORE_PASSWORD && docker run -d --name privanetix-node -v "$HOME/privasea/config:/app/config" -e KEYSTORE_PASSWORD=$KEYSTORE_PASSWORD privasea/acceleration-node-beta:latest
```

8. Now follow the guide from **Step 3 (Manage my Privanetix node)** from [this docs](https://www.privasea.ai/privanetix-node)
