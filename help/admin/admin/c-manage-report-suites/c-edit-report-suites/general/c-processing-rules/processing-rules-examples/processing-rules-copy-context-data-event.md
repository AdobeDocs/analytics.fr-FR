---
description: Les règles de traitement peuvent déclencher des événements sur la base de variables Données contextuelles.
subtopic: Processing rules
title: Définir un événement à l’aide d’une variable de données contextuelles
feature: Admin Tools
uuid: 4a6018eb-03e2-4ec8-874b-e48bf716e103
exl-id: f0af0e23-c08a-4f82-85b4-25064eeaa3c6
source-git-commit: 71ff81a0ae67c6f4cc9a8df567e27223cc63f18c
workflow-type: ht
source-wordcount: '163'
ht-degree: 100%

---

# Définir un événement à l’aide d’une variable de données contextuelles

Les règles de traitement peuvent déclencher des événements sur la base de variables Données contextuelles.

Les variables de données contextuelles sont spécifiées dans AppMeasurement au format suivant :

```
 s.contextData['search_term']
```

La liste [!UICONTROL Variables contextuelles] contient toutes les variables qui ont été envoyées à la suite de rapports au cours des 30 derniers jours. Si vous connaissez le nom de la variable de données contextuelles, mais ne l’avez pas envoyée dans la suite de rapports actuelle, vous pouvez ajouter une valeur en entrant le nom de la variable et en cliquant sur **[!UICONTROL Ajouter les données contextuelles nom de la variable]** :

![](assets/add-context-variable.png)

La définition de règle suivante s’étend à la règle [Copier une variable de données contextuelles dans une eVar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md) pour créer également un événement sur chaque accès contenant une variable de données contextuelles spécifique :

| Jeu de règles | Valeur |
|---|---|
| Condition | Si les données contextuelles « terme_recherché » sont définies |
| Action | Définir l’événement « recherches » |

Par exemple :

![](assets/processing_rule_set_event.png)

Reportez-vous à la rubrique [Variables Données contextuelles](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/contextdata.html?lang=fr) dans l’aide d’implémentation.
