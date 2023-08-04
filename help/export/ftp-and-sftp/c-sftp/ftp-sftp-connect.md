---
description: Instructions pour configurer un transfert sécurisé avec des serveurs FTP Adobe.
keywords: ftp;sftp
title: Connexion à un compte FTP Adobe par SFTP
feature: FTP Export
exl-id: 727d4f7a-d7d1-40cf-bdcd-c783ca47f51c
source-git-commit: 62132284ca70f3bdb1a8896e4548b8b63a5c03c8
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 64%

---

# Connexion à un compte FTP par SFTP

Pour configurer le transfert sécurisé par FTP :

1. (Conditionnel) Si vous souhaitez configurer un transfert sécurisé avec des serveurs FTP Adobes :

   1. Demandez un compte FTP hébergé par Adobe (quota de 50 Mo).

   1. Créez des clés RSA publique/privée.

      * Dans un environnement Linux, exécutez :

        ```
        ssh-keygen -t rsa
        ```

      * Dans un environnement Windows, utilisez puttyGen.

1. (Conditionnel) Si vous souhaitez configurer un transfert sécurisé avec votre propre emplacement FTP, vous devez disposer d’un hôte SFTP, d’un nom d’utilisateur et d’un site de destination contenant une clé publique RSA ou DSA valide. Vous pouvez télécharger la clé publique appropriée à la création du flux.

1. Créez un fichier nommé [!DNL authorized_keys] (sans extension).

1. Copiez le contenu de la clé publique dans [!DNL authorized_keys].

1. Chargez [!DNL authorized_keys] sur un compte FTP :

   * Connectez-vous au compte FTP Adobe.
   * Créez un répertoire [!DNL .ssh] (s’il n’existe pas déjà).
   * Chargez le fichier [!DNL authorized_keys] dans le répertoire [!DNL .ssh].

1. Testez la connexion en vous connectant au compte FTP par SFTP.

Pour plus d’informations, consultez [Comment se connecter à Adobe par SFTP sans mot de passe_...](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md).
