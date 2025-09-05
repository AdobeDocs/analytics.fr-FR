---
description: La détection de référencement payant fait la distinction entre les recherches payantes et les recherches naturelles dans les rapports Moteurs de recherche et Mots-clés de recherche.
title: Détection de recherche payante
feature: Admin Tools
exl-id: 6b513ad2-f955-4a34-92f8-57a141e44801
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 100%

---

# Détection de recherche payante

[!UICONTROL La détection de référencement payant] fait la distinction entre les recherches payantes et les recherches naturelles dans les rapports [!UICONTROL Moteurs de recherche] et [!UICONTROL Mots-clés de recherche]. Vous pouvez indiquer les moteurs de recherche dans lesquels vous utilisez des annonces publicitaires payantes et spécifier une chaîne de caractères située dans l’URL d’une visite effectuée à partir d’une annonce payante.

## Options de configuration {#configuration}

Le tableau suivant décrit les champs et options utilisés pour [configurer la détection de référencement payant](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/t-paid-search-detection.md).

| Option | Description |
| --- | --- |
| [!UICONTROL Moteur de recherche] | Sélectionnez un moteur de recherche dans la liste déroulante. Indiquez le moteur si vous utilisez des paramètres de chaîne de requête différents en fonction des moteurs de recherche. En règle générale, la valeur `Any` est suffisante. |
| [!UICONTROL Chaîne de requête] | Spécifie une chaîne pour une correspondance sensible à la casse avec nʼimporte quelle partie du paramètre de la chaîne de requête, qui est la partie de l’URL après le signe « ? ». <br>**Remarque** : [!UICONTROL la détection de référencement payant] est sensible à la casse. Par exemple, une règle qui spécifie « PID » comme paramètre de chaîne de requête ne tient pas compte de « pid ». Si votre entreprise utilise une casse mixte (combinaison de majuscules et de minuscules), placez les valeurs exactes en tant que règles distinctes, de telle sorte que tous les paramètres de chaîne de requête souhaités puissent être capturés. |
