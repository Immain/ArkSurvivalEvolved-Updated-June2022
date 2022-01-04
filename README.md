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
- VMWare with AlmaLinux 8.5 or higher Installed (MacOS)
- Physical Machine with AlmaLinux 8.5 or higher (Recommended) 

# Generating a Hashed Password For This Script
- sudo dnf -y install epel-release
- sudo dnf install python3
- python3 -c 'import crypt,getpass;pw=getpass.getpass();print(crypt.crypt(pw) if (pw==getpass.getpass("Confirm: ")) else exit())'
- It will immediately ask you to type in a password and then confirm it (Like The Example Below)
```
Password: 
Confirm: 
$6$/1OFlW9yH1KHHiOm$pn2SfNgbF/rbblahjseab/p1Xb6Z29UZik.BUilZ.TLnp9yvl2HViB3fs8XdVteboeioss7o2A4g1IYxw.TFJ/
```

# Installing Ansible on AlmaLinux 8.5 or higher:
- sudo dnf update -y
- sudo dnf makecache
- sudo dnf install epel-release -y
- sudo dnf makecache
- sudo dnf install ansible -y
- ansible --version

# Ports:
- The Island
  - 27015/udp Query
  - 7777/udp Game client port 
  - 32330/udp Rcon

# Map-Names:
- The Island: TheIsland
