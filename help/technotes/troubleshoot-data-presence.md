---
title: Résolution des problèmes de présence des données
description: Découvrez les étapes que vous pouvez suivre lorsque les données ne s’affichent pas dans les rapports.
translation-type: tm+mt
source-git-commit: 47b14bde1bb1217bcb172c6d4f01d68f917d44db
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 4%

---


# Résolution des problèmes de présence des données

En Analysis Workspace, certaines configurations de projet renvoient zéro ligne. Dans les rapports et analyses, l’affichage de certains rapports renvoie le message suivant :

**&quot;Aucune donnée disponible pour les critères sélectionnés.&quot;**

Suivez les étapes ci-après pour déterminer pourquoi un rapport n’affiche pas de données.

## Les données existent mais sont filtrées

Votre suite de rapports contient des données, mais les composants spécifiques utilisés dans le rapport filtres toutes les données.

* **Segments**: Les segments peuvent facilement empêcher l’affichage de toutes les données dans un rapport. Vérifiez toutes les définitions de segment et supprimez tous les segments pour voir si un segment cause l’absence de vos données.
* **Mesures**: Vérifiez que les mesures appropriées sont utilisées. Remplacez la mesure par [Occurrences](/help/components/metrics/occurrences.md) pour vous assurer que la mesure n’est pas le contributeur d’un rapport sans données.
* **Plages** de dates : Les plages de dates trop éloignées dans le passé ou à tout moment dans le futur ne renvoient pas de données. La stratégie [de rétention des](data-retention.md) données de votre entreprise détermine la distance de conservation des données restantes.
* **Filtres**: Supprimez tous les filtres de recherche du rapport.

## Les données n&#39;existent pas

S’il n’existe aucun segment, la mesure est Occurrences, la plage de dates est le mois en cours et il n’y a aucun filtres de recherche, vérifiez les éléments suivants :

* **Vérifiez la suite** de rapports : Assurez-vous d’être dans une suite de rapports contenant des données. De nombreuses entreprises disposent de nouvelles suites de rapports de test ou de développement qui ne contiennent généralement pas beaucoup de données.
* **Latence**: Si vous consultez des données récentes, il se peut que les données soient retardées. Voir [Latence](latency.md) pour plus d’informations.
* **Valider la collecte** de données : Accédez à la propriété web dont votre suite de rapports est censée effectuer le suivi, puis ouvrez le débogueur [d’](https://docs.adobe.com/content/help/fr-FR/debugger/using/experience-cloud-debugger.html)Adobe. Assurez-vous qu’une demande d’image Analytics est présente lors du chargement d’une page. Si une demande d’image s’affiche, assurez-vous qu’elle utilise l’identifiant de suite de rapports correct, qu’elle comprend un code [de deviseCode](/help/implement/vars/config-vars/currencycode.md)valide et que la prise en charge [de l’](/help/implement/vars/page-vars/timestamp.md) horodatage correspond entre la demande d’image et la suite de rapports.
