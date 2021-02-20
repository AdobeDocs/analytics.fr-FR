---
description: Le Report Builder Adobe propose désormais des paramètres de gestion des autorisations analogues à ceux des Outils d’administration d’Analytics.
title: Autorisations d’accès utilisateur pour les dimensions et les mesures
topic: Report builder
uuid: b561407d-c4fa-4f1e-8b16-5ca46fcbf36f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 100%

---


# Autorisations d’accès utilisateur pour les dimensions et les mesures

Le Report Builder Adobe propose désormais des paramètres de gestion des autorisations analogues à ceux des Outils d’administration d’Analytics.

En tant qu’utilisateur non administrateur, vous avez peut-être créé antérieurement des classeurs avec des requêtes pointant vers des dimensions et des mesures auxquelles vous n’avez pas accès. Ces autorisations sont maintenant appliquées.

Par exemple, si vous actualisez une requête qui inclut des dimensions ou des mesures auxquelles vous n’avez pas accès, vous obtenez une erreur d’autorisation limitée (Restricted Permission Error) :

![](assets/arb_restrc_perm.png)

Suivez ces instructions pour **chaque** classeur du Report Builder que vous conservez :

1. Ouvrez le classeur.
1. Actualisez toutes les requêtes.
1. Si une erreur d’autorisation d’accès utilisateur s’affiche, cliquez sur **[!UICONTROL Ouvrir un fichier CSV (Open CSV File)]** pour accéder à la liste des erreurs d’autorisation limitée.
1. Créez un fichier « AllRestrictedPermissionErrors.xlsx » et copiez/collez la liste des erreurs d’autorisation limitée du fichier CSV vers ce fichier.
1. Fermez le classeur du Report Builder.

Une fois que vous avez traité tous les classeurs, vous devez avoir une liste complète des erreurs d’autorisation limitée dans « AllRestrictedPermissionErrors.xlsx ». Envoyez cette liste à votre administrateur d’accès utilisateur Adobe Analytics en lui demandant de vous octroyer l’accès aux mesures et dimensions.
