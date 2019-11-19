---
description: Description des champs et informations sur les variables lors de l’utilisation de Dynamic Tag Management pour déployer Adobe Analytics.
keywords: Dynamic Tag Management;global variables;server variable;evar;props;dynamic variable prefix;dynamic variable
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: Variables globales
uuid: d759320a-96ee-4073-b5fd-5257b7033003
translation-type: tm+mt
source-git-commit: e9820869d16b8656ebebe11e397a3d7d8123fbcf

---


# Variables globales

Description des champs et informations sur les variables lors de l’utilisation de Dynamic Tag Management pour déployer Adobe Analytics.

Ces variables se déclenchent sur toutes les balises de règle de chargement de page. Vous pouvez obtenir le même effet en utilisant une [règle de chargement de page](/help/implement/c-implement-with-dtm/c-rules/t-rules-page-conditions.md) définie pour se déclencher sur toutes les pages. Il se peut que ces variables ne se déclenchent pas dans les règles [d’appel direct](/help/implement/c-implement-with-dtm/c-rules/t-rules-direct-conditions.md) et [basées sur un événement](/help/implement/c-implement-with-dtm/c-rules/t-rules-event-conditions.md).

## Variables globales - Description des champs {#section_2917F62FCC8D43F982B2612A702DEF81}

**[!UICONTROL *`Property`*]** &gt; ![](assets/settings_gear.png) **[!UICONTROL Modifier l’outil]** &gt; **[!UICONTROL Variables globales]**

| Élément | Description |
|--- |--- |
| Serveur | La variable prédéfinie renseigne la dimension Serveurs dans Adobe Analytics. Voir [Variables de page](/help/implement/js-implementation/page-variables/page-variables.md) |
| eVars | [Les variables eVar](/help/implement/js-implementation/page-variables/evarn.md) sont utilisées pour créer des rapports de conversion personnalisés. |
| Propriétés | [Les variables de propriété (prop)](/help/implement/js-implementation/page-variables/propn.md) sont utilisées pour créer des rapports de trafic personnalisés. |
| Préfixe de variable dynamique | Préfixe spécial au début de la valeur. Le préfixe par défaut est « D= ». Voir [Variables dynamiques](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/dynvars-overview.html) |
