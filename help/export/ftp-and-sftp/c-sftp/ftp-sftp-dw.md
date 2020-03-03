---
description: Adobe prend en charge l’exportation de requêtes Data Warehouse vers les serveurs SFTP.
keywords: ftp;sftp
title: Envoi de requêtes Data Warehouse vers les serveurs SFTP
uuid: 393634a1-0643-4d63-bb6e-fb80f1ba76c1
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Envoi de requêtes Data Warehouse vers les serveurs SFTP

Adobe prend en charge l’exportation de requêtes Data Warehouse vers les serveurs SFTP.

Veillez à accomplir les tâches suivantes :

Adobe prend en charge l’exportation de requêtes Data Warehouse sur les serveurs SFTP, à condition que les critères suivants soient satisfaits :

* Le protocole [!DNL sftp://] est spécifié dans le champ hôte (par exemple, [!DNL sftp://ftp.example.com]) et SEUL le port 22 est utilisé pour demander un rapport Data Warehouse.

   Vous pouvez également utiliser l’option [!DNL sftp+norename://], comme décrit ci-dessous.

* Le fichier [!DNL authorized_keys] d’Adobe se trouve dans le répertoire [!DNL .ssh] dans le répertoire racine de l’utilisateur sous le nom duquel vous êtes connectés.

* La destination ne figure pas sur [!DNL ftp.omniture.com]. Le protocole sFTP entre les serveurs internes d’Adobe n’est pas pris en charge.
* La destination prend en charge l’authentification à un facteur (PKI). S’il y a deux facteurs, le rapport ne sera pas remis. Vérifiez que le serveur n’est pas configuré pour une authentification à deux facteurs. Avec Adobe Analytics, seule cette clé est nécessaire pour se connecter.
* Adobe prend en charge le chiffrement SSHv2 et revient à SSHv1 (clé RSA seulement).

Pour envoyer une demande [!DNL Data Warehouse] par SFTP :

1. Récupérez le fichier [!DNL authorized_keys] en demandant à la personne habilitée à le faire de contacter l’assistance clientèle.
1. Une fois ce fichier récupéré, connectez-vous au site FTP avec les mêmes identifiants que ceux utilisés pour la requête [!DNL Data Warehouse].
1. Dans le répertoire racine, naviguez jusqu’au dossier nommé [!DNL .ssh] (s’il n’existe pas, créez-le) et placez-y le fichier [!DNL authorized_keys].

1. Allez au gestionnaire de requêtes [!DNL Data Warehouse]. Configurez la demande, puis cliquez sur **[!UICONTROL Options de remise avancées]**.

1. Dans la fenêtre contextuelle, cliquez sur **[!UICONTROL FTP]**, puis spécifiez le site FTP (y compris le protocole [!DNL sftp://], par exemple [!DNL sftp://ftp.omniture.com]) par l’intermédiaire du port 22.

   La spécification du protocole [!DNL sftp://] est autorisée seulement si vous utilisez le protocole SFTP. Les demandes FTP régulières doivent omettre le préfixe de protocole (par exemple, [!DNL ftp.omniture.com] au lieu de [!DNL ftp://ftp.omniture.com]).

1. Entrez le nom du dossier dans lequel placer le fichier dans le champ Folder (Dossier). Un dossier est requis.
1. Entrez les mêmes noms d’utilisateur et mot de passe que ceux utilisés à l’étape 2.
1. Cliquez sur **[!UICONTROL Envoyer]**.

La commande sftp PUT place un fichier temporaire avec une extension .part dans le répertoire spécifié. Une fois le transfert terminé, l’extension de fichier est renommée en extension finale ; le fichier est alors prêt à être utilisé.

[!DNL sftp+norename://] peut également être spécifié au lieu de [!DNL sftp://] pour charger directement le fichier avec le nom définitif, sans nom de fichier [!DNL .part] temporaire. Cette méthode est appropriée lorsque le serveur SFTP gère automatiquement le changement de nom du fichier lors du téléchargement et qu’il n’y a aucune chance que le fichier soit traité avant la fin du transfert.
