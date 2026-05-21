---
description: Le gestionnaire de suites de rapports virtuelles permet aux administrateurs de modifier, d’ajouter, de baliser, de supprimer, de renommer, d’approuver, de copier, d’exporter et de filtrer les suites de rapports virtuelles. Il n’est pas visible par les utilisateurs qui ne sont pas administrateurs.
keywords: Suite de rapports virtuelle
title: Gestion des suites de rapports virtuelles
feature: VRS
exl-id: b6d58456-bd07-4d97-aff8-216e8440fdc0
TQID: https://experienceleague.adobe.com/ty0vdByiytUJcbNpBMqyp10S2wDRCVllzxbY99r3coA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 481
ht-degree: 62%

---

# Gestion des suites de rapports virtuelles

Le gestionnaire de suites de rapports virtuelles permet aux administrateurs de modifier, d’ajouter, de baliser, de supprimer, de renommer, d’approuver, de copier, d’exporter et de filtrer les suites de rapports virtuelles. Il n’est pas visible par les utilisateurs qui ne sont pas administrateurs.

**[!UICONTROL Analytics]** > **[!UICONTROL Composants]** > **[!UICONTROL Suites de rapports virtuelles]**

![](assets/vrs-manage.png)

>[!NOTE]
>
>Dans le gestionnaire de suites de rapports virtuelles, vous ne pouvez afficher que vos propres suites de rapports virtuelles. Vous devez cliquer sur **[!UICONTROL Tout afficher]** pour afficher les suites de rapports virtuelles des autres utilisateurs.

| Tâche | Description |
| --- | --- |
| Ajouter | Permet d’accéder au créateur de suites de rapports virtuelles où vous pouvez créer des suites de rapports virtuelles. |
| Balises | Tous les utilisateurs peuvent créer des balises pour les suites de rapports virtuelles et appliquer une ou plusieurs balises à l’une de ces suites. Cependant, vous ne pouvez afficher les balises que pour les suites de rapports virtuelles qui vous appartiennent. Quels types de balises devriez-vous créer ? Vous trouverez ci-dessous quelques suggestions de balises utiles :<ul><li>Des balises basées sur des noms d’équipe, par exemple Marketing des réseaux sociaux, Marketing des appareils mobiles</li><li>Les balises Projet (balises d’analyse), telles que l’analyse de la page d’accès</li><li>Les balises Catégorie : Hommes ; géographie</li><li>Les balises Workflow : Traité pour (une division spéciale) ; Approuvé.</li></ul> |
| Supprimer | Si vous supprimez une suite de rapports virtuelle, les rapports planifiés et les tableaux de bord auxquels cette suite de rapports virtuelle est appliquée continuent à fonctionner normalement. Le rapport ou le tableau de bord continue à utiliser la suite de rapports virtuelle supprimée jusqu’à ce que vous enregistriez à nouveau le rapport planifié.  Les rapports planifiés ne sont pas mis à jour lorsque vous modifiez une suite de rapports virtuelle portant le même nom.<br>Par exemple : vous disposez de deux suites de rapports virtuelles portant le même nom et de suites de rapports parentes différentes :<br>Un signet référence la suite de rapports virtuelle pour la suite de rapports mainprod. Vous supprimez ensuite cette suite de rapports virtuelle, car elle est en double. Le signet continue de s’exécuter, faisant référence à la définition des suites de rapports virtuelles supprimées. Si vous modifiez la définition des suites de rapports virtuelles restantes, la suite de rapports virtuelle appliquée au signet ne change pas. Elle utilise l’ancienne définition. Pour corriger ce problème, mettez à jour le signet pour référencer la nouvelle définition. Si vous ne savez pas si un signet, un tableau de bord ou un rapport planifié utilise une suite de rapports virtuelle supprimée, vous pouvez modifier le nom des suites de rapports virtuelles restantes afin de savoir plus clairement si le signet utilise les suites de rapports virtuelles restantes. |
| Renommer | À tous les emplacements où s’affiche la suite de rapports virtuelle (comme dans le sélecteur de suite de rapports), son nouveau nom apparaît. |
| Approuver/Ne plus approuver | Permet d’approuver les suites de rapports virtuelles pour les rendre officielles ou canoniques. Vous pouvez inverser le processus en annulant l’approbation. |
| Copier | Permet de créer une copie distincte avec un nouvel identifiant de suite de rapports. Elle est toutefois dotée du même nom et de la même définition. |
| Exporter dans un fichier CSV | Permet d’exporter la définition de suite de rapports virtuelle vers un fichier .csv. |
| Filtre | Permet de filtrer par balises, suite de rapports parente, propriétaires et d’autres filtres (Tout afficher, A moi, Favoris et Approuvé). |
