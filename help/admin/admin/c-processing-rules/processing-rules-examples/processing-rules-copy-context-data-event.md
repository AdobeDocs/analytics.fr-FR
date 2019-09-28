---
description: Les règles de traitement peuvent déclencher des événements sur la base de variables Données contextuelles.
seo-description: Les règles de traitement peuvent déclencher des événements sur la base de variables Données contextuelles.
seo-title: Définir un événement à l’aide d’une variable de données contextuelles
solution: Analytics
subtopic: Règles de traitement
title: Définir un événement à l’aide d’une variable de données contextuelles
topic: Outils d’administration
uuid: 4a6018eb-03e2-4ec8-874b-e48bf716e103
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Définir un événement à l’aide d’une variable de données contextuelles

Les règles de traitement peuvent déclencher des événements sur la base de variables Données contextuelles.

Les variables de données contextuelles sont spécifiées dans AppMeasurement au format suivant :

```
 s.contextData['search_term']
```

La liste [!UICONTROL Variables contextuelles] contient toutes les variables qui ont été envoyées à la suite de rapports au cours des 30 derniers jours. If you know the context data variable name but have not sent it into the current report suite, you can add a value by typing the variable name and clicking **[!UICONTROL Add variable name context data]**:

![](assets/add-context-variable.png)

La définition de règle suivante s’étend sur la règle [Copier une variable de données contextuelles dans une règle d’eVar](../../../../admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md#concept_43AA4980A2D847D6A3BEC50BCC0780E7) pour définir également un événement pour chaque accès contenant une variable de données contextuelles spécifique :

| Jeu de règles | Valeur |
|---|---|
| Condition | Si les données contextuelles « terme_recherché » sont définies |
| Action | Définir l’événement « recherches » |

Par exemple :

![](assets/processing_rule_set_event.png)

Reportez-vous à la rubrique [Variables Données contextuelles](https://marketing.adobe.com/resources/help/en_US/sc/implement/context_data_variables.html) dans l’aide d’implémentation.
