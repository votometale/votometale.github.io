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

![Choose Distribution](/1.jpeg "Choose Distribution")

- Go for **Ubuntu**
- Complete the buying process.
- After a **short while** (takes ~10 minutes) you will receive your credentials on your email.
- In a separate email you receive the following information: **IP + username + password** .

To connect to your server you need a SSH client:
- You can use any ssh client you want: I am using **Termius** on my Mac. For windows you can use **putty** I guess, and for Ubuntu you can use its own **terminal**.
- Now you have your server ready to be setup.

2. ### Setup necessary stuff on server:

- Make a SSH connection to your server

![SSH Connection](/3.jpeg "SSH Connection")

- Run the following commands: `sudo apt-get update`, `sudo apt-get upgrade`
- Run the following command to start v2ray script `bash <(curl -s -L https://git.io/v2ray.sh)` 

![Run v2ray script](/4.jpeg "Run v2ray script")

- This will ask some questions in chinese language:
- The first one asks about the *version* of the v2ray you like:

![Choose version](/5.jpeg "Choose version")

- Then it asks for the protocol you would like to use, *TCP* works fine:

![Choose protocol](/6.jpeg "Choose protocol")

- Now you choose the *port* (remember your port choice)
- Then it asks if you want to install *Ad Blocker*, you can say NO
- Next it asks if you want to install *Shadow Socks*, you can say NO

![Finall questions](/7.jpeg "Final Questions")

- And finally it asks you to confirm the settings once more. You should press *Enter* to finish installation.

![Confirmation](/8.jpeg "Confirmation")

- Then it outputs once more the settings. Specifically you need the port:

![Output](/9.jpeg "Output")

3. ### Open up your firewall:

- Install ufw: `apt install ufw`
- Open up common ports: `ufw allow http`, `ufw allow https`, `ufw allow ssh`
- Open up VMESS port you chose before: `ufw allow <the number above>`

![Ports](/10.jpeg "Ports")

- Finally enable the firewall: `ufw enable`

4. ### Check if the configuration is happy ready:

- run `v2ray url`. This should show to you the configurartion link.

![URL](/11.jpeg "URL")

5. ### Run logging process on your server:

- Run the `v2ray log` command, and you will see the v2ray logs live. For the moment since nobody is connected to your server, there won't be any logs.

6. ### Share the URL of step 4 with your friends so that they can use it to connect to your server.

7. ### Install v2ray client on your devices:

Copy the shared link:

![Copy link](/13.jpeg "Copy link")

## IOS:
Install **NapsternetV**.

- Open the app, and on the **Configs** tab click on the **+** button on top right.

![Import](/14.jpeg "Import")

- Select the newly added link:

![Select the setting](/15.jpeg "Select the setting")

- And finally on the **Home** tab, press the **connect(play)** button.

![Connect](/16.jpeg "Connect")

## Android:
Install **V2rayNG**.

- Open the app, click on the **three dots** button on top right.

![Import](/14.jpeg "Import")

- Select the newly added link:

![Select the setting](/15.jpeg "Select the setting")

- And finally on the **Home** tab, press the **connect(play)** button.

![Connect](/16.jpeg "Connect")


8. ### You should see the logs on the server ;)
