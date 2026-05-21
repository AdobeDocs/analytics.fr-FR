---
description: Instructions pour configurer un transfert sécurisé avec des serveurs FTP Adobe.
keywords: ftp;sftp
title: Connexion à un compte FTP Adobe par SFTP
feature: FTP Export
exl-id: 727d4f7a-d7d1-40cf-bdcd-c783ca47f51c
TQID: https://experienceleague.adobe.com/uXtJtDP58tSIzb9AvoAknAYoMt7SknJSgxRKNgIAXM8
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 214
ht-degree: 38%

---

# Connexion à un compte FTP par SFTP

Pour configurer un transfert sécurisé avec FTP :

1. (Conditionnel) Si vous souhaitez configurer un transfert sécurisé avec des serveurs FTP Adobe :

   1. Demandez un compte FTP hébergé par Adobe (quota de 50 Mo).

   1. Créer des clés publiques/privées.

      * Dans l’environnement Linux, exécutez :

        ```
        ssh-keygen -t ed25519 -C "your-comment-or-email"
        ```

        Si votre politique ne vous permet pas d’utiliser ed25519, exécutez :

        ```
        ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
        ```

        **Remarque :** cela s&#39;applique généralement aux clients qui opèrent sous FIPS 186-4, comme ed25519 est d&#39;abord pris en charge dans le FIPS 186-5 plus récent.

      * Dans un environnement Windows, utilisez puttyGen.

1. (Conditionnel) Si vous souhaitez configurer un transfert sécurisé avec votre propre emplacement FTP, vous devez disposer d’un hôte SFTP, d’un nom d’utilisateur et du site de destination contenant une clé publique RSA ou ed25519 valide. Vous pouvez télécharger la clé publique appropriée à la création du flux.

1. Créez un fichier nommé [!DNL `authorized_keys`] (sans extension).

1. Copiez le contenu de la clé publique dans [!DNL `authorized_keys`].

1. Chargez [!DNL `authorized_keys`] sur un compte FTP :

   * Connectez-vous au compte FTP Adobe.
   * Créez un répertoire [!DNL .ssh] (s’il n’existe pas déjà).
   * Chargez le fichier [!DNL `authorized_keys`] dans le répertoire [!DNL .ssh].

1. Testez la connexion en vous connectant au compte FTP par SFTP.

Pour plus d’informations, voir [ Connexion à Adobe via SFTP sans mot de passe ](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md).

