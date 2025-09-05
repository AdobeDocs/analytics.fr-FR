---
title: Prise en charge des composants dans Data Warehouse
description: Découvrez quelles sont les dimensions et les mesures supplémentaires disponibles dans Data Warehouse et celles qui ne sont pas prises en charge.
feature: Data Warehouse
exl-id: ce7411a4-a720-47b7-90d5-4d867eff4bae
source-git-commit: 665319bdfc4c1599292c2e7aea45622d77a291a7
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 45%

---

# Prise en charge des composants dans Data Warehouse

Le traitement unique dans l’architecture Data Warehouse autorise certains composants qui ne sont généralement pas disponibles dans d’autres fonctionnalités d’Adobe Analytics. En raison de son architecture unique, certains composants ne sont pas disponibles pour utilisation soit dans les rapports soit dans les segments. Utilisez cette page pour comprendre ce qui peut être utilisé et ce qui ne le peut pas.

## Composants uniques à Data Warehouse

Certaines dimensions et mesures pouvant être utilisées dans Data Warehouse ne sont pas disponibles lors de l’utilisation d’autres fonctionnalités dans Adobe Analytics.

### Dimensions prises en charge exclusivement

* **Experience Cloud ID** : pour les implémentations qui utilisent le service Experience Cloud ID (ECID), un nombre 128 bits composé de deux nombres 64 bits concaténés, ajoutés à 19 chiffres.
* **URL de la page** : URL de la page sur laquelle l’accès a eu lieu.
* **ID d’achat** : identifiant unique d’un achat, défini à l’aide de la variable purchaseID.
* **Identifiant visiteur** : fournit l’identifiant unique du visiteur. Cette valeur est la même que la valeur concaténée des colonnes `visid_high` et `visid_low` dans les flux de données. Pour en savoir plus, consultez [Référence des colonnes de données](../analytics-data-feed/c-df-contents/datafeeds-reference.md) dans les flux de données.

### Mesures prises en charge exclusivement

* **Visites** : cette mesure dans le contexte de Data Warehouse exclut les visites de cookies non persistants.
* **Visites - Tous les visiteurs** : cette mesure dans le contexte de Data Warehouse est plus proche de la mesure Visites dans d’autres outils d’Adobe Analytics.

## Composants non pris en charge dans Data Warehouse

Certaines dimensions et mesures ne sont pas prises en charge dans Data Warehouse.

>[!NOTE]
>
>Si une dimension ou une mesure n’est pas prise en charge dans Data Warehouse, les segments utilisant ces composants ne sont pas non plus pris en charge. Vérifiez toujours la compatibilité du produit lors de la création ou de la modification d’un segment.

### Dimensions non prises en charge

* Matin/après-midi
* Certaines dimensions basées sur le cheminement, notamment :
   * Toutes les dimensions d’entrée, à l’exception de la page d’accès
   * Toutes les dimensions de sortie, à l’exception des pages de sortie et des liens de sortie
   * Profondeur d’accès
   * Fréquence des retours
   * Durée avant événement
   * Durée de consultation de la page – Regroupement
   * Durée par visite – Regroupement
* Classement de toutes les pages de recherche
* Variables de hiérarchie
* Type d’accès
* Pages introuvables (disponibles en tant que dimension, non prises en charge pour la segmentation)
* Référencement payant
* Visites de page unique
* Suivi du motif d’exclusion
* États américains

### Mesures non prises en charge

* Certaines mesures basées sur le cheminement, notamment :
   * Retours
   * Entrées
   * Sorties
   * Actualisations
   * Accès unique
   * Mesures de « durée de la visite »
* Mesures de participation (comme décrit dans la section [Créer une mesure de « participation »](/help/components/calculated-metrics/workflow/c-build-metrics/participation-metric.md))

### Dimensions prises en charge d’une autre manière (formatage de date non standard)

Les dimensions temporelles suivantes sont prises en charge :

* Année
* Trimestre
* Mois
* Semaine
* Jour
* Heure 
* Minute

Toutefois, la sortie des dates n’est pas standard lors de l’utilisation de ces dimensions.

Tenez compte des points suivants lors du calcul de la sortie des dates dans Data Warehouse :

* Les dimensions de date s’affichent au format suivant : `1YYMMDDHHMM`

* L&#39;année (YY) est compensée par 1900. Cela signifie que vous ajoutez des `1900` aux 3 premières valeurs du champ de date.

  Par exemple, si la valeur du champ Semaine de la plage de dates dans Data Warehouse est `1250901`, vous ajoutez 1 900 à 125, ce qui donne l’année 2025.

* Tous les mois sont basés sur zéro, janvier étant représenté par 00, février par 01, etc., comme suit :

   * 00 : janvier
   * 01 : Février
   * 02 : mars
   * 03 : avril
   * 04 : mai
   * 05 : Juin
   * 06 : juillet
   * 07 : août
   * 08 : septembre
   * 09 : octobre
   * 10 : novembre
   * 11 : décembre

  Par exemple, si la valeur du champ Semaine de la plage de dates dans Data Warehouse est `1250901`, le mois est représenté par 09, qui indique octobre.




## Segments en tant que dimensions dans Data Warehouse

Lorsque vous utilisez un segment comme une dimension dans Data Warehouse, le rapport renvoie une colonne contenant `"0"` ou `"1"` :

* **`"0"`** : l’élément de dimension ne répondait pas aux critères du segment.
* **`"1"`** : l’élément de dimension répondait aux critères du segment.
