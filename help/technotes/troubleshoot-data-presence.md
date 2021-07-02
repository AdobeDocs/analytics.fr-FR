---
title: Résolution des problèmes de présence des données
description: Découvrez les mesures que vous pouvez suivre lorsque vous ne voyez pas de données dans les rapports.
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: ht
source-wordcount: '332'
ht-degree: 100%

---


# Résolution des problèmes de présence des données

Dans Analysis Workspace, certaines configurations de projet ne renvoient aucune ligne. Dans Reports &amp; Analytics, l’affichage de certains rapports renvoie le message suivant :

**&quot;Aucune donnée disponible pour les critères sélectionnés.&quot;**

Procédez comme suit pour déterminer pourquoi un rapport n’affiche pas de données.

## Les données existent mais sont filtrées.

Votre suite de rapports contient des données, mais les composants spécifiques utilisés dans le rapport les filtrent.

* **Segments** : les segments peuvent facilement empêcher l’affichage de toutes les données dans un rapport. Vérifiez toutes les définitions de segment et supprimez tous les segments pour voir si un segment provoque l’affichage de vos données.
* **Mesures** : vérifiez que les mesures correctes sont utilisées. Remplacez la mesure par [Occurrences](/help/components/metrics/occurrences.md) pour vous assurer que la mesure ne contribue pas à obtenir un rapport sans données.
* **Périodes** : les périodes trop éloignées dans le passé ou à tout moment dans le futur ne renvoient pas de données. La [politique de conservation des données](data-retention.md) de votre entreprise détermine la durée de conservation des données.
* **Filtres** : supprimez tous les filtres de recherche du rapport.

## Les données n’existent pas.

S’il n’existe aucun segment, la mesure est Occurrences, la période correspond au mois en cours et il n’existe aucun filtre de recherche, alors vérifiez les éléments suivants :

* **Vérifiez la suite de rapports** : assurez-vous que vous êtes dans une suite de rapports contenant des données. De nombreuses entreprises disposent de nouvelles suites de rapports de test ou de développement qui ne contiennent généralement pas beaucoup de données.
* **Latence** : si vous affichez des données récentes, les données peuvent simplement être retardées. Voir [Latence](latency.md) pour plus d’informations.
* **Validation de la collecte de données** : accédez à la propriété web dont votre suite de rapports est censée effectuer le suivi, puis ouvrez le débogueur [Adobe](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=fr). Assurez-vous qu’une demande d’image Analytics est présente lors du chargement d’une page. Si vous voyez une demande d’image, assurez-vous qu’elle utilise l’identifiant correct de la suite de rapports, qu’elle inclut un [currencyCode](/help/implement/vars/config-vars/currencycode.md) valide et que la [prise en charge de l’horodatage](/help/implement/vars/page-vars/timestamp.md) correspond entre la demande d’image et la suite de rapports.
