---
description: Instructions pour configurer un transfert sécurisé avec des serveurs FTP Adobe.
keywords: ftp;sftp
title: Connexion à un compte FTP Adobe par SFTP
uuid: 4faf27b8-7276-4c68-87cb-35802b809e27
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Connexion à un compte FTP Adobe par SFTP

Instructions pour configurer un transfert sécurisé avec des serveurs FTP Adobe.

1. Demandez un compte FTP hébergé par Adobe (quota de 50 Mo).
1. Créez des clés RSA publique/privée. Sous Linux, exécutez :

   ```
   ssh-keygen -t rsa
   ```

   Dans un environnement Windows, créez les clés à l’aide de puttyGen.

1. Create a file named [!DNL authorized_keys] (no extension).
1. Copy the contents of the Public key into [!DNL authorized_keys].
1. Upload [!DNL authorized_keys] to an FTP account:

   * Connectez-vous au compte FTP Adobe.
   * Create a [!DNL .ssh] directory (if it does not already exist).
   * Upload the [!DNL authorized_keys] file to the [!DNL .ssh] directory.

1. Testez la connexion en vous connectant au compte FTP à l’aide de SFTP.

[Pour plus d’informations, voir ](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)Comment se connecter à Adobe par sFTP sans mot de passe_....
