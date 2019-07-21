---
description: Les suites de rapports de cumul combinent les données de plusieurs suites de rapports affiliées et les affichent dans un jeu de données résumé.
seo-description: Les suites de rapports de cumul combinent les données de plusieurs suites de rapports affiliées et les affichent dans un jeu de données résumé.
seo-title: Suites de rapports globales et de cumul
solution: Analytics
title: Suites de rapports globales et de cumul
topic: Outils d’administration
uuid: c 90 b 8 e 38-2 c 95-4318-8165-a 362106 b 6142
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Suites de rapports globales et de cumul

Les suites de rapports de cumul combinent les données de plusieurs suites de rapports affiliées et les affichent dans un jeu de données résumé.

Les cumuls (à ne pas confondre avec les suites de rapports globales) constituent un emplacement facilement accessible pour consulter des totaux cumulés, tels que les mesures Pages vues, Recettes ou Technologie. Ils sont utilisés fréquemment, dans la mesure où ils ne nécessitent aucune implémentation supplémentaire.

## Définition des types de suite de rapports {#section_E51E03E3917040278600A7E9638A91C7}

**Suite de rapports globale** : l’implémentation est modifiée afin d’envoyer des demandes d’image, via des domaines, dans une suite de rapports globale unique, en plus des suites de rapports individuelles.

**Suite de rapports de cumul** : elle est créée dans les outils d’administration. Cette suite calcule la somme de chaque mesure à la fin de chaque journée.

* Les cumuls peuvent être utilisés librement et n’incrémentent pas les appels de serveur.
* Les cumuls fournissent des données totales, mais ne génèrent pas de rapports sur des valeurs individuelles. Ainsi, les valeurs eVar1 ne sont pas incluses, mais le total cumulé peut l’être.
* Les données ne sont pas dédupliquées lorsqu’elles sont combinées dans des suites de rapports. Un seul utilisateur peut être concerné par trois suites de rapports différentes en un jour et apparaître sous la forme de trois visiteurs uniques par jour dans le cumul.
* L’agrégation des cumuls a lieu la nuit.
* Lors de l’ajout d’une suite de rapports à un cumul existant, les données historiques ne sont pas intégrées au cumul.
* Les suites de rapports de cumul offrent des capacités de création de rapports limitées. Par exemple, les comptes de visiteurs uniques des différentes suites de rapports s’additionnent. Si une même personne visite deux suites de rapports distinctes, un cumul recense cette personne comme deux visiteurs, alors qu’une suite de rapports globale standard l’affiche comme un seul visiteur.
* Toutes les suites de rapports affiliées doivent comporter des données pour qu’un cumul fonctionne. Si vous intégrez de nouvelles suites de rapports dans un cumul, veillez à leur envoyer au moins une page vue.
* Les suites de rapports de cumul sont limitées à 40 suites enfants.
* Les suites de rapports de cumul sont limitées à 100 événements.
* Les données contenues dans les suites de rapports de cumul ne prennent pas en charge les sous-relations, les segments ni les autres mesures introduites dans les rapports marketing.
* Le rapport Pages n’est pas disponible dans les suites de rapports cumulées. Il est remplacé par le rapport Sites les plus populaires, qui tient compte des mesures au niveau de la suite enfant.

## Suites de rapports globales et de cumul {#section_7B3703DC7ABF4B9EA9DF02A54592CAD0}

**Appels serveur** : les suites de rapports globales incrémentent des appels au serveur secondaire, alors que les suites de rapports de cumul n’effectuent aucun appel serveur.

**Changements d’implémentation** : les suites de rapports de cumul ne nécessitent aucun changement d’implémentation, alors que les suites globales exigent qu’un identifiant de suite de rapports supplémentaire soit placé dans le fichier s_code.js.

**Duplication** : contrairement aux cumuls, les suites de rapports globales dédupliquent les visiteurs uniques. Ainsi, si un utilisateur visite trois ou quatre de vos domaines le même jour, les cumuls comptabilisent trois visiteurs uniques par jour. Quant aux suites de rapports globales, elles n’en comptabilisent qu’un seul.

**Période** : les cumuls ne sont traités qu’à minuit, tous les jours, alors que les suites de rapports globales génèrent des rapports sur les données avec une latence standard.

**Étendue** : les suites de rapports globales peuvent non seulement allouer du crédit à des variables de conversion entre des suites de rapports, mais aussi fournir un cheminement entre les suites. Les cumuls n’offrent aucun moyen de communiquer entre les suites de rapports.

**Données historiques** : les cumuls peuvent agréger des données historiques, alors que les suites de rapports globales ne génèrent des rapports qu’à partir du point où les données ont été implémentées.

**Rapports** : les suites de rapports globales fournissent des informations supplémentaires sur TOUS les rapports implémentés ; les cumuls ne fournissent des données agrégées que sur les rapports de haut niveau.

**Produits pris en charge** : les cumuls ne sont pas pris en charge dans Data Warehouse, ni dans l’Ad Hoc Analysis. Les rapports marketing sont limités à 40 suites de rapports enfants. Les suites de rapports globales peuvent être utilisées dans tous les produits et comporter un nombre illimité de suites enfants.

## Quel type de suite de rapports vais-je implémenter ? {#section_868066B9604B49BABBF84074BA5E9C71}

Pour déterminer le type de suite de rapports à implémenter, vous devez tenir compte des points suivants :

* Le nombre d’appels serveur est-il un facteur essentiel pour ma société ? S’il est important de limiter le nombre d’appels serveur, pensez à utiliser des cumuls. Les suites de rapports globales multiplient pratiquement par deux le nombre d’appels serveur effectués.
* La création de rapports portant sur un total de trafic de haut niveau sur toutes les suites s’avère-t-elle suffisante ? Si la déduplication des visiteurs constitue une exigence, optez pour une suite de rapports globale.
* Le cheminement et les événements de succès/conversion entre les domaines sont-ils des facteurs importants ? Si vous faites un usage intensif des campagnes sur plusieurs sites, optez pour une suite de rapports globale.
* L’affichage des données totales du site est-il sensible au temps ? Les suites de rapports individuelles continuent de générer des rapports en temps quasi réel. Si la possibilité de consulter des totaux d’une suite de rapports le jour suivant vous convient, il est conseillé d’opter pour des cumuls.
* Y a-t-il un grand nombre de données historiques exploitables ? Les suites de rapports globales ne peuvent pas créer de rapports de manière rétroactive ; il est donc conseillé d’opter pour des cumuls si vous accordez de l’importance aux données historiques.
* Data Warehouse et l’Ad Hoc Analysis sont-ils essentiels dans le cadre de la création de rapports ? Si tel est le cas, il est conseillé d’opter pour une suite de rapports globale.

L’option retenue n’a aucune incidence sur les suites de rapports individuelles. Pesez soigneusement les avantages et les inconvénients de chaque type avant de faire votre choix.
