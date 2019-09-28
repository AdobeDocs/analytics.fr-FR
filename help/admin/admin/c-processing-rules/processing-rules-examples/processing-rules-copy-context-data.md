---
description: Les règles de traitement servent à déplacer des valeurs des variables Données contextuelles vers des props et des eVars.
seo-description: Les règles de traitement servent à déplacer des valeurs des variables Données contextuelles vers des props et des eVars.
seo-title: Copier une variable de données contextuelles dans une eVar
solution: Analytics
subtopic: Règles de traitement
title: Copier une variable de données contextuelles dans une eVar
topic: Outils d’administration
uuid: 1beaec4c-71e9-49ce-b154-78408cc532a3
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Copier une variable de données contextuelles dans une eVar

Les règles de traitement servent à déplacer des valeurs des variables Données contextuelles vers des props et des eVars.

Les variables de données contextuelles sont spécifiées dans AppMeasurement au format suivant :

```
 s.contextData['search_term']
```

La liste [!UICONTROL Variables contextuelles] contient toutes les variables qui ont été envoyées à la suite de rapports au cours des 30 derniers jours. If you know the context data variable name but have not sent it into the current report suite, you can add a value by typing the variable name and clicking **[!UICONTROL Add variable name context data]**:

![](assets/add-context-variable.png)

La définition de règle suivante renseigne une eVar sur chaque accès contenant une variable de données contextuelles spécifique :

| Jeu de règles | Valeur |
|---|---|
| Condition | Si les données contextuelles « terme_recherché » sont définies |
| Action | Remplacer la valeur d’eVar3 par « terme_recherché » |

Par exemple :

![](assets/set-context-data.png)

Reportez-vous à la rubrique [Variables Données contextuelles](https://marketing.adobe.com/resources/help/en_US/sc/implement/context_data_variables.html) dans l’aide d’implémentation.
