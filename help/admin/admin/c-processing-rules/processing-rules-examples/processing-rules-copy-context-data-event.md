---
description: Les règles de traitement peuvent déclencher des événements sur la base de variables Données contextuelles.
seo-description: Les règles de traitement peuvent déclencher des événements sur la base de variables Données contextuelles.
seo-title: Définition d'un événement à l'aide d'une variable de données contextuelles
solution: Analytics
subtopic: Règles de traitement
title: Définition d'un événement à l'aide d'une variable de données contextuelles
topic: Outils d’administration
uuid: 4 a 6018 eb -03 e 2-4 ec 8-874 b-e 48 bf 716 e 103
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Définition d'un événement à l'aide d'une variable de données contextuelles

Les règles de traitement peuvent déclencher des événements sur la base de variables Données contextuelles.

Les variables de données contextuelles sont spécifiées dans AppMeasurement au format suivant :

```
 s.contextData['search_term']
```

La liste [!UICONTROL Variables contextuelles] contient toutes les variables qui ont été envoyées à la suite de rapports au cours des 30 derniers jours. If you know the context data variable name but have not sent it into the current report suite, you can add a value by typing the variable name and clicking **[!UICONTROL Add variable name context data]**:

![](assets/add-context-variable.png)

The following rule definition expands on the [Copy a Context Data Variable to an eVar](../../../../admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md#concept_43AA4980A2D847D6A3BEC50BCC0780E7) rule to also set an event on every hit that contains a specific context data variable:

| Jeu de règles | Valeur |
|---|---|
| Condition | Si les données contextuelles « terme_recherché » sont définies |
| Action | Définir l’événement « recherches » |

Par exemple :

![](assets/processing_rule_set_event.png)

Reportez-vous à la rubrique [Variables Données contextuelles](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=context_data_variables) dans l’aide d’implémentation.
