# **Update and Install Dependencies**
```
$ apt update -y && apt upgrade -y && apt autoremove -y && apt install screen curl -y
```
# **Install Docker**
```
$ apt install docker.io -y
```
# **Pull Images From Docker Hub**
```
$ docker pull raiblocksone/raione:R1_V.02
```
# **Run Nodes Once To Get Settings File**
```
$ docker run --restart=unless-stopped -d -p 7075:7075 -p 127.0.0.1:7076:7076 -p 127.0.0.1:7078:7078 -v /root/raiblocksone/:/root --name raione-node raiblocksone/raione:R1_V.02 
```
# **Stop Nodes**
```
$ docker stop raione-node
```
# **Enable Voting**
```
$ sudo nano raiblocksone/Nano/config-node.toml
```
# **copy this code below to the config-node.toml**
- Copy this code at the top of file config-node.toml
```
$ [node]
​
enable_voting = true
Change RPC Settings
```
# **change the value of enable_control to true**
```
$ sudo nano raiblocksone/Nano/config-rpc.toml
```
# **Restart The Services**
```
$ docker restart raione-node
```
# **RPC Command**
- use this command to interact with your nodes
Check nodes version
```
$ curl -d '{"action": "version"}' localhost:7076
```
Check nodes version
```
$ curl -d '{"action": "block_count"}' localhost:7076
```
Create New Nodes Wallet_ID
```
$ curl -g -d '{ "action": "wallet_create"}' localhost:7076
```
Import your wallet into node
```
curl -g -d '{ "action": "wallet_change_seed", "wallet": "YOUR_NODES_WALLET_ID", "seed": "YOUR_SEED_64char"}' localhost:7076
```
more rpc command are available on official nano pages : <a href="https://docs.nano.org/commands/rpc-protocol/">https://docs.nano.org/commands/rpc-protocol/</a>
# **To Backup Your SEED:**
Go to your docker container
```
$ docker exec -it raione-node /bin/bash
```
Use Command below to get your SEED and Private Key
```
$ /usr/bin/./nano_node --wallet_decrypt_unsafe --wallet=%YOUR_WALLLET_ID%
```
<img src="https://pbs.twimg.com/profile_images/1694749398457081856/QrgBrvWt_400x400.jpg">

# **Contact Me🔥☕**
<p align="left">
<a href="https://www.github.com/0xGilang"><img height="40" width="40" align="center" src="https://avatars.githubusercontent.com/u/94946818?v=4"></a>
<a href="https://www.facebook.com/Gilangbuanasultoni" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/facebook.svg" alt="AryaTrickers2020" height="30" width="40" /></a>
<a href="https://wa.me/6282131561458?text=Halo+Bang+Gilang" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/whatsapp.svg" alt="6289694295787" height="30" width="40" /></a>
<a href="https://twitter.com/Gilangsultoni"><img height="40" width="40" align="center" src="https://static.dezeen.com/uploads/2023/07/x-logo-twitter-elon-musk_dezeen_2364_col_0.jpg"></a>

------
------

