---
description: Instructions pour configurer un transfert sécurisé avec des serveurs FTP Adobe.
keywords: ftp;sftp
title: Connexion à un compte FTP Adobe par SFTP
feature: FTP Export
exl-id: 727d4f7a-d7d1-40cf-bdcd-c783ca47f51c
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: ht
source-wordcount: '134'
ht-degree: 100%

---

# Connexion à un compte FTP Adobe par SFTP

Instructions pour configurer un transfert sécurisé avec des serveurs FTP Adobe.

1. Demandez un compte FTP hébergé par Adobe (quota de 50 Mo).
1. Créez des clés RSA publique/privée. Sous Linux, exécutez :

   ```
   ssh-keygen -t rsa
   ```

   Dans un environnement Windows, créez les clés à l’aide de puttyGen.

1. Créez un fichier nommé [!DNL authorized_keys] (sans extension).
1. Copiez le contenu de la clé publique dans [!DNL authorized_keys].
1. Chargez [!DNL authorized_keys] sur un compte FTP :

   * Connectez-vous au compte FTP Adobe.
   * Créez un répertoire [!DNL .ssh] (s’il n’existe pas déjà).
   * Chargez le fichier [!DNL authorized_keys] dans le répertoire [!DNL .ssh].

1. Testez la connexion en vous connectant au compte FTP par SFTP.

Pour plus d’informations, consultez [Comment se connecter à Adobe par SFTP sans mot de passe_...](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md).
