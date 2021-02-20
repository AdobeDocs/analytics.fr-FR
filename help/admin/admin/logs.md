---
description: Fichiers journaux permettant de savoir quand se connectent les utilisateurs, leur utilisation, l’accès, les suites de rapports et les changements administratifs.
title: Journaux
topic: Admin tools
translation-type: tm+mt
source-git-commit: 9b56730548975435c5607428e4c71efda1d6a8d0
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 72%

---


# Journaux

Fichiers journaux permettant de savoir quand se connectent les utilisateurs, leur utilisation, l’accès, les suites de rapports et les changements administratifs.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Journaux]**

## Journal d’administration {#section_8ADE8A7204A8401C968ABC20AECA381D}

Le journal d’administration consigne toutes les modifications effectuées par les administrateurs dans les outils d’administration. Il fournit une passerelle vers des rapports définis par l’utilisateur depuis n’importe lequel des trois journaux. Vous pouvez rechercher des événements correspondant à vos critères sélectionnés sur une période déterminée.

## Journal d’utilisation et des accès {#section_6FBAF92D9EA244809C45A78A2F0A7232}

Le [!UICONTROL Journal d’utilisation et des accès] vous permet d’évaluer l’utilisation des rapports au niveau du compte d’utilisateur. Par exemple, il suit l’ouverture, la création, la mise à jour, le non-partage et la suppression des actions dans Analysis Workspace. Cela permet de mieux comprendre qui utilise Workspace et à quelle fréquence.

| Élément | Description |
|---|---|
| Période | Indiquez un filtre de plage de dates. Vous pouvez saisir une date manuellement au format AAAA-MM-JJ ou cliquer sur l’icône Calendrier pour en choisir une. |
| Connexion | Vous pouvez filtrer le journal par nom d’utilisateur. |
| IP | Vous pouvez filtrer le journal par adresse IP. |
| Suite de rapports | Vous pouvez filtrer le journal selon un identifiant de suite de rapports spécifique. |
| Type d’événement | Vous pouvez filtrer le journal selon un type d’événement. Sélectionnez un type d’événement dans la liste déroulante. Voir la liste complète des types d&#39;événement ci-dessous. |
| Événement | Vous pouvez filtrer le journal sur la base d’un mot ou d’une expression de la description de l’événement. |
| Télécharger le rapport | Exporte le contenu du [!UICONTROL journal d’utilisation et des accès] dans un fichier délimité par des tabulations. |

### Types d’événements

| Type d&#39;événement | Description |
| --- | --- |
| Aucune catégorie | Ça pourrait être n&#39;importe quel type d&#39;événement. |
| Échec de l&#39;identification | Échec du processus de connexion de l&#39;utilisateur. |
| Identification réussie | L&#39;utilisateur s&#39;est connecté correctement. |
| Action administrateur | Une action d&#39;administration s&#39;est produite, telle que la modification d&#39;une suite de rapports, la modification des paramètres de société, la création d&#39;un utilisateur, etc. |
| Changement des paramètres de sécurité | Un paramètre de sécurité a été modifié. |
| Rapport affiché | Un rapport Rapports et analyses a été affiché. |
| Rapport téléchargé | Un rapport Rapports et analyses a été téléchargé. |
| Alerte envoyée | Une alerte a été envoyée. |
| Action utilisateur | Les informations sur l’utilisateur ont été modifiées. |
| Outil affiché | Un outil a été vu. |
| Action Omniture | Une action a été exécutée par l&#39;Adobe. |
| Récupération du mot de passe | Un mot de passe a été récupéré. |
| Signets | Un signet a été géré. |
| Tableaux de bord | Un tableau de bord a été géré. |
| Alertes | Une alerte a été gérée. |
| Événements calendrier | Un événement de calendrier a été géré. |
| Cibles | Une cible a été gérée. |
| Paramètres des rapports | Un paramètre de rapport a été géré. |
| Rapports programmés | Un rapport planifié a été géré. |
| Exclure par IP | Le paramètre IP a été modifié. |
| Nommer pages | Obsolète. |
| Classifications | Une classification a été gérée. |
| Sources de données | Une source de données a été gérée. |
| Projet espace de travail | Un projet Workspace a été affiché ou modifié. |
| Segment | Un segment a été créé/modifié. |
| Mesure calculée | Une mesure calculée a été créée/modifiée. |
| Période | Une plage de dates a été créée/modifiée. |
| Suite de rapports virtuelle | Une suite de rapports virtuelle a été créée/modifiée. |
| Analyse des contributions | Une tâche d&#39;analyse de contribution a été exécutée. |
| Méthode API | Un appel d&#39;API a été effectué. |


## Journal des modifications de la suite des rapports  {#section_3864966639414BBEA871F4D0352F56B6}

Le journal des modifications de la suite de rapports affiche les modifications apportées à vos suites de rapports en dehors de l’Administration.

Les outils suivants permettent de modifier une suite de rapports hors des [!UICONTROL Outils d’administration] :

* Téléchargements de classifications réalisés dans un navigateur web (les transferts effectués par FTP ne sont pas inclus dans le journal des modifications)
* Modifications effectuées dans des versions antérieures
* Modifications effectuées par un gestionnaire de compte ou le service d’assistance clientèle à l’aide d’outils internes

| Élément | Description |
|---|---|
| Période | Indiquez un filtre de plage de dates. Vous pouvez saisir une date manuellement au format AAAA-MM-JJ ou cliquer sur l’icône Calendrier pour en choisir une. |
| Société | Vous pouvez filtrer le journal par nom de société. |
| Connexion | Vous pouvez filtrer le journal par nom d’utilisateur. |
| IP | Vous pouvez filtrer le journal par adresse IP. |
| Événement | Vous pouvez filtrer le journal sur la base d’un mot ou d’une expression de la description de l’événement. |
| Télécharger le rapport | Exporte le contenu du [!UICONTROL journal d’utilisation et des accès] dans un fichier délimité par des tabulations. |

