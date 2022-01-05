# Ark-Survival-Evolved-Vanilla-Jan2022
<img src=https://almalinux.org/static/images/logo.svg>
<img src=https://www.nintendo.com//content/dam/noa/en_US/games/switch/a/ark-survival-evolved-switch/ark-survival-evolved-switch-hero.jpg>

# Automation Script for Ark Survival Evolved - Vanilla Linux Script for AlmaLinux

Ark Survival Evolved Cluster Automation Script

# Requirements: 
- AlmaLinux 8.5 or higher ( This can be installed on a local machine or using a VMware Service of your choice)
- You can download the AlmaLinux ISO here: https://mirrors.almalinux.org/isos.html
- Access to Port Forwarding on your router
- RAM: 8GB of RAM or Higher
- SSD: 100GB or Higher
- Processor: Intel Core i5-8400 or Higher / AMD Ryzen 5 1600 or Higher
- Does NOT require GPU usage

# Machine Suggestions
- VMWare, Hyper-V, VirtualBox, VMWare Workstation with AlmaLinux 8.5 or higher Installed
- Physical Machine with AlmaLinux 8.5 or higher (Recommended) 

# On your Linux Desktop:
```
sudo mkdir /home/arkserver/github
```
```
cd /home/arkserver/ArkSurvivalEvolved-Vanilla-Jan2022
```
```
sudo dnf install git -y
```
**Make sure you are within the github directory, then run:**
```
git clone https://github.com/Immain/ArkSurvivalEvolved-Vanilla-Jan2022.git
```
# Generating a Hashed Password For This Script
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

# Installing Ansible on AlmaLinux 8.5 or higher:
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
# Updating Ark Survival Evolved
**To Update Ark Survival, Use the script under "Tools" labeled update.yaml**
```
cd /home/arkserver/ArkSurvivalEvolved-Vanilla-Jan2022/tools
```
```
ansible-playbook update.yaml
```
**You can also copy the update script into your /home/arkserver/linux/ark/ folder and execute the playbook**
```
sudo cp /home/arkserver/ArkSurvivalEvolved-Vanilla-Jan2022/tools/update.yaml /home/arkserver/linux/ark/
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
> The Island: TheIsland

# Update Log
- 01/05/22: **Changed order of tasks due to INI not moving over correctly**
- 01/04/22: **Added automation tools including update, start, and stop**
