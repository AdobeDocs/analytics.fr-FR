---
description: Procédure de transfert d’un fichier de sources de données.
subtopic: Data sources
title: Transfert d’un fichier de sources de données
topic: Developer and implementation
uuid: 5a9dde91-1297-47e5-9393-611b40413c17
translation-type: tm+mt
source-git-commit: fb2a63432275c4ab621df263035400051ff6bb32
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 87%

---


# Transfert d’un fichier de sources de données

Une fois le fichier de données préparé, envoyez-le à la fonctionnalité Sources de données pour traitement. Adobe gère plusieurs serveurs FTP de sources de données, où vous pouvez transférer vos fichiers. Gardez à l’esprit ce qui suit au sujet des serveurs FTP de sources de données :

* Sélectionnez Infos FTP en regard de l’entrée de source de données dans l’onglet [!UICONTROL Gérer les sources de données] afin d’obtenir les informations relatives à l’hôte, à l’identifiant et au mot de passe FTP pour le compte FTP de la source de données. Quiconque ayant accès à ces informations peut transférer des données dans votre suite de rapports.
* Pour des raisons de sécurité, les comptes FTP sont fermés après 30 jours d’inactivité.
* Les comptes FTP sont spécifiques à une source de données. Vous ne pouvez pas utiliser un compte FTP pour transférer des fichiers de sources de données vers plusieurs sources de données.

**Transfert d’un fichier de sources de données**

1. Utilisez un client FTP pour envoyer les données vers votre site FTP de sources de données.

   (accessible dans le lien Infos FTP dans le Gestionnaire des sources de données).

1. Transférez un fichier [!DNL .fin] afin d’indiquer à Adobe que le transfert du fichier de source de données est terminé.

   Le fichier [!DNL .fin] doit être nommé exactement de la même façon que le fichier de source de données, à l’exception de son extension. Le fichier de source de données n’est pas placé en file d’attente de traitement tant que le fichier [!DNL .fin] n’est pas transféré.

   Ne transférez pas le fichier tant que tous les fichiers de sources de données ne sont pas complètement transférés. Sinon, les sources de données peuvent tenter de traiter un fichier incomplet.
1. Une fois le fichier .fin téléchargé, il est important de se déconnecter du site FTP Sources de données. La raison en est qu’Analytics utilise des événements de déconnexion comme déclencheur pour indiquer que les fichiers sont prêts pour le traitement.
1. Vérifiez la présence éventuelle de messages durant le traitement du fichier de source de données.

   Le Gestionnaire des sources de données affiche des erreurs qui surviennent durant le traitement des fichiers.

