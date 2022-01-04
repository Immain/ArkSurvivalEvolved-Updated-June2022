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

# Installing Ansible on AlmaLinux 8.5 or higher:
- sudo dnf update -y
- sudo dnf makecache
- sudo dnf install epel-release -y
- sudo dnf makecache
- sudo dnf install ansible -y
- ansible --version
