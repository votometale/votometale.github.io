Hello guys!
In this tutorial I'm going through a Tutorial to create a VPN server.

There are several approaches to this, the first one is the easiest one:

## How to create a VMESS / VLESS server:

1. ### Buy a cheap Ubuntu server:

- I personally use http://ovh.com
- Go for buying **Virtual Private Server**

![Buy VPS](/buy_vps.jpeg "Buy VPS")
- The first two cheap options would work
- Choose the **Distribution Only** image
- Go for **Ubuntu**
- Complete the buying process.
- After a **short while** (takes ~5 minutes) you will receive your credentials on your email.
- In a separate email you receive the following information: IP + username + password
- You can use any ssh client you want: I am using **Termius** on my Mac.
- Now you have your server ready to be setup.

2. ### Setup necessary stuff on server:

- Make a SSH connection to your server
- some typical commands: `sudo apt-get update`
- or once more: `sudo apt-get upgrade`
- Run the following command to start v2ray script `bash <(curl -s -L https://git.io/v2ray.sh)` 
- This will ask some questions in chinese:
- The first one asks about the *version*
- Then asks for the protocol, *TCP* works usually fine
- Now you choose the *port* (remember your port choice)
- Then it asks if you want to install *Ad Blocker*, you can say NO
- Next it asks if you want to install *Shadow Socks*, you can say NO
- And finally you should press *Enter* to finish installation

3. ### Open up your firewall:

- Install ufw: `apt install ufw`
- Open up typical ports: `ufw allow http`, `ufw allow https`, `ufw allow ssh`
- Open up VMESS port you chose before: `ufw allow <the number above>`
- run: `ufw enable`

4. ### Check if the configuration is happy ready:

- run `v2ray url`. This should show to you the configurartion link.

5. ### Install v2ray client on your devices:

v2ray apps for Android:
- v2RayNG
- Kitsunebi
- BifrostV
- V2Ray


v2ray apps for iOS:
- ShadowRocket
- Kitsunebi – supports UDP relay
- Quantumult
- i2Ray
