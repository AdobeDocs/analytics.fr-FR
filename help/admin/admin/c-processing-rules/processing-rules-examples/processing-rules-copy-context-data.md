---
description: Les règles de traitement servent à déplacer des valeurs des variables Données contextuelles vers des props et des eVars.
seo-description: Les règles de traitement servent à déplacer des valeurs des variables Données contextuelles vers des props et des eVars.
seo-title: Copie d'une variable de données contextuelles dans une evar
solution: Analytics
subtopic: Règles de traitement
title: Copie d'une variable de données contextuelles dans une evar
topic: Outils d’administration
uuid: 1 beaec 4 c -71 e 9-49 ce-b 154-78408 cc 532 a 3
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Copie d'une variable de données contextuelles dans une evar

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

Reportez-vous à la rubrique [Variables Données contextuelles](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=context_data_variables) dans l’aide d’implémentation.
