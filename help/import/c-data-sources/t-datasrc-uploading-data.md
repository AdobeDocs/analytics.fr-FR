---
description: Procédure de transfert d’un fichier de sources de données.
seo-description: Procédure de transfert d’un fichier de sources de données.
seo-title: Transfert d'un fichier de sources de données
solution: Analytics
subtopic: Sources de données
title: Transfert d'un fichier de sources de données
topic: Développeur et mise en œuvre
uuid: 5 a 9 dde 91-1297-47 e 5-9393-611 b 40413 c 17
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Transfert d'un fichier de sources de données

Procédure de transfert d’un fichier de sources de données.

Une fois le fichier de données préparé, envoyez-le à la fonctionnalité Sources de données pour traitement. Adobe gère plusieurs serveurs FTP de sources de données, où vous pouvez transférer vos fichiers. Gardez à l’esprit ce qui suit au sujet des serveurs FTP de sources de données :

* Sélectionnez Infos FTP en regard de l’entrée de source de données dans l’onglet [!UICONTROL Gérer les sources de données] afin de connaître les renseignements relatifs à l’hôte, à l’identifiant et au mot de passe FTP pour le compte FTP de la source de données. Quiconque ayant accès à ces informations peut transférer des données dans votre suite de rapports.
* Pour des raisons de sécurité, les comptes FTP sont fermés après 30 jours d’inactivité.
* Les comptes FTP sont spécifiques à une source de données. Vous ne pouvez pas utiliser un compte FTP pour transférer des fichiers de sources de données vers plusieurs sources de données.

**Transfert d’un fichier de sources de données**

1. Utilisez un client FTP pour envoyer les données vers votre site FTP de sources de données.

   (accessible dans le lien Infos FTP dans le Gestionnaire des sources de données).

1. Upload a [!DNL .fin] file to notify Adobe that the Data Sources file upload is complete.

   [!DNL .fin] Le fichier doit porter le même nom que le fichier de sources de données, à l'exception de l'extension de fichier. Adobe does not queue the Data Sources file for processing until you upload the [!DNL .fin] file.

   Ne transférez pas le fichier tant que tous les fichiers de sources de données ne sont pas complètement transférés. Sinon, les sources de données peuvent tenter de traiter un fichier incomplet.
1. Vérifiez la présence éventuelle de messages durant le traitement du fichier de source de données.

   Le Gestionnaire des sources de données affiche des erreurs qui surviennent durant le traitement des fichiers.

