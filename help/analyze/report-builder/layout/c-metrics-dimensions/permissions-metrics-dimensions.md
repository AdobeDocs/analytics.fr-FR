---
description: Le Créateur de rapports Adobe propose désormais des paramètres de gestion des autorisations analogues à ceux des Outils d’administration d’Analytics.
seo-description: Le Créateur de rapports Adobe propose désormais des paramètres de gestion des autorisations analogues à ceux des Outils d’administration d’Analytics.
seo-title: Autorisations d'accès utilisateur pour les dimensions et les mesures
solution: Analytics
title: Autorisations d'accès utilisateur pour les dimensions et les mesures
topic: Créateur de rapports
uuid: b 561407 d-c 4 fa -4 f 1 e -8 b 16-5 ca 46 fcbf 36 f
translation-type: tm+mt
source-git-commit: d75c58caf1220031fa36483a0ad50ea6f7be7c39

---


# Autorisations d'accès utilisateur pour les dimensions et les mesures

Le Créateur de rapports Adobe propose désormais des paramètres de gestion des autorisations analogues à ceux des Outils d’administration d’Analytics.

En tant qu’utilisateur non administrateur, vous avez peut-être créé antérieurement des classeurs avec des requêtes pointant vers des dimensions et des mesures auxquelles vous n’avez pas accès. Ces autorisations sont maintenant appliquées.

Par exemple, si vous actualisez une requête qui inclut des dimensions ou des mesures auxquelles vous n’avez pas accès, vous obtenez une erreur d’autorisation limitée (Restricted Permission Error) :

![](assets/arb_restrc_perm.png)

Suivez ces instructions pour **chaque** classeur du Créateur de rapports que vous conservez :

1. Ouvrez le classeur.
1. Actualisez toutes les requêtes.
1. Si une erreur d’autorisation d’accès utilisateur s’affiche, cliquez sur **[!UICONTROL Ouvrir un fichier CSV (Open CSV File)]pour accéder à la liste des erreurs d’autorisation limitée.**
1. Créez un fichier « AllRestrictedPermissionErrors.xlsx » et copiez/collez la liste des erreurs d’autorisation limitée du fichier CSV vers ce fichier.
1. Fermez le classeur du Créateur de rapports.

Une fois que vous avez traité tous les classeurs, vous devez avoir une liste complète des erreurs d’autorisation limitée dans « AllRestrictedPermissionErrors.xlsx ». Envoyez cette liste à votre administrateur d’accès utilisateur Adobe Analytics en lui demandant de vous octroyer l’accès aux mesures et dimensions.
