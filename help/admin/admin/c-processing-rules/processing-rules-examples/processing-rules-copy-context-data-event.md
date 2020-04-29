---
description: Les règles de traitement peuvent déclencher des événements sur la base de variables Données contextuelles.
subtopic: Processing rules
title: Définir un événement à l’aide d’une variable de données contextuelles
topic: Admin tools
uuid: 4a6018eb-03e2-4ec8-874b-e48bf716e103
translation-type: tm+mt
source-git-commit: 327fdfd6a6d6bfe1c7bae9825fc8812b5ac7d095

---


# Définir un événement à l’aide d’une variable de données contextuelles

Les règles de traitement peuvent déclencher des événements sur la base de variables Données contextuelles.

Les variables de données contextuelles sont spécifiées dans AppMeasurement au format suivant :

```
 s.contextData['search_term']
```

The [!UICONTROL Context Variables] list contains all variables that were sent to the report suite in the previous 30 days. If you know the context data variable name but have not sent it into the current report suite, you can add a value by typing the variable name and clicking **[!UICONTROL Add variable name context data]**:

![](assets/add-context-variable.png)

La définition de règle suivante s’étend à la règle [Copier une variable de données contextuelles dans une eVar](/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md) pour créer également un événement sur chaque accès contenant une variable de données contextuelles spécifique :

| Jeu de règles | Valeur |
|---|---|
| Condition | Si les données contextuelles « terme_recherché » sont définies |
| Action | Définir l’événement « recherches » |

Par exemple :

![](assets/processing_rule_set_event.png)

Reportez-vous à la rubrique [Variables Données contextuelles](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/contextdata.html) dans l’aide d’implémentation.
