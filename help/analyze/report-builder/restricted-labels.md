---
title: Que sont les libellés restreints dans Report Builder ?
description: Décrit les libellés restreints dans Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: aa2182f9-a140-4239-b2fb-f723e2767260
source-git-commit: c333a82848ed74a002a07f8c5e2857426a78425c
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 49%

---

# Libellés restreints dans Report Builder

En règle générale, les paramètres liés à la gouvernance de données dans Adobe Analytics sont hérités de Adobe Experience Platform. L’intégration entre la gouvernance des données d’Adobe Analytics et de Adobe Experience Platform permet l’étiquetage des données Adobe Analytics sensibles et l’application des politiques de confidentialité.

Les étiquettes de confidentialité et les politiques créées sur les jeux de données consommés par Experience Platform peuvent être affichées dans le workflow des suites de rapports Adobe Analytics. Ces étiquettes arrêtent ou avertissent les utilisateurs qui créent des mesures et/ou des dimensions à partir de champs sensibles. Pour plus d’informations sur les jeux de données, consultez la [Présentation des jeux de données](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=fr)

En outre, lorsque des données sont exportées à partir d’Adobe Analytics (par le biais de rapports, d’exports, d’API, etc.), des avertissements ou des étiquettes sont ajoutés afin d’informer les utilisateurs qu’un rapport contient des informations sensibles qui doivent être traitées d’une manière spécifique.

Cette intégration vous permet de gérer la conformité plus facilement. Les gestionnaires de données de votre entreprise peuvent définir des politiques pour restreindre l’utilisation. Ainsi, vos utilisateurs Adobe Analytics peuvent utiliser les données de manière plus sécurisée, tout en sachant qu’elles sont conformes aux politiques définies par les gestionnaires de données.

Pour plus d’informations, voir [Adobe Analytics et gouvernance des données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-privacy/privacy-overview.html?lang=fr)

## Afficher des données limitées dans Report Builder

Deux politiques définies par Adobe sont affichées dans Adobe Analytics et affectent la création de rapports, le téléchargement et le partage :

* Politique Application d’Analytics
* Politique Application du téléchargement

Les composants affectés par ces politiques sont grisés. Lorsque vous passez la souris sur un composant auquel une stratégie est appliquée, une note s’affiche pour indiquer les éléments suivants : **Des politiques ont été appliquées à ce champ pour interdire l’utilisation de ces données.** Pour plus d’informations, voir [Étiquettes et politiques](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-governance.html?lang=fr).

![Note de politique indiquant l’utilisation interdite des données.](assets/rb-restricted-label.png)

## Mettre à jour les rapports contenant des données limitées

Dans les cas où un utilisateur a créé un rapport Report Builder avec des éléments de données ultérieurement limités, un message d’erreur s’affiche lorsque le rapport est actualisé.

![Message d’erreur affiché après la restriction ultérieure des éléments de données.](assets/error-restricted-data.png)
