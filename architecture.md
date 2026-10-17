
# Contexte

Ce projet a pour objectif de concevoir, déployer, sécuriser et automatiser une infrastructure informatique d’entreprise réaliste.
L’infrastructure simule l’environnement informatique d’une petite entreprise en s’appuyant sur la virtualisation, des serveurs Linux, la segmentation réseau, 
la sécurisation des communications par pare-feu et l’automatisation des tâches d’administration.


# Composants de l'architecture IT de la PME

## Pare-feu
- hostname: fw-01
- Technologies utilisées : OPNsense
Rôle : Routage réseau et sécurité

## Serveur d'administration
- hostname: bastion01
- OS: Debian Linux
- Adresse IP : 10.10.10.10
- Rôle : Administration sécurisée via SSH

## Serveur applicatif
- hostname: app01
- OS: Debian Linux
- Adresse IP : 10.20.20.10
- Application : Nginx, application Python

## Serveur de base de données
- hostname: db01
- OS: Debian Linux
- Adresse IP : 10.30.30.10
- Application : PostgreSQL

#  Segmentation réseau


| Réseau | Sous-réseau | Fonction |
|--------|-------------|----------|
| ADMIN | 10.10.10.0/24 | Administration |
| DMZ | 10.20.20.0/24 | Hébergement de l'application |
| SERVERS | 10.30.30.0/24 | Base de données |

## 4. Principes de sécurité

- Segmentation du réseau en plusieurs zones distinctes (Admin, DMZ, Servers)
- Application d'une politique de pare-feu restrictive (par défaut ce sera refus)
- Authentification SSH par clés cryptographiques
- Restriction des accès à la base de données
- Administration sécurisée des serveurs via un bastion SSH



# Ansible permettra d'automatiser les tâches suivantes :

- Configuration des systèmes Linux
- Gestion des utilisateurs et des permissions
- Configuration et sécurisation des accès SSH
- Installation et mise à jour des paquets
- Déploiement de l'application
- Configuration des paramètres de sécurité
