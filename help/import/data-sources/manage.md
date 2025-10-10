---
title: Gérer des sources de données
description: Naviguez dans l’interface de gestion des sources de données.
exl-id: 315501fb-26e1-436a-938d-5957ca037cd0
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 7%

---

# Gérer des sources de données

Utilisez le gestionnaire de sources de données pour créer, modifier ou désactiver des sources de données. Vous pouvez également effectuer le suivi des statuts des fichiers chargés vers les emplacements FTP des sources de données.

**[!UICONTROL Admin]** > **[!UICONTROL Tous les administrateurs]** > **[!UICONTROL Sources de données]**

Utilisez le sélecteur de suites de rapports en haut à droite pour basculer entre les suites de rapports de votre entreprise.

Cette interface comporte trois onglets principaux : **[!UICONTROL Gérer]**, **[!UICONTROL Créer]** et **[!UICONTROL Journal des fichiers]**.

## Gérer

L’onglet **[!UICONTROL Gérer]** gère toutes les sources de données créées par votre organisation. Vous pouvez afficher des informations FTP, apporter des modifications aux variables utilisées dans les fichiers de modèle ou désactiver entièrement les sources de données.

![Gérer](assets/manage.png)

La source de données la plus élevée est toujours [!UICONTROL balise web]. Cette source de données est ce que vous utilisez pour la collecte de données standard via AppMeasurement. Il ne peut pas être modifié ni désactivé.

Chaque source de données possède les options suivantes :

* **[!UICONTROL Redémarrer le traitement]** : redémarre le traitement de la source de données qui s’était précédemment arrêté en raison d’erreurs. Le traitement se poursuit jusqu’à la prochaine erreur. Data Sources interrompt le traitement d’un fichier de sources de données uniquement lorsque vous sélectionnez **[!UICONTROL Arrêter le traitement en cas d’erreur]**.
* **[!UICONTROL Traitement terminé]** : n’est plus utilisé - ce bouton était uniquement utilisé pour [Sources de données à traitement complet](full-processing-eol.md).
* **[!UICONTROL Arrêter le traitement en cas d’erreur]** : une case à cocher qui indique au serveur de traitement de s’arrêter lorsqu’il rencontre une erreur. La source de données ne reprend pas le traitement tant que vous n’avez pas sélectionné **[!UICONTROL Redémarrer le traitement]**. Lorsqu’une source de données rencontre une erreur de fichier, elle vous informe de l’erreur. Adobe déplace le fichier contenant l’erreur dans un dossier appelé `files_with_errors` sur le serveur FTP. Une fois le problème résolu, renvoyez le fichier pour traitement.
* **[!UICONTROL Configurer]** : lien qui vous guide tout au long de l’assistant de création de sources de données pour cette source de données. Cet assistant vous permet de renommer la source de données ou de reconfigurer les variables automatiquement incluses lors du téléchargement d’un fichier de modèle.
* **[!UICONTROL Informations FTP]** : lien qui vous mène à la dernière étape de l’assistant de création de sources de données dans laquelle les informations d’identification FTP s’affichent.

Une fois qu’une source de données reçoit des données, une table contenant plusieurs colonnes pour les fichiers chargés s’affiche.

* **[!UICONTROL Fichiers dans la file d’attente de traitement]** : nom du fichier.
* **[!UICONTROL Lignes]** : nombre total de lignes dans le fichier.
* **[!UICONTROL Erreurs]** : nombre de lignes contenant des erreurs et n’ayant pas pu être ingérées.
* **[!UICONTROL Avertissements]** : nombre de lignes contenant des avertissements.
* **[!UICONTROL Reçu]** : la date et l’heure de réception du fichier dans le fuseau horaire de la suite de rapports.
* **[!UICONTROL Statut]** : statut du fichier (`Success` ou `Failed`).

## Créer

L’onglet **[!UICONTROL Créer]** vous donne un point de départ pour l’assistant de création de sources de données.

![Créer](assets/create.png)

La catégorie et le type de source de données étaient plus précieux dans les versions précédentes d’Adobe Analytics. Cependant, leur utilisation reste limitée :

* Le type de source de données s’affiche dans les onglets [Gérer](#manage) pour la source de données elle-même et [Journal des fichiers](#file-log) pour chaque fichier individuel.
* Certains types de sources de données incluent automatiquement des variables lors du téléchargement du fichier de modèle. Cependant, vous pouvez inclure n’importe quelle dimension ou mesure disponible à condition qu’elle respecte le [format de fichier](file-format.md) établi.

Au-delà de ces raisons, toutes les catégories et tous les types de sources de données que vous pouvez choisir sont identiques. Sélectionnez la catégorie et le type qui correspondent le mieux à votre objectif d’utilisation des sources de données.

Le retrait de [sources de données à traitement complet](full-processing-eol.md) rend impossible la sélection de plusieurs catégories et types. Si vous sélectionnez un type de source de données à traitement complet, le bouton **[!UICONTROL Activer]** est grisé.

## Journal des fichiers

L’onglet **[!UICONTROL Journal des fichiers]** vous donne une vue agrégée de tous les fichiers de source de données chargés pour la suite de rapports donnée.

![Journal des fichiers](assets/file-log.png)

Une barre de recherche est disponible pour vous aider à localiser une source de données spécifique. Le tableau présente les colonnes suivantes :

* **[!UICONTROL Data Source Name]** : nom de la source de données.
* **[!UICONTROL Type]** : le type de la source de données.
* **[!UICONTROL Nom de fichier]** : le nom du fichier qui a été chargé.
* **[!UICONTROL Lignes]** : nombre total de lignes dans le fichier.
* **[!UICONTROL Erreurs]** : nombre de lignes contenant des erreurs.
* **[!UICONTROL Avertissements]** : n’est plus utilisé. Nombre de lignes contenant des avertissements.
* **[!UICONTROL Reçu]** : date et heure auxquelles Adobe a commencé à traiter le fichier.
* **[!UICONTROL Statut]** : le statut du fichier (`Success` ou `Failed`).
