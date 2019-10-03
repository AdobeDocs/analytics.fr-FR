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
source-git-commit: 2ea071c4d4f675c74770396610219d405a07a0e1

---


# Copier une variable de données contextuelles dans une eVar

Les règles de traitement permettent de déplacer des valeurs des variables de données contextuelles vers des props et des eVars. Without processing rules, context data variables are meaningless and do not populate any reports in Analytics.

La liste [!UICONTROL Variables contextuelles] contient toutes les variables qui ont été envoyées à la suite de rapports au cours des 30 derniers jours. If you know the context data variable name but have not sent it into the current report suite, you can add a value by typing the variable name and clicking **[!UICONTROL Add variable name context data]**:

![Ajouter](assets/add-context-variable.png)

The following example takes the  context data variable and places its value into :`search_term``eVar3`

![Définir](assets/set-context-data.png)

The above example works great when there are only a few eVars to populate. If your organization has hundreds of context data variables that each need their own eVar, you can use conditional statements. Des dizaines d’instructions conditionnelles peuvent s’intégrer à une règle de traitement unique, ce qui permet à votre entreprise de renseigner toutes les eVars d’une suite de rapports sans avoir à respecter la limite de 150 règles de traitement.

The following example populates  with the context data variable , but only if  is set:`prop7``testhierarchy``testhierarchy`

![Conditionnel](assets/add-conditional.png)

For more information on implementing context data variables, see Context data variables in the Implement user guide.[](../../../../implement/js-implementation/c-variables/context-data-variables.md)
