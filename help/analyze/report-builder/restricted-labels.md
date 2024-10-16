---
title: Que sont les libellés restreints dans Report Builder ?
description: Décrit les libellés restreints dans Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Analytics
source-git-commit: eedabc6295f9b918e1e00b93993680e676c216c3
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 49%

---

# Libellés restreints dans Report Builder

En règle générale, les paramètres liés à la gouvernance des données dans Adobe Analytics sont hérités de Adobe Experience Platform. L’intégration entre Adobe Analytics et la gouvernance des données Adobe Experience Platform permet d’étiqueter les données Adobe Analytics sensibles et d’appliquer les politiques de confidentialité.

Les étiquettes de confidentialité et les stratégies créées sur les jeux de données consommés par l’Experience Platform peuvent être affichées dans le workflow des suites de rapports Adobe Analytics. Ces étiquettes arrêtent ou avertissent les utilisateurs qui créent des mesures et/ou des dimensions à partir de champs sensibles. Pour plus d’informations sur les jeux de données, consultez la [Présentation des jeux de données](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=fr)

En outre, lorsque des données sont exportées depuis Adobe Analytics (par le biais de rapports, d&#39;exports, d&#39;API, etc.), des avertissements ou des libellés sont ajoutés afin d&#39;informer les utilisateurs qu&#39;un rapport contient des informations sensibles qui doivent être traitées d&#39;une manière spécifique.

Cette intégration vous permet de gérer la conformité plus facilement. Les gestionnaires de données de votre entreprise peuvent définir des politiques pour restreindre l’utilisation. Par conséquent, vos utilisateurs Adobe Analytics peuvent utiliser les données de manière plus sécurisée, tout en sachant qu’elles sont conformes aux stratégies définies par les gestionnaires de données.

Pour plus d’informations, voir [Adobe Analytics et gouvernance des données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-privacy/privacy-overview.html?lang=fr)

## Afficher des données limitées dans Report Builder

Deux stratégies définies par l’Adobe sont affichées dans Adobe Analytics, ce qui affecte le reporting, le téléchargement et le partage :

* Politique Application d’Analytics
* Politique Application du téléchargement

Les composants affectés par ces politiques sont grisés. Lorsque vous passez la souris sur un composant auquel une stratégie est appliquée, une note s’affiche pour indiquer les éléments suivants : **Des politiques ont été appliquées à ce champ pour interdire l’utilisation de ces données.** Pour plus d’informations, voir [Étiquettes et politiques](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-governance.html?lang=fr).

![La note de politique indiquant l’utilisation interdite des données.](assets/rb-restricted-label.png)

## Mettre à jour les rapports contenant des données limitées

Dans les cas où un utilisateur a créé un rapport Report Builder avec des éléments de données ultérieurement limités, un message d’erreur s’affiche lorsque le rapport est actualisé.

![Le message d’erreur affiché après la restriction des éléments de données.](assets/error-restricted-data.png)
