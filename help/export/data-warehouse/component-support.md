---
title: Prise en charge des composants dans Data Warehouse
description: Découvrez quelles sont les dimensions et les mesures supplémentaires disponibles dans Data Warehouse et celles qui ne sont pas prises en charge.
translation-type: ht
source-git-commit: 00d4d59cb4c922b54a97ef7000e294ef3bf61f20

---


# Prise en charge des composants dans Data Warehouse

L’architecture de traitement unique de Data Warehouse autorise certains composants qui ne sont généralement pas disponibles avec d’autres fonctionnalités d’Adobe Analytics. En raison de son architecture unique, certains composants ne sont pas disponibles pour utilisation soit dans les rapports soit dans les segments. Utilisez cette page pour comprendre ce qui peut être utilisé et ce qui ne le peut pas.

## Composants uniques à Data Warehouse

Certaines dimensions et mesures peuvent être utilisées dans Data Warehouse alors qu’elles ne sont pas disponibles avec d’autres fonctionnalités d’Adobe Analytics.

### Dimensions prises en charge exclusivement

* Experience Cloud ID : pour les implémentations qui utilisent le service Experience Cloud ID (ECID) un nombre 128 bits consitué de deux nombres 64 bits concaténés complétés par 19 chiffres.
* URL de la page : l’URL de la page sur lequel l’accès s’est produit.
* Identifiants d’achat : l’identificateur unique pour un achat, tel qu’il est défini à l’aide de la variable purchaseID.
* Identifiant visiteur : fournit l’identifiant unique du visiteur. Cette valeur est la même que la valeur concaténée des colonnes `visid_high` et `visid_low` dans les flux de données. Pour en savoir plus, consultez [Référence des colonnes de données](../analytics-data-feed/c-df-contents/datafeeds-reference.md) dans les flux de données.

### Mesures prises en charge exclusivement

* Visites : dans le contexte de Data Warehouse, cette mesure exclut les visites de cookies non persistants.
* Visites - tous les visiteurs : dans le contexte de Data Warehouse, cette mesure possède une parité plus proche de la mesure des visites qu’avec d’autres outils au sein d’Adobe Analytics.

## Composants non pris en charge dans Data Warehouse

Certaines dimensions et mesures ne sont pas prises en charge dans Data Warehouse.

> [!NOTE] Si une dimension ou une mesure n’est pas prise en charge dans Data Warehouse, les segments utilisant ces composants ne sont pas non plus pris en charge. Vérifiez toujours la compatibilité du produit lors de la création ou de la modification d’un segment.

### Dimensions non prises en charge

* Certaines dimensions temporelles, notamment :
   * Matin/après-midi
   * Jour du mois
   * Jour de la semaine
   * Jour de l’année
   * Heure du jour
   * Minute
   * Mois de l’année
   * Trimestre de l’année
   * Jour ouvrable/week-end
   * Année
* Certaines dimensions basées sur le cheminement, notamment :
   * Toutes les dimensions d’entrée, à l’exception de la page d’accès
   * Toutes les dimensions de sortie, à l’exception des pages de sortie et des liens de sortie
   * Détail des accès
   * Fréquence des retours
   * Durée avant événement
   * Durée de consultation de la page – Regroupement
   * Durée par visite – Regroupement
   * Profondeur de visite
* Classement de toutes les pages de recherche
* Variables de hiérarchie
* Type d’accès
* Pages introuvables (disponibles en tant que dimension, non prises en charge pour la segmentation)
* Recherche payante
* Visites sur une seule page
* Suivi du motif d’exclusion
* États américains

### Mesures non prises en charge

* Certaines mesures basées sur le cheminement, notamment :
   * Retours
   * Entrées
   * Sorties
   * Actualisations
   * Accès unique
   * Mesures « Tranche de temps »
