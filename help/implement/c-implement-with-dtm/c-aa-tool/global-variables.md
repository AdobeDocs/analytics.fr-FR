---
description: Description des champs et informations sur les variables lors de l’utilisation de Dynamic Tag Management pour déployer Adobe Analytics.
keywords: Gestion dynamique des balises ; variables globales ; variable server ; evar ; props ; dynamic variable prefix ; variable dynamique
seo-description: Description des champs et informations sur les variables lors de l’utilisation de Dynamic Tag Management pour déployer Adobe Analytics.
seo-title: Variables globales
solution: Marketing Cloud, Analytics, gestion dynamique des balises
title: Variables globales
uuid: d 759320 a -96 ee -4073-b 5 fd -5257 b 7033003
translation-type: tm+mt
source-git-commit: 3489f00bd7dddefda0420fc361056416f6f10d3f

---


# Variables globales

Description des champs et informations sur les variables lors de l’utilisation de Dynamic Tag Management pour déployer Adobe Analytics.

Ces variables se déclenchent sur toutes les balises de règle de chargement de page. Vous pouvez obtenir le même effet en utilisant une [règle de chargement de page](../../../implement/c-implement-with-dtm/c-rules/t-rules-page-conditions.md#task_69B41CB230EE4530A755D91233F73706) définie pour se déclencher sur toutes les pages. These variables might not fire in [Direct-Call](../../../implement/c-implement-with-dtm/c-rules/t-rules-direct-conditions.md#task_85EB8F01775A402BA53B8298F0AADA09) and [Event-Based](../../../implement/c-implement-with-dtm/c-rules/t-rules-event-conditions.md#task_A122DE72110F4579A91F9D96D92D39FC) rules.

## Variables globales - Description des champs {#section_2917F62FCC8D43F982B2612A702DEF81}

**[!UICONTROL *`Property`*]** &gt; ![](assets/settings_gear.png)**[!UICONTROL Modifier l'outil]** &gt; **[!UICONTROL Variables globales]**

| Élément | Description |
|--- |--- |
| Serveur | La variable prédéfinie renseigne la dimension Servers dans Adobe Analytics. See [Page Variables](/help/implement/js-implementation/c-variables/page-variables.md) |
| eVars | [Les variables evar](/help/implement/js-implementation/c-variables/page-variables.md) sont utilisées pour créer des rapports de conversion personnalisés. |
| Propriétés | [Les variables prop](/help/implement/js-implementation/c-variables/page-variables.md) sont utilisées pour créer des rapports de trafic personnalisés. |
| Préfixe de variable dynamique | Préfixe spécial au début de la valeur. Le préfixe par défaut est « D= ». Voir [Variables dynamiques](/help/implement/js-implementation/c-variables/dynvars-overview.md) |
