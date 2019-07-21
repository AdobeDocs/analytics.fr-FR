---
description: Adobe prend en charge l'exportation de demandes d'entrepôt de données vers les serveurs SFTP.
keywords: ftp ; sftp
seo-description: Adobe prend en charge l'exportation de demandes d'entrepôt de données vers les serveurs SFTP.
seo-title: Envoi de demandes d'entrepôt de données aux serveurs SFTP
solution: Analytics
title: Envoi de demandes d'entrepôt de données aux serveurs SFTP
uuid: 393634 a 1-0643-4 d 63-bb 6 e-fb 80 f 1 ba 76 c 1
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Envoi de demandes d'entrepôt de données aux serveurs SFTP

Adobe prend en charge l'exportation de demandes d'entrepôt de données vers les serveurs SFTP.

Veillez à accomplir les tâches suivantes :

Adobe prend en charge l'exportation des demandes d'entrepôt de données vers les serveurs SFTP, à condition que les éléments suivants soient satisfaits :

* [!DNL sftp://] est spécifié dans le champ hôte (par exemple, [!DNL sftp://ftp.example.com]) et que seul le port 22 est utilisé lors de la demande d'un rapport Entrepôt de données.

   You can also use the [!DNL sftp+norename://] option, as described below.

* [!DNL authorized_keys] Le fichier Adobe se trouve dans [!DNL .ssh] le répertoire du répertoire racine de l'utilisateur auquel vous vous connectez.

* La destination ne figure pas sur [!DNL ftp.omniture.com]. Le protocole sFTP entre les serveurs internes d’Adobe n’est pas pris en charge.
* La destination prend en charge l’authentification à un facteur (PKI). S’il y a deux facteurs, le rapport ne sera pas remis. Vérifiez que le serveur n’est pas configuré pour une authentification à deux facteurs. Avec Adobe Analytics, seule cette clé est nécessaire pour se connecter.
* Adobe prend en charge le chiffrement SSHv2 et revient à SSHv1 (clé RSA seulement).

To successfully send a [!DNL Data Warehouse] request via SFTP:

1. Récupérez le fichier [!DNL authorized_keys] en demandant à la personne habilitée à le faire de contacter l’assistance clientèle.
1. After this file is obtained, log in to the FTP site under the same credentials that are used for the [!DNL Data Warehouse] request.
1. In the root directory, navigate to the folder named [!DNL .ssh] (if one does not exist, create one) and place the [!DNL authorized_keys] file there.

1. Go to the [!DNL Data Warehouse] request manager. Configurez la demande, puis cliquez sur **[!UICONTROL Options de remise avancées]**.

1. In the pop-up window, click **[!UICONTROL FTP]**, then specify the ftp site (including the [!DNL sftp://] protocol, such as [!DNL sftp://ftp.omniture.com]) via port 22.

   Including the [!DNL sftp://] protocol is only permitted when using SFTP. Regular FTP requests should omit the protocol prefix (such as, [!DNL ftp.omniture.com] instead of [!DNL ftp://ftp.omniture.com]).

1. Entrez le nom du dossier dans lequel placer le fichier dans le champ Folder (Dossier). Un dossier est requis.
1. Entrez les mêmes nom d’utilisateur et mot de passe que ceux utilisés à l’étape 2.
1. Cliquez sur **[!UICONTROL Envoyer]**.

La commande sftp PUT place un fichier temporaire avec une extension .part dans le répertoire spécifié. Une fois le transfert terminé, l’extension de fichier est renommée en extension finale ; le fichier est alors prêt à être utilisé.

Alternatively, [!DNL sftp+norename://] can be specified instead of [!DNL sftp://] to upload the file directly with the final name, without a temporary [!DNL .part] file name during upload. Cette approche est appropriée lorsque le serveur SFTP gère le changement de nom du fichier lors du téléchargement automatique et qu'il n'y a aucune probabilité que le fichier en cours de traitement soit traité avant le transfert.
