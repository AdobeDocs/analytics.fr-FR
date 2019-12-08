---
description: Décrit la manière dont le créateur de rapports prend en charge les rapports de cheminement et d’abandons et en quoi l’implémentation diffère des rapports et analyses.
title: Rapports Chemin et Abandon de chemin dans Report Builder
topic: Report builder
uuid: 9ca6cb97-8f31-46f6-977a-e81a89a176d1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Rapports Chemin et Abandon de chemin dans Report Builder

Décrit la manière dont le créateur de rapports prend en charge les rapports de cheminement et d’abandons et en quoi l’implémentation diffère des rapports et analyses.

| Nom du rapport Chemin dans les rapports et analyses (Chemins &gt; dimension &gt;) | Pris en charge dans le Créateur de rapports ? |
|--- |--- |
| Flux de dimension suivante/précédente | Non fourni en tant que rapport autonome. Peut être reproduit avec plusieurs requêtes avec la dimension Chemin et en utilisant un filtre. |
| Suivant/Précédent  dimension | Non fourni en tant que rapport autonome. Peut être reproduit avec un rapport de cheminement et en utilisant un filtre. |
| Abandon | Pris en charge et fourni en tant que rapport autonome ( Chemins &gt; dimension &gt; Abandon de dimension). |
| Chemins complets | Non pris en charge. |
| Pathfinder | Non fourni en tant que rapport autonome. Peut être reproduit en tant que rapport de cheminement utilisant un filtre. |
| Longueur de chemin | Pris en charge uniquement pour la dimension Page. |
| Analyse de page &gt;  résumé des dimensions | Non fourni en tant que rapport autonome. Peut être reproduit avec plusieurs requêtes avec la dimension Chemin et en utilisant un filtre. |
| Analyse de page &gt; Actualisations | Non fourni en tant que rapport autonome. Peut être reproduit avec un rapport Dimension utilisant la mesure Actualisations. |
| Analyse de page &gt; Profondeur de dimension | Pris en charge uniquement pour la dimension Page. |
| Analyse de page &gt; Durée de consultation de la dimension | Non pris en charge. |
| Entrées et sorties &gt; Pages d’entrée | Non fourni en tant que rapport autonome. Peut être reproduit en tant que rapport de cheminement utilisant le filtre prédéfini Site d’entrée. |
| Entrées et sorties &gt; Pages d’entrée originales | Pris en charge uniquement pour la dimension Page. |
| Entrées et sorties &gt; Visites sur une seule page | Non fourni en tant que rapport autonome. Peut être reproduit en tant que rapport de cheminement utilisant un filtre prédéfini. |
| Entrées et sorties &gt; Dimension Sortie | Non fourni en tant que rapport autonome. Peut être reproduit en tant que rapport Chemin utilisant le filtre prédéfini Site de sortie. |
