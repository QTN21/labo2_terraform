# Labo 2 Cloud : SIEM

Ce labo a pour but de mettre en place un SIEM sur une infrastructure générée avec Terraform. Ce repository contient un README.md avec la description de l'infrastructure mise en place, les fichiers de configuration pour lancer l'infrastructure, un dossier avec un schema d'attaque crée via [Attack Flow Builder](https://center-for-threat-informed-defense.github.io/attack-flow/ui/).
La finalité du projet est de mener une attaque par bruteforce sur la machine afin qu'elle soit détectée par le SIEM.

## Elements de l'architecture
| Element Azure | Nom| Quantité |
|--|--|--|
| Security Group | myNetworkSecurityGroup | 1|
| Network Interface Card | myNIC | 1 |
| Disk | myOSDisk| 1|
| Virtual Machine | myVM_HELMO|1|
| Virtual Network | myVnet|1|
| Public IP Address | myPublicIP|1|

## Description
La machine virtuel est composée des éléments de base : disque, carte réseau (avec IP publique). Elle est placée dans un LAN Virtuel, lui-même placé dans un sécurity group qui joue le role de Firewall pour notre infrastructure. Une paire de clé SSH a été configurée sur la machine afin de pouvoir y accéder à distance.

## Aperçu de l'architecture
![](./.images/diagram_azure.jpg) 

--- 

# Exemple d'attaque : Bruteforce de clé SSH
Le but de cette attaque est de trouver des clés publiques SSH afin de mener un bruteforce sur la machine dans Azure.

![](./Attack_Flow_Builder/Bruteforce_SSH_VM_Azure.png)
