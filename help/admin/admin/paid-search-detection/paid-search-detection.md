---
description: 'La détection de recherche payante fait la distinction entre les recherches payantes et les recherches naturelles dans les rapports Moteurs de recherche et Mots-clés de recherche. '
title: Détection de recherche payante
feature: Admin Tools
exl-id: 6b513ad2-f955-4a34-92f8-57a141e44801
source-git-commit: 2c0aef13bdb88b0a7aa9f100c72c21f66a14c8dd
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 71%

---

# Détection de recherche payante

[!UICONTROL La détection de recherche payante fait la distinction entre les recherches payantes et les recherches naturelles dans les rapports Moteurs de recherche et Mots-clés de recherche. ] Vous pouvez indiquer les moteurs de recherche dans lesquels vous utilisez des annonces publicitaires payantes et spécifier une chaîne de caractères située dans l’URL d’une visite effectuée à partir d’une annonce payante.

## Options de configuration {#section_0C2CFA0AF77B47098BE37CB024665D0D}

Le tableau suivant décrit les champs et options utilisés pour [configurer la détection de référencement payant](/help/admin/admin/paid-search-detection/t-paid-search-detection.md).

| Option | Description |
| --- | --- |
| [!UICONTROL Moteur de recherche ] | Sélectionnez un moteur de recherche dans la liste déroulante. Indiquez le moteur si vous utilisez des paramètres de chaîne de requête différents en fonction des moteurs de recherche. En règle générale, la valeur `Any` est suffisante. |
| [!UICONTROL Chaîne de requête] | Indique une chaîne pour une correspondance sensible à la casse avec une partie du paramètre de chaîne de requête, qui fait partie de l’URL située après le &quot;?&quot;. <br>**Remarque**: [!UICONTROL Détection de recherche payante] est sensible à la casse. Par exemple, une règle qui spécifie &quot;PID&quot; comme paramètre de chaîne de requête ne correspond pas à &quot;pid&quot;. Si votre entreprise utilise une casse mixte (combinaison de majuscules et de minuscules), placez les valeurs exactes en tant que règles distinctes, de telle sorte que tous les paramètres de chaîne de requête souhaités puissent être capturés. |
