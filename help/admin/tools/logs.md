---
description: Fichiers journaux permettant de savoir quand se connectent les utilisateurs, leur utilisation, l’accès, les suites de rapports et les changements administratifs.
title: Journaux
feature: Admin Tools
exl-id: 43f79e2a-2cb9-47eb-982a-54714c9cbafc
role: Admin
TQID: https://experienceleague.adobe.com/TsWKmf74-b1RhjP0CSGZatLrGN39xDylj9tbFZg5R-Y
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: c6a85389-fb1b-4b26-96ea-08f17fed0c9fid: e44bec7e-8653-4d5b-b53e-60b1ae7c3475id: e499b847-6dc4-408a-9f0b-70d35ce9b711id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d095671a-1355-40aa-8b5f-06c33c68080bid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 595
ht-degree: 71%

---

# Journaux

Fichiers journaux permettant de savoir quand se connectent les utilisateurs, leur utilisation, l’accès, les suites de rapports et les changements administratifs.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Tous les administrateurs]** > **[!UICONTROL Journaux]**

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
| Type d’événement | Vous pouvez filtrer le journal selon un type d’événement. Sélectionnez un type d’événement dans la liste déroulante. Consultez la liste complète des types d’événements ci-dessous. |
| Événement | Vous pouvez filtrer le journal sur la base d’un mot ou d’une expression de la description de l’événement. |
| Télécharger le rapport | Exporte le contenu du [!UICONTROL journal d’utilisation et des accès] dans un fichier délimité par des tabulations. |

### Types d’événements

| Type d’événement | Description |
| --- | --- |
| Aucune catégorie | Peut être n’importe quel type d’événement. |
| Échec de la connexion | Échec du processus de connexion de l&#39;utilisateur. |
| Identification réussie | L&#39;utilisateur s&#39;est connecté. |
| Action administrateur | Une action d’administration s’est produite, comme la modification d’une suite de rapports, la modification des paramètres de l’entreprise, la création d’un utilisateur, l’annulation d’une demande de rapport, etc. |
| Changement des paramètres de sécurité | Un paramètre de sécurité a été modifié. |
| Alerte envoyée | Une alerte a été envoyée. |
| Action utilisateur | Les informations utilisateur ont été modifiées. |
| Outil affiché | Un outil a été consulté. |
| Action Omniture | Une action a été effectuée par Adobe. |
| Récupération du mot de passe | Mot de passe récupéré. |
| Signets | Un signet a été géré. |
| Tableaux de bord | Un tableau de bord a été géré. |
| Alertes | Une alerte a été gérée. |
| Événements calendrier | Un événement de calendrier a été géré. |
| Cibles | Une cible a été gérée. |
| Paramètres des rapports | Un paramètre de rapport a été géré. |
| Rapports planifiés | Un rapport planifié a été géré. |
| Exclure par adresse IP | Le paramètre d’adresse IP a été modifié. |
| Nommer pages | Obsolète. |
| Classifications | Une classification a été gérée. |
| Sources de données | Une source de données a été gérée. |
| Projet espace de travail | Un projet Workspace a été affiché ou modifié. |
| Segment | Un segment a été créé/modifié. |
| Mesure calculée | Une mesure calculée a été créée/modifiée. |
| Période | Une période a été créée/modifiée. |
| Suite de rapports virtuelle | Une suite de rapports virtuelle a été créée/modifiée. |
| Analyse des contributions | Une tâche d’analyse des contributions a été exécutée. |
| Méthode API | Un appel API a été effectué. |


## Journal des modifications de la suite des rapports {#section_3864966639414BBEA871F4D0352F56B6}

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
