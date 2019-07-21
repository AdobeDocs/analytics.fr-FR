---
description: Décrit la manière dont le créateur de rapports prend en charge les rapports de cheminement et d'abandon et explique comment l'implémentation diffère des rapports et analyses.
seo-description: Décrit la manière dont le créateur de rapports prend en charge les rapports de cheminement et d'abandon et explique comment l'implémentation diffère des rapports et analyses.
seo-title: Rapports Chemin et Abandon de chemin dans le créateur de rapports
solution: Analytics
title: Rapports Chemin et Abandon de chemin dans le créateur de rapports
topic: Créateur de rapports
uuid: 9 ca 6 cb 97-8 f 31-46 f 6-977 a-e 81 a 89 a 176 d 1
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Rapports Chemin et Abandon de chemin dans le créateur de rapports

Décrit la manière dont le créateur de rapports prend en charge les rapports de cheminement et d'abandon et explique comment l'implémentation diffère des rapports et analyses.

| Nom du rapport Chemin dans les rapports et analyses (Chemins &gt; dimension &gt;) | Pris en charge dans le Créateur de rapports ? |
|--- |--- |
| Flux de dimension Suivant/Précédent | Non fourni en tant que rapport autonome. Peut être reproduit avec plusieurs requêtes avec la dimension Chemin et en utilisant un filtre. |
| Suivant/Précédent  dimension | Non fourni en tant que rapport autonome. Peut être reproduit avec un rapport de cheminement et en utilisant un filtre. |
| Abandon | Pris en charge et fourni en tant que rapport autonome (Chemins &gt; dimension &gt; Dimension Abandon). |
| Chemins complets | Non pris en charge. |
| PathFinder | Non fourni en tant que rapport autonome. Peut être reproduit en tant que rapport de cheminement utilisant un filtre. |
| Longueur de chemin | Pris en charge uniquement pour la dimension Page. |
| Analyse de page &gt;  Résumé de la dimension | Non fourni en tant que rapport autonome. Peut être reproduit avec plusieurs requêtes avec la dimension Chemin et en utilisant un filtre. |
| Analyse de page &gt; Actualisations | Non fourni en tant que rapport autonome. Peut être reproduit avec un rapport Dimension utilisant la mesure Actualisations. |
| Analyse de page &gt; Profondeur de dimension | Pris en charge uniquement pour la dimension Page. |
| Analyse de page &gt; Durée de consultation de la dimension | Non pris en charge. |
| Entrées et sorties &gt; Pages d’entrée | Non fourni en tant que rapport autonome. Peut être reproduit en tant que rapport de cheminement utilisant le filtre prédéfini Site d’entrée. |
| Entrées et sorties &gt; Pages d’entrée originales | Pris en charge uniquement pour la dimension Page. |
| Entrées et sorties &gt; Visites sur une seule page | Non fourni en tant que rapport autonome. Peut être reproduit en tant que rapport de cheminement utilisant un filtre prédéfini. |
| Entrées et sorties &gt; Quitter  dimension | Non fourni en tant que rapport autonome. Peut être reproduit en tant que rapport Chemin utilisant le filtre prédéfini Site de sortie. |