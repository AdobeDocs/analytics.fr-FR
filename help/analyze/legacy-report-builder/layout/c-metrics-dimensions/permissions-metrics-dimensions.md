---
description: Le Report Builder Adobe propose désormais des paramètres de gestion des autorisations analogues à ceux des Outils d’administration d’Analytics.
title: Autorisations d’accès utilisateur pour les dimensions et les mesures
uuid: b561407d-c4fa-4f1e-8b16-5ca46fcbf36f
feature: Report Builder
role: User, Admin
exl-id: 53cfdcf4-31c3-40ab-aca4-8f0f9be6fe13
source-git-commit: bb908f8dd21f7f11d93eb2e3cc843f107b99950d
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 71%

---

# Autorisations d’accès utilisateur pour les dimensions et les mesures

Adobe Report Builder propose des paramètres d’autorisation similaires à ceux des outils d’administration Analytics.

En tant qu’utilisateur non administrateur, vous avez peut-être créé antérieurement des classeurs avec des requêtes pointant vers des dimensions et des mesures auxquelles vous n’avez pas accès. Ces autorisations sont maintenant appliquées.

Par exemple, si vous actualisez une requête qui inclut des dimensions ou des mesures auxquelles vous n’avez pas accès, vous obtenez une erreur d’autorisation limitée (Restricted Permission Error). Le message d’erreur indique qu’une demande n’est pas disponible pour votre compte utilisateur en raison des autorisations d’administration.

![Capture d&#39;écran montrant le message d&#39;erreur d&#39;autorisation limitée (Restricted Permission Error).](assets/arb_restrc_perm.png)

Suivez ces instructions pour **chaque** classeur du Report Builder que vous conservez :

1. Ouvrez le classeur.
1. Actualisez toutes les requêtes.
1. Si une erreur d’autorisation d’accès utilisateur s’affiche, cliquez sur **[!UICONTROL Ouvrir un fichier CSV (Open CSV File)]** pour accéder à la liste des erreurs d’autorisation limitée.
1. Créez un fichier « AllRestrictedPermissionErrors.xlsx » et copiez/collez la liste des erreurs d’autorisation limitée du fichier CSV vers ce fichier.
1. Fermez le classeur du Report Builder.

Une fois que vous avez traité tous les classeurs, vous devez avoir une liste complète des erreurs d’autorisation limitée dans « AllRestrictedPermissionErrors.xlsx ». Envoyez cette liste à votre administrateur d’accès utilisateur Adobe Analytics en lui demandant de vous octroyer l’accès aux mesures et dimensions.
