---
description: Le Gestionnaire de suites de rapports virtuelles permet aux administrateurs de modifier, ajouter, baliser, supprimer, renommer, approuver, copier, exporter et filtrer des suites de rapports virtuelles. Il n’est pas visible par les utilisateurs qui ne sont pas administrateurs.
keywords: Virtual Report Suite
title: Gestion des suites de rapports virtuelles
topic: Reports and analytics
uuid: ce683c01-2d7d-4f2a-98db-946f68eda99b
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Gestion des suites de rapports virtuelles

Le Gestionnaire de suites de rapports virtuelles permet aux administrateurs de modifier, ajouter, baliser, supprimer, renommer, approuver, copier, exporter et filtrer des suites de rapports virtuelles. Il n’est pas visible par les utilisateurs qui ne sont pas administrateurs.

**[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Virtual Report Suites]**

![](assets/vrs-manage.png)

>[!NOTE] Dans le Gestionnaire de suites de rapports virtuelles, vous ne pouvez afficher que vos propres suites de rapports virtuelles. You have to click **[!UICONTROL Show All]** to see everyone else&#39;s.

| Tâche | Description |
|--- |--- |
| Ajouter | Permet d’accéder au créateur de suites de rapports virtuelles où vous pouvez créer des suites de rapports virtuelles. |
| Balise | Tous les utilisateurs peuvent créer des balises pour les segments et appliquer une ou plusieurs balises à un segment. Cependant, vous ne pouvez afficher les balises que pour les segments que vous possédez. Quels types de balises devriez-vous créer ? Voici quelques suggestions de balises utiles :<ul><li>Balises basées sur les noms d’équipe, tels que Marketing social, Marketing mobile</li><li>Balises de projet ( balises  de), telles que le de  de page d’entrée</li><li>Balises de  : Hommes ; géographie</li><li>Balises de processus : traité pour (une unité opérationnelle spécifique); Approuvé</li></ul> |
| Supprimer | Si vous supprimez une suite de rapports virtuelle, les rapports planifiés et les tableaux de bord pour lesquels cette suite de rapports est appliquée continuent de fonctionner correctement (par exemple, le rapport ou le tableau de bord continue d’utiliser la suite de rapports virtuelle supprimée jusqu’à ce que vous enregistriez de nouveau le rapport planifié).  Les rapports planifiés ne sont pas mis à jour lorsque vous modifiez une suite de rapports virtuelle portant le même nom.<br>Par exemple : vous disposez de deux suites de rapports virtuelles portant le même nom et de suites de rapports parentes différentes :<br>Un signet référence la suite de rapports virtuelle pour la suite de rapports mainprod. Vous supprimez ensuite cette suite de rapports virtuelle, car elle est en double. Le signet continue à s’exécuter, référençant la définition de la suite de rapports virtuelle supprimée. Si vous modifiez la définition de la suite de rapports virtuelle restante, la suite de rapports virtuelle appliquée au signet ne change pas. Il utilise l&#39;ancienne définition. Pour corriger ce problème, mettez à jour le signet pour référencer la nouvelle définition. Si vous ne savez pas si un signet, un tableau de bord ou un rapport planifié utilise une suite de rapports virtuelle supprimée, vous pouvez modifier le nom de la suite de rapports virtuelle restante pour déterminer si le signet utilise cette dernière. |
| Renommer | Partout où la suite de rapports virtuelle s’affiche, comme dans le sélecteur de suite de rapports, elle affiche le nouveau nom. |
| Approbation/désapprobation | Approuvez les suites de rapports virtuelles pour les rendre &quot;officielles&quot; ou &quot;canoniques&quot;. Vous pouvez inverser le processus en désapprouvant. |
| Copie | Crée une copie distincte avec son propre nouvel identifiant de suite de rapports, mais avec le même nom et la même définition. |
| Exporter au format CSV | Exportez la définition de la suite de rapports virtuelle dans un fichier .csv. |
| Filtrer | Filtrez par balises, suite de rapports parente, propriétaires et autres  de (Tout afficher, Le mien, Favoris et Approuvé). |
