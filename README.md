# Born2beroot - Projet 42
## Description

Born2beroot est un projet de l'école 42 qui consiste à installer et configurer un serveur basé sur une distribution Linux (Debian ou CentOS). L'objectif de ce projet est de vous familiariser avec la gestion d'un système Unix-like, incluant la configuration de services essentiels, la gestion des utilisateurs, la sécurité et la surveillance du système.

Le projet met l'accent sur les bonnes pratiques de sécurité, la gestion des utilisateurs et des groupes, ainsi que l'automatisation de certaines tâches d'administration système.
Fonctionnalités

  - Installation et configuration d'un serveur sur une machine virtuelle (VM).
  
  - Mise en place de la partition automatique.
  
  - Sécurisation du serveur avec un pare-feu (ufw sur Debian ou firewalld sur CentOS).
  
  - Configuration d'un accès SSH sécurisé.
  
  - Configuration d'un utilisateur ayant des droits sudo limités avec une politique stricte de sécurité.
  
  - Mise en place de services de surveillance tels que UFW, fail2ban, et cron pour des tâches automatisées.
  
  - Installation et utilisation de AppArmor (ou SELinux pour CentOS) pour renforcer la sécurité.

## Installation

Pour ce projet, vous devrez installer une machine virtuelle (VM) sur votre machine hôte. Vous pouvez utiliser VirtualBox ou VMware pour créer et configurer cette VM.

## Prérequis

  Télécharger et installer VirtualBox ou VMware.
  
  Téléchargez une ISO de la distribution Linux que vous avez choisie (Debian ou CentOS).

## Étapes d'installation

    Création de la VM :
        Créez une machine virtuelle dans VirtualBox ou VMware.
        Allouez au minimum 1024 Mo de RAM.
        Choisissez un disque dur de type Dynamically Allocated d'au moins 8 Go.

    Installation de l'OS :
        Démarrez la VM avec l'ISO de la distribution choisie.
        Suivez les étapes d'installation de votre distribution, configurez les partitions comme demandé dans le projet.

    Post-installation :
        Créez un utilisateur ayant des droits sudo, avec des restrictions pour renforcer la sécurité.
        Configurez le pare-feu UFW ou firewalld selon votre distribution.
        Mettez en place le service SSH sécurisé et limitez les accès.
        Installez fail2ban pour protéger le serveur contre les tentatives de brute force.

## Utilisation

Une fois le serveur configuré, vous pouvez tester les éléments suivants :

SSH : Connectez-vous à distance à votre serveur en utilisant l'IP de votre VM via le protocole SSH.

Exemple :

```bash

ssh utilisateur@<adresse_ip_du_serveur>
```
UFW/Firewalld : Assurez-vous que le pare-feu est actif et ne permet que les connexions autorisées (SSH notamment).

Exemple de commandes UFW :

```bash

sudo ufw status
sudo ufw allow OpenSSH
sudo ufw enable
```
fail2ban : Vérifiez que le service fail2ban est actif pour protéger contre les tentatives de connexion non autorisées.

```bash

sudo systemctl status fail2ban
```
Automatisation : Utilisez cron pour automatiser des tâches comme la mise à jour du système ou la surveillance des logs.

## Sécurisation
### AppArmor (Debian) ou SELinux (CentOS)

Activez et configurez AppArmor ou SELinux pour sécuriser davantage votre serveur. Ces outils permettent de restreindre les accès des applications aux ressources système.

Exemple de commandes pour AppArmor :

```bash

sudo systemctl enable apparmor
sudo systemctl start apparmor
```
### Politique de mots de passe

Assurez-vous d'utiliser une politique de mots de passe robuste, en limitant la durée de vie des mots de passe et en demandant une longueur minimale.

## Contributeurs

[Adrien Cabarbaye](https://github.com/Demiaeuw)

## Licence

Ce projet est sous la licence MIT. Voir le fichier [LICENSE](LICENSE) pour plus d'informations.
