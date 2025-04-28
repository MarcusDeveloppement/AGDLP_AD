# Projet : Mise en place Active Directory avec AGDLP

## Objectif du projet

Créer une infrastructure Active Directory sous environnement virtualisé (VMware) en appliquant la méthode AGDLP afin de structurer la gestion des accès aux ressources réseau de manière professionnelle, sécurisée et évolutive.

## 🛠 Technologies utilisées

- VMware Workstation
- Windows Server 2025 (Active Directory)
- Windows 10 (Client)
- DNS intégré à Active Directory
- Système de fichiers NTFS
- Méthode AGDLP (Accounts - Global Groups - Domain Local Groups - Permissions)

## Pourquoi utiliser AGDLP ?

L'utilisation de la méthode AGDLP permet :

- Une meilleure **visibilité** et **contrôle** des accès aux ressources,
- Une **réduction des erreurs** humaines lors des mouvements internes,
- Une **maintenance simplifiée** de l’infrastructure,
- Une **meilleure sécurité** réseau et une **auditabilité** optimale,
- Une **scalabilité** adaptée aux petites et grandes entreprises.

Sans AGDLP, les droits seraient attribués directement aux utilisateurs, rendant la maintenance complexe et risquée.  
Avec AGDLP, les utilisateurs sont ajoutés dans des Groupes Globaux, qui eux-mêmes reçoivent les permissions via des Groupes Locaux, garantissant une structure claire et évolutive.

## Étapes du projet

### 1. Installation et configuration réseau

- Installation de Windows Server et Windows 10.
- Configuration IP fixe sur le serveur et le client.
- Définition du serveur lui-même comme serveur DNS.

### 2. Installation de l'Active Directory et DNS

- Installation du rôle Active Directory Domain Services (AD DS) et DNS Server.
- Promotion du serveur en tant que Contrôleur de Domaine (Domaine : `marctech.fr`).
- Le serveur Active Directory agit également comme serveur DNS interne.

### 3. Création des OU et des utilisateurs

- Mise en place d'une structure propre avec des Unités d'Organisation (OU) par service.
- Création des utilisateurs dans leur OU respective.

### 4. Ajout d'un disque supplémentaire pour les partages

- Ajout d’un second disque (E:) pour éviter d'utiliser le disque système (C:).
- Séparation des données et du système pour des raisons de performances, sécurité et facilité de sauvegarde.

### 5. Création des Groupes GL et DL

- Groupes Globaux (`GL_`) : pour les utilisateurs par service (Marketing, Compta, etc.).
- Groupes Locaux (`DL_`) : pour l'attribution des droits d'accès sur les ressources.

### 6. Mise en place des partages réseau

- Création du dossier principal `Partages` sur E:.
- Utilisation du caractère `$` pour cacher le partage (accessible uniquement en connaissant le chemin complet).

### 7. Attribution des droits NTFS

- Attribution des droits sur les dossiers uniquement via les Groupes Locaux.
- Respect des meilleures pratiques de sécurité réseau.

### 8. Tests et validation

- Vérification que les utilisateurs accèdent uniquement aux ressources autorisées.
- Confirmation de la bonne mise en œuvre du modèle AGDLP.

## Résultat

- Infrastructure sécurisée, scalable et professionnelle.
- Gestion simplifiée des utilisateurs et des ressources.
- Respect des standards IT d'administration système moderne.

## Auteur

\*Projet réalisé par :** [Marc Khamchanh]  
**Date :** 27/04/2025  
**Contexte :\*\* Projet personnel de mise en pratique des infrastructures Active Directory & Sécurité réseau.
