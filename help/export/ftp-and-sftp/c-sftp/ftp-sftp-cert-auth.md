---
description: La connexion sans mot de passe à un compte FTP est possible seulement s’ils utilisent tous deux une connexion SFTP et une autre méthode d’authentification. Ceci implique deux fichiers (l’un sur le compte FTP et l’autre sur votre ordinateur), appelés combinaison de clés publique/privée.
keywords: ftp;sftp
title: Connexion à Adobe via SFTP sans mot de passe
uuid: 88728309-50d2-450b-b0e6-7dcdf61b5dbc
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Connexion à Adobe via SFTP sans mot de passe

La connexion sans mot de passe à un compte FTP est possible seulement s’ils utilisent tous deux une connexion SFTP et une autre méthode d’authentification. Ceci implique deux fichiers (l’un sur le compte FTP et l’autre sur votre ordinateur), appelés combinaison de clés publique/privée.

Cette méthode d’authentification n’est pas moins sécurisée qu’avec un mot de passe. Il s’agit d’une autre forme d’authentification qui n’oblige pas l’utilisateur à saisir son mot de passe à chaque fois. Si cette méthode est correctement utilisée, cet ordinateur particulier peut accéder aux fichiers sans avoir à spécifier un mot de passe. Ceci doit être configuré individuellement sur chaque ordinateur. Toutes les autres connexions qui n’utilisent pas ces fichiers clés doivent spécifier un mot de passe.

Certains clients nécessitent un protocole SFTP (protocole de transfert de fichiers sécurisé) pour la transmission de données sensibles. Une connexion SFTP est plus sécurisée qu’une connexion FTP standard, car elle permet la communication de données chiffrées. Par défaut, tous les comptes FTP Adobe sont compatibles avec le protocole SFTP. Une connexion SFTP peut être ouverte avec un nom d’utilisateur et un mot de passe valides, en utilisant un client SFTP qui se connecte au port 22 (les connexions FTP standard non sécurisées utilisent le port 21).

Lors de l’utilisation du protocole SFTP, il est possible, dans certains cas, d’utiliser des clés privées pour se connecter au compte sans mot de passe. Grâce à cette méthode, votre ordinateur utilise les fichiers clés pour s’authentifier, plutôt que de recourir à l’authentification usuelle par mot de passe. Ceci signifie que seul l’ordinateur qui possède la clé privée peut se connecter sans mot de passe. Tous les autres ordinateurs/utilisateurs doivent continuer à s’authentifier par mot de passe (sauf si des clés privées ont été configurées également sur ces ordinateurs).

**Configuration et utilisation de clés privées pour une authentification sans mot de passe**

1. Compte FTP créé (Adobe).

   Un représentant Adobe peut créer un compte FTP si vous n’en avez pas déjà un. Contactez votre gestionnaire de compte Adobe ou l’assistance clientèle Adobe pour qu’un compte soit créé.
1. Création de clés publique/privée (client).

   Créez une combinaison de clés publique/privée. La clé privée est un fichier privé qui réside sur votre ordinateur ou serveur et qui y est propre. Le fichier de clé publique doit être transféré sur le compte Adobe. Avec cette méthode, vous pouvez vous connecter sans authentification par mot de passe. Le fichier de clé publique côté Adobe correspond au fichier de clé privée sur votre ordinateur/serveur et s’authentifie de cette façon.

   Pour créer ces fichiers, demandez à votre groupe d’assistance réseau interne de créer un jeu de clés adapté à votre environnement. De nombreux outils et applications peuvent servir à créer ces deux fichiers.

   Vous trouverez ci-dessous un exemple de la façon de procéder dans un environnement Shell UNIX. Cet exemple illustre la manière dont il est possible de procéder et peut servir de référence pour communiquer vos exigences à votre équipe ou groupe réseau interne.

   ```
   // Linux/Unix (bash shell)
   
   // First make sure the ".ssh" directory exists
   
   $ mkdir ~/.ssh
   
   $ cd ~/.ssh
   
   // Now actually generate the key pair
   
   // Usually we will want to create an empty passphrase (just hit "Enter" for both password prompts)
   
   $ ssh-keygen -q -t dsa
   
   Enter file in which to save the key (/home/user/.ssh/id_dsa):
   
   Enter passphrase (empty for no passphrase): ...
   
   Enter same passphrase again: ...
   
   // Rename or copy the public key file to "authorized_keys"
   
   // This "authorized_keys" file is the one that we will upload to the Adobe FTP server in step 3
   
   $ cp id_dsa.pub authorized_keys 
   ```

1. Transfert de la clé publique sur le compte FTP (client).

   Transférez et testez la clé publique. Connectez-vous au compte FTP Adobe et créez un répertoire [!DNL .ssh], s’il n’existe pas déjà. Chargez le fichier [!DNL authorized_keys] dans le répertoire [!DNL .ssh]. Vous pouvez le faire de différentes façons (ligne de commande, client FTP graphique, etc.). Il suffit d’avoir la capacité de créer un répertoire et de transférer un fichier.

   Voici un exemple en utilisant un Shell UNIX.

   ```
   $ ftp ftp.Adobe.com
   
   OR (depending on hostname provided by Adobe)
   
   $ ftp ftp2.Adobe.com
   
   // Enter username and password for account as prompted
   
   ftp> mkdir .ssh
   
   ftp> cd .ssh
   
   ftp> put authorized_keys
   
   ftp> exit
   
   // Now test the connection by logging in to the server using "sftp" command:
   
   $ sftp username@ftp.omniture.com
   
   OR (depending on hostname provided by Adobe)
   
   $ sftp username@ftp2.omniture.com
   
   // You should immediately receive an sftp prompt without having to enter the password:
   
   sftp>
   ```

