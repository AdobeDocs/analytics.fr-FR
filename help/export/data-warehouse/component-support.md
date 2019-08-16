---
title: Prise en charge des composants dans l'entrepôt de données
description: Découvrez les dimensions et mesures supplémentaires disponibles dans Data Warehouse et ce qui n'est pas pris en charge.
translation-type: tm+mt
source-git-commit: 8f3f11ada9bd12498dc40931cc987aa550b8d655

---


# Prise en charge des composants dans l'entrepôt de données

L'architecture de traitement unique de l'entrepôt de données permet à certains composants qui ne sont généralement pas disponibles dans d'autres fonctionnalités d'Adobe Analytics. En raison de son architecture unique, certains composants ne sont pas disponibles dans les rapports ou les segments. Utilisez cette page pour comprendre ce qui peut être utilisé et ce qui ne le peut pas.

## Composants propres à l'entrepôt de données

Certaines dimensions et mesures peuvent être utilisées dans l'entrepôt de données, alors qu'elles ne sont pas disponibles à l'aide d'autres fonctionnalités dans Adobe Analytics.

### Dimensions prises en charge exclusivement

* Identifiant visiteur Experience Cloud : Pour les implémentations qui utilisent le service d'ID d'expérience (ECID), un nombre 128 bits composé de deux nombres 64 bits concaténés ajoutés à 19 chiffres.
* URL de la page : URL de la page sur laquelle l'accès a eu lieu.
* ID d'achat : Identifiant unique d'un achat, défini à l'aide de la variable purchaseid.
* Identifiant visiteur : Fournit l'identifiant unique du visiteur. Cette valeur est identique à la valeur concaténée des `visid_high` colonnes et `visid_low` des flux de données. Pour [plus d'informations, voir Référence](../analytics-data-feed/c-df-contents/datafeeds-reference.md) de colonne de données sous Flux de données.

### Mesures prises en charge exclusivement

* Visites : Cette mesure dans le contexte de l'entrepôt de données exclut les visites de cookies non persistantes.
* Visites - Tous les visiteurs : Cette mesure dans le contexte de l'entrepôt de données est plus proche de la mesure Visites dans d'autres outils d'Adobe Analytics.

## Composants non pris en charge dans l'entrepôt de données

Certaines dimensions et mesures ne sont pas prises en charge dans Data Warehouse.

> [!NOTE] Si une dimension ou une mesure n'est pas prise en charge dans l'entrepôt de données, les segments utilisant ces composants ne sont pas non plus pris en charge. Vérifiez toujours la compatibilité des produits lors de la création ou de la modification d'un segment.

### Dimensions non prises en charge

* Certaines dimensions temporelles, dont :
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
* Certaines dimensions basées sur le cheminement, dont :
   * Toutes les dimensions d'entrée, à l'exception de Page d'entrée
   * Toutes les dimensions de sortie, à l'exception des liens de sortie et de sortie
   * Détail des accès
   * Fréquence des retours
   * Durée avant événement
   * Durée de consultation de la page – Regroupement
   * Durée par visite – Regroupement
   * Profondeur de visite
* Classement de toutes les pages de recherche
* Variables de hiérarchie
* Type d’accès
* Pages introuvables (disponibles sous forme de dimension ; non pris en charge pour la segmentation)
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
   * Mesures de durée de la visite
