---
description: Les mesures de participation attribuent tout le crédit du de réussite à toutes les valeurs d’une eVar transmises au cours d’une visite. Les mesures de participation sont utiles pour déterminer les pages, campagnes ou autres valeurs de variable personnalisée qui contribuent le plus à la réussite de votre site. La participation est basée sur les visites. Toutes les valeurs d’eVar d’une visite avant et après l’accès lorsqu’un se produit reçoivent un crédit de participation, quel que soit le paramètre d’expiration.
title: Participation
topic: Metrics
uuid: a7fa791d-0a77-429e-808e-4f97bb9ae5fc
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Participation

Les mesures de participation attribuent tout le crédit du de réussite à toutes les valeurs d’une eVar transmises au cours d’une visite. Les mesures de participation sont utiles pour déterminer les pages, campagnes ou autres valeurs de variable personnalisée qui contribuent le plus à la réussite de votre site. La participation est basée sur les visites. Toutes les valeurs d’eVar d’une visite avant et après l’accès lorsqu’un se produit reçoivent un crédit de participation, quel que soit le paramètre d’expiration.

Voir [Participation des visiteurs – Ad Hoc Analysis](/help/components/c-variables/c-metrics/metrics-visitor-participation.md) pour en savoir plus sur l’utilisation de la participation dans le cadre de l’Ad Hoc Analysis.

Les mesures de participation ont deux paramètres par de conversion :

* **Désactivé**: Etat par défaut de chaque  de conversion. Les données de participation ne seront pas collectées pour ce .
* **Activé**: Les données de participation sont collectées pour cette  de.

>[!NOTE] Vous pouvez activer la participation pour 100 événements personnalisés au maximum. De plus, vous pouvez créer des mesures de participation dans le créateur de [mesures calculées](https://marketing.adobe.com/resources/help/fr_FR/analytics/calcmetrics/participation_metric.html).

Une fois activées, les mesures de participation sont automatiquement disponibles dans tous les rapports de conversion. Cependant, les mesures de participation peuvent également être affichées dans des rapports de trafic spécifiques à votre demande. Vous pouvez éventuellement demander que des mesures de participation soient disponibles dans certains rapports de trafic personnalisés.

## Exemple de participation aux recettes  {#section_DAB6C348201B454BB4ED01313AA777AF}

Supposons la séquence suivante :

1. Un utilisateur accède à votre site et recherche &quot;chaussures&quot;.
1. L&#39;utilisateur recherche ensuite &quot;tennis chaussures&quot;.
1. L’utilisateur clique sur un lien vers la page du produit, ajoute l’élément au panier et effectue un achat de 120 euros.

Lors de l’affichage des recettes dans le rapport Termes de recherche interne, les éléments suivants s’affichent en fonction de l’attribution sélectionnée :

* **Premier**: Les &quot;chaussures&quot; obtiendraient un crédit pour les 120 $. &quot;tennis&quot; aurait 0 $.
* **Dernier**: Les &quot;tennis&quot; obtiendraient un crédit pour les 120 dollars. &quot;chaussures&quot; obtiendrait 0 $.
* **Linéaire**: Chaque campagne recevra un crédit de 60 USD.

   La participation est similaire à l’attribution linéaire, sauf que le crédit total est attribué à toutes les valeurs. Si vous utilisez la mesure Recettes (Participation), l’attribution n’est pas prise en compte. Dans cet exemple, les recettes (participation) rapporteraient 120 euros pour les deux termes de recherche.

>[!MORELIKETHIS]
>
>* [Calculs de mesures](/help/components/c-variables/c-metrics/metrics-calculations.md)

