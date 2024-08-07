---
title: Gestion des sources de données
description: Accédez à l’interface de gestion des sources de données .
exl-id: 315501fb-26e1-436a-938d-5957ca037cd0
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 7%

---

# Gestion des sources de données

Utilisez le gestionnaire de sources de données pour créer, modifier ou désactiver des sources de données. Vous pouvez également effectuer le suivi des statuts des fichiers chargés vers les emplacements FTP des sources de données.

**[!UICONTROL Admin]** > **[!UICONTROL Tous les administrateurs]** > **[!UICONTROL Sources de données]**

Utilisez le sélecteur de suite de rapports dans la partie supérieure droite pour basculer entre les suites de rapports de votre entreprise.

Cette interface comporte trois onglets principaux : **[!UICONTROL Gérer]**, **[!UICONTROL Créer]** et **[!UICONTROL Journal des fichiers]**.

## Gérer

L’onglet **[!UICONTROL Gérer]** traite toutes les sources de données que votre entreprise a créées. Vous pouvez afficher des informations sur le FTP, apporter des modifications aux variables utilisées dans les fichiers de modèle ou désactiver entièrement les sources de données.

![Gérer](assets/manage.png)

La source de données la plus élevée est toujours [!UICONTROL Balise Web]. Cette source de données est ce que vous utilisez pour la collecte de données classique par AppMeasurement. Il ne peut pas être modifié ni désactivé.

Chaque source de données dispose des options suivantes :

* **[!UICONTROL Redémarrer le traitement]** : redémarre le traitement de la source de données précédemment interrompu en raison d’erreurs. Le traitement se poursuit jusqu’à la prochaine erreur. La fonctionnalité Sources de données interrompt le traitement d’un fichier de source de données uniquement lorsque vous sélectionnez **[!UICONTROL Arrêter le traitement en cas d’erreur]**.
* **[!UICONTROL Terminer le traitement]** : ce bouton n’était plus utilisé ; il n’était utilisé que pour les [sources de données à traitement complet](full-processing-eol.md).
* **[!UICONTROL Arrêter le traitement en cas d’erreur]** : une case à cocher qui indique au serveur de traitement de s’arrêter en cas d’erreur. La source de données ne reprend le traitement que lorsque vous sélectionnez **[!UICONTROL Redémarrer le traitement]**. Lorsqu’une source de données rencontre une erreur de fichier, elle vous en informe. Adobe déplace le fichier contenant l’erreur dans un dossier appelé `files_with_errors` sur le serveur FTP. Une fois le problème résolu, renvoyez le fichier pour traitement.
* **[!UICONTROL Configurer]** : lien qui vous guide tout au long de l’assistant de création de sources de données pour cette source de données. Cet assistant vous permet de renommer la source de données ou de reconfigurer automatiquement les variables incluses lors du téléchargement d’un fichier de modèle.
* **[!UICONTROL Infos FTP]** : lien permettant d’accéder à la dernière étape de l’assistant de création de sources de données où s’affichent les informations d’identification FTP.

Une fois qu’une source de données reçoit des données, un tableau s’affiche contenant plusieurs colonnes pour les fichiers chargés.

* **[!UICONTROL Fichiers dans la file d’attente de traitement]** : nom du fichier.
* **[!UICONTROL Lignes]** : nombre total de lignes dans le fichier.
* **[!UICONTROL Erreurs]** : nombre de lignes contenant des erreurs et n’ayant pas pu être ingérées.
* **[!UICONTROL Avertissements]** : nombre de lignes contenant des avertissements.
* **[!UICONTROL Reçu]** : horodatage de réception du fichier dans le fuseau horaire de la suite de rapports.
* **[!UICONTROL Status]** : état du fichier (`Success` ou `Failed`).

## Créer

L’onglet **[!UICONTROL Créer]** vous donne un point de départ pour l’assistant de création de sources de données.

![Créer](assets/create.png)

La catégorie et le type de source de données étaient plus précieux dans les versions précédentes d’Adobe Analytics. Toutefois, leur utilisation reste limitée :

* Le type de source de données s’affiche dans l’onglet [Gérer](#manage) pour la source de données elle-même et dans l’onglet [Journal du fichier](#file-log) pour chaque fichier.
* Certains types de sources de données incluent automatiquement des variables lors du téléchargement du fichier de modèle. Cependant, vous pouvez inclure n’importe quelle dimension ou mesure disponible tant qu’elle respecte le [format de fichier](file-format.md) établi.

Au-delà de ces raisons, toutes les catégories et tous les types de sources de données que vous pouvez sélectionner sont effectivement identiques. Sélectionnez la catégorie et le type qui représentent le mieux votre objectif d’utilisation des sources de données.

Avec la suppression de [sources de données à traitement complet](full-processing-eol.md), plusieurs catégories et types ne peuvent pas être sélectionnés. Si vous sélectionnez un type de source de données à traitement complet, le bouton **[!UICONTROL Activer]** est grisé.

## Journal des fichiers

L’onglet **[!UICONTROL Journal des fichiers]** vous donne une vue globale de tous les fichiers de source de données chargés pour la suite de rapports donnée.

![Journal des fichiers](assets/file-log.png)

Une barre de recherche est disponible pour vous aider à localiser une source de données spécifique. Le tableau présente les colonnes suivantes :

* **[!UICONTROL Data Source Name]** : nom de la source de données.
* **[!UICONTROL Type]** : type de la source de données.
* **[!UICONTROL Nom de fichier]** : nom du fichier qui a été chargé.
* **[!UICONTROL Lignes]** : nombre total de lignes dans le fichier.
* **[!UICONTROL Erreurs]** : nombre de lignes contenant des erreurs.
* **[!UICONTROL Avertissements]** : n’est plus utilisé. Nombre de lignes contenant des avertissements.
* **[!UICONTROL Reçu]** : date et heure auxquelles l’Adobe a commencé à traiter le fichier.
* **[!UICONTROL Status]** : état du fichier (`Success` ou `Failed`).
