---
description: Instructions pour configurer un transfert sécurisé avec des serveurs FTP Adobe.
keywords: ftp ; sftp
seo-description: Instructions pour configurer un transfert sécurisé avec des serveurs FTP Adobe.
seo-title: Connexion à un compte FTP Adobe avec SFTP
solution: Analytics
title: Connexion à un compte FTP Adobe avec SFTP
uuid: 4 faf 27 b 8-7276-4 c 68-87 cb -35802 b 809 e 27
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Connexion à un compte FTP Adobe avec SFTP

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

1. Testez la connexion en vous connectant au compte FTP à l'aide du protocole SFTP.

For more detailed information, see [How to Connect to Adobe via sFTP Without a Password_...](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md#concept_962A381F42A4472AA366A08CCC962846).
