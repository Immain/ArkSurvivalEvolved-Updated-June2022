# ArkSurvivalEvolved-Updated-June2022
<img src=https://almalinux.org/static/images/logo.svg>
<img src=https://playpc.io/wp-content/uploads/2020/08/ark-sruvival-evolved-wallpaper.jpg>

# Automation Script for Ark Survival Evolved - Vanilla Linux Script for AlmaLinux

Ark Survival Evolved Cluster Automation Script - **Updated June 20, 2022**

This project is ongoing and will continue to be updated over time.

# Requirements: 
- AlmaLinux 8.5 / CentOS 8 Stream or higher ( This can be installed on a local machine or using a VMware Service of your choice)
- You can download the AlmaLinux ISO here: https://mirrors.almalinux.org/isos.html
- Access to Port Forwarding on your router
- RAM: 8GB of RAM or Higher
- SSD: 100GB or Higher
- Processor: Intel Core i5-8400 or Higher / AMD Ryzen 5 1600 or Higher
- Does NOT require GPU usage

# Machine Suggestions:
- VMWare, Hyper-V, VirtualBox, VMWare Workstation with AlmaLinux 8.5 or higher Installed
- Physical Machine with AlmaLinux 8.5 or higher (Recommended) 

# Installation

## 1. Install Ansible
```
sudo dnf update -y
```
```
sudo dnf makecache
```
```
sudo dnf install epel-release -y
```
```
sudo dnf makecache
```
```
sudo dnf install ansible -y
```
```
ansible --version
```

## 2. On your Linux Desktop:
```
sudo mkdir /home/arkserver/Desktop
```
```
cd /home/arkserver/Desktop/ArkSurvivalEvolved-Updated-June2022
```
```
sudo dnf install git -y
```
**Make sure you are within the arkserver directory, then run:**
```
git clone https://github.com/Immain/ArkSurvivalEvolved-Updated-June2022.git
```

## 3. Generating a Hashed Password For This Script:
```
sudo dnf -y install epel-release
```
```
sudo dnf install python3
```
```
python3 -c 'import crypt,getpass;pw=getpass.getpass();print(crypt.crypt(pw) if (pw==getpass.getpass("Confirm: ")) else exit())'
```
**It will immediately ask you to type in a password and then confirm it (Like The Example Below)**
```
Password: 
Confirm: 
$6$/1OFlW9yH1KHHiOm$pn2SfNgbF/rbblahjseab/p1Xb6Z29UZik.BUilZ.TLnp9yvl2HViB3fs8XdVteboeioss7o2A4g1IYxw.TFJ/
```
**Once this is completed, take the generated hash and add it to the start script under vars/password.**

## How to Cluster Your Server
To cluster your server, add the following by using the command:
```
sudo nano /home/arkserver/linux/ark/theisland.sh
```
```
screen -dmS theisland ShooterGame/Binaries/Linux/ShooterGameServer TheIsland?listen?Multihome=0.0.0.0?SessionName=$?MaxPlayers=$?QueryPort=$?Port=$?ServerAdminPassword=$ -NoTransferFromFiltering clusterid=cluster00000 -server -log
```
Cluster ID's can be any number, for each server, you will need to add the exact same cluster id to the bash file in order to cluster your servers correctly.

## How to Run The Ansible Script
Use the following to initiate the Ark Server Ansible Script
```
cd /home/arkserver/Desktop/ArkSurvivalEvolved-Updated-June2022
```
```
ansible-playbook launcher.yaml --ask-become-pass
```
Type the Sudo password you created, the script should run on it's own after that.

# Discord Integration

## Discord Webhooks:
In order to send Discord Notifications from Ansible, you will need to install the community add-on using:
```
ansible-galaxy collection install community.general
```
**Making a Webhook:**
Open your Server Settings and head into the Integrations tab:
Click the "Create Webhook" button to create a new webhook!
<img src=https://support.discord.com/hc/article_attachments/1500000463501/Screen_Shot_2020-12-15_at_4.41.53_PM.png>
You'll have a few options here. You can:

Edit the avatar: By clicking the avatar next to the Name in the top left

Choose what channel the Webhook posts to: By selecting the desired text channel in the  dropdown menu.

Name your Webhook: Good for distinguishing multiple webhooks for multiple different services.

You now have your own handy URL / pneumatic tube schoomp-er that you can link to more websites to receive messages from. 
<img src=https://support.discord.com/hc/article_attachments/360101553853/Screen_Shot_2020-12-15_at_4.51.38_PM.png>

# Updating Ark Survival Evolved:
**To Update Ark Survival, Use the script under "Tools" labeled update.yaml**
```
cd /home/arkserver/ArkSurvivalEvolved-Updated-June2022/tools
```
```
ansible-playbook update.yaml
```
**You can also copy the update script into your /home/arkserver/linux/ark/ folder and execute the playbook**
```
sudo cp /home/arkserver/ArkSurvivalEvolved-Updated-June2022/tools/update.yaml /home/arkserver/linux/ark/
```
**Then execute the script with**
```
ansible-playbook update.yaml
```
# Ports:
> The Island
 - **27015/udp Query**
 - **7777/udp Game client port**

# Map-Names:
- The Island:	TheIsland
- The Center:	TheCenter
- Scorched Earth:	ScorchedEarth_P
- Ragnarok:	Ragnarok
- Aberration:	Aberration_P
- Extinction:	Extinction
- Valguero:	Valguero_P
- Genesis Part-1:	Genesis
- Crystal Isles	CrystalIsles
- Genesis Part-2:	Gen2
- Lost Island:	LostIsland
- Fjordur: Fjordur

# Update Log:
- 06/20/22: **Updated Script to current ansible changes, fixed typos and removed modules that no longer worked.**
- 04/28/22: **Added Discord Notifications & Fixed some errors with the script**
- 01/05/22: **Changed order of tasks due to INI not moving over correctly**
- 01/04/22: **Added automation tools including update, start, and stop**
- 01/03/22: **Create Repository**
