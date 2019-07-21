---
description: Les mesures de participation attribuent la totalité du crédit des événements de succès à toutes les valeurs d’une eVar transmises durant une visite. Ces mesures se révèlent particulièrement utiles pour déterminer les pages, les campagnes ou d’autres variables personnalisées qui contribuent le plus au succès de votre site. La participation dépend des visites. Toutes les valeurs d’eVar d’une visite avant l’accès (accès compris) lorsqu’un événement survient reçoivent le crédit de la participation, quel que soit le paramètre d’expiration.
seo-description: Les mesures de participation attribuent la totalité du crédit des événements de succès à toutes les valeurs d’une eVar transmises durant une visite. Ces mesures se révèlent particulièrement utiles pour déterminer les pages, les campagnes ou d’autres variables personnalisées qui contribuent le plus au succès de votre site. La participation dépend des visites. Toutes les valeurs d’eVar d’une visite avant l’accès (accès compris) lorsqu’un événement survient reçoivent le crédit de la participation, quel que soit le paramètre d’expiration.
seo-title: Participation
solution: Analytics
title: Participation
topic: Mesures
uuid: a 7 fa 791 d -0 a 77-429 e -808 e -4 f 97 bb 9 ae 5 fc
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Participation

Les mesures de participation attribuent la totalité du crédit des événements de succès à toutes les valeurs d’une eVar transmises durant une visite. Ces mesures se révèlent particulièrement utiles pour déterminer les pages, les campagnes ou d’autres variables personnalisées qui contribuent le plus au succès de votre site. La participation dépend des visites. Toutes les valeurs d’eVar d’une visite avant l’accès (accès compris) lorsqu’un événement survient reçoivent le crédit de la participation, quel que soit le paramètre d’expiration.

See [Visitor Participation - Ad Hoc Analysis](../../../components/c-variables/c-metrics/metrics-visitor-participation.md#concept_ACBAE3626B224D9683257B5F73E0FB4A) for more information about how Ad Hoc Analysis uses participation.

Les mesures de participation présentent deux paramètres par événement de conversion :

* **Désactivé** : état par défaut de chaque événement de conversion. Les données de participation ne sont pas rassemblées pour cet événement.
* **Activé** : les données de participation sont collectées pour cet événement.

>[!NOTE]
>
>Vous pouvez activer la participation pour 100 événements personnalisés au maximum. De plus, vous pouvez créer des mesures de participation dans le créateur de [mesures calculées](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/participation_metric.html).

Aussitôt la participation activée, les mesures de participation sont disponibles automatiquement dans tous les rapports de conversion. Cependant, ces mesures peuvent également être affichées, à votre demande, dans des rapports de trafic spécifiques. Vous pouvez éventuellement demander que des mesures de participation soient disponibles dans certains rapports de trafic personnalisés.

## Exemple de participation aux recettes {#section_DAB6C348201B454BB4ED01313AA777AF}

Supposez la séquence suivante :

1. Un utilisateur parcourt votre site et recherche des « chaussures ».
1. Il recherche ensuite des « tennis ».
1. Il clique sur un lien vers la page de produits, ajoute l’article au panier et effectue un achat de 120 €.

Lors de l’affichage des recettes dans le rapport Termes de recherche internes, les informations suivantes s’afficheront en fonction de l’affectation sélectionnée :

* **Premier** : les « chaussures » recevront un crédit pour la somme de 120 $. « tennis » obtiendra 0 $.
* **Dernier** : « tennis » recevra un crédit de 120 $. « chaussures » obtiendra 0 $.
* **Linéaire** : chaque campagne recevra un crédit de 60 $.

   La participation est semblable à l’affectation linéaire, sauf qu’un crédit complet est attribué à toutes les valeurs. Si vous utilisez la mesure Participation aux recettes, il n’est pas tenu compte de l’attribution. Les recettes (participation) dans cet exemple recevraient 120 $ pour les deux termes de recherche.

>[!MORE_LIKE_THIS]
>
>* [Calculs de mesures](/help/components/c-variables/c-metrics/metrics-calculations.md)

