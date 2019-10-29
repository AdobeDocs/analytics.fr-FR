---
title: Prise en charge des composants dans Data Warehouse
description: Découvrez les dimensions et mesures supplémentaires disponibles dans l’entrepôt de données et ce qui n’est pas pris en charge.
translation-type: tm+mt
source-git-commit: 00d4d59cb4c922b54a97ef7000e294ef3bf61f20

---


# Prise en charge des composants dans Data Warehouse

L’architecture de traitement unique de l’entrepôt de données permet à certains composants qui ne sont généralement pas disponibles dans d’autres fonctionnalités d’Adobe Analytics. En raison de son architecture unique, certains composants ne sont disponibles ni dans les rapports, ni dans les segments. Utilisez cette page pour comprendre ce qui peut être utilisé et ce qui ne le peut pas.

## Composants propres à l’entrepôt de données

Certaines dimensions et mesures peuvent être utilisées dans l’entrepôt de données, alors qu’elles ne sont pas disponibles avec d’autres fonctionnalités d’Adobe Analytics.

### Dimensions prises en charge exclusivement

* Experience Cloud ID : Pour les implémentations qui utilisent le service d’ID d’expérience (ECID), un nombre de 128 bits composé de deux nombres 64 bits concaténés est ajouté à 19 chiffres.
* URL de la page : URL de la page sur laquelle l’accès s’est produit.
* ID d’achat : Identificateur unique d’un achat, défini à l’aide de la variable purchaseID.
* Identifiant visiteur : Fournit l’identifiant unique du visiteur. Cette valeur est identique à la valeur concaténée de `visid_high` et `visid_low` de colonnes dans les flux de données. Pour plus d’informations, voir Référence [de colonne de](../analytics-data-feed/c-df-contents/datafeeds-reference.md) données sous Flux de données.

### Mesures prises en charge exclusivement

* Visites : Cette mesure dans le contexte de l’entrepôt de données exclut les visites de cookies non persistants.
* Visites - Tous les visiteurs : Cette mesure dans le contexte de l’entrepôt de données est plus proche de la mesure des visites dans d’autres outils d’Adobe Analytics.

## Composants non pris en charge dans Data Warehouse

Certaines dimensions et mesures ne sont pas prises en charge dans l’entrepôt de données.

> [!NOTE] Si une dimension ou une mesure n’est pas prise en charge dans l’entrepôt de données, les segments utilisant ces composants ne sont pas non plus pris en charge. Vérifiez toujours la compatibilité des produits lors de la création ou de la modification d’un segment.

### Dimensions non prises en charge

* Certaines dimensions temporelles, notamment :
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
* Certaines dimensions basées sur le cheminement, notamment :
   * Toutes les dimensions d’entrée, à l’exception de la page d’entrée
   * Toutes les dimensions de sortie, à l’exception des pages de sortie et du lien de sortie
   * Détail des accès
   * Fréquence des retours
   * Durée avant événement
   * Durée de consultation de la page – Regroupement
   * Durée par visite – Regroupement
   * Profondeur de visite
* Classement de toutes les pages de recherche
* Variables de hiérarchie
* Type d’accès
* Pages introuvables (disponible en tant que dimension) ; non pris en charge pour la segmentation)
* Recherche payante
* Visites sur une seule page
* Suivi du motif d’exclusion
* États américains

### Mesures non prises en charge

* Certaines mesures basées sur le cheminement, notamment :
   * Retours
   * Entrées
   * Sorties
   * Actualisations
   * Accès unique
   * Mesures "Durée de la visite"
