---
description: Description des champs et informations sur les variables lors de l’utilisation de Dynamic Tag Management pour déployer Adobe Analytics.
keywords: Dynamic Tag Management;variables globales;variable server;evar;propriétés;préfixe de variable dynamique;variable dynamique
seo-description: Description des champs et informations sur les variables lors de l’utilisation de Dynamic Tag Management pour déployer Adobe Analytics.
seo-title: Variables globales
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: Variables globales
uuid: d759320a-96ee-4073-b5fd-5257b7033003
translation-type: ht
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Variables globales

Description des champs et informations sur les variables lors de l’utilisation de Dynamic Tag Management pour déployer Adobe Analytics.

Ces variables se déclenchent sur toutes les balises de règle de chargement de page. Vous pouvez obtenir le même effet en utilisant une [règle de chargement de page](../../../implement/c-implement-with-dtm/c-rules/t-rules-page-conditions.md#task_69B41CB230EE4530A755D91233F73706) définie pour se déclencher sur toutes les pages. Il se peut que ces variables ne se déclenchent pas dans les règles [d’appel direct](../../../implement/c-implement-with-dtm/c-rules/t-rules-direct-conditions.md#task_85EB8F01775A402BA53B8298F0AADA09) et [basées sur un événement](../../../implement/c-implement-with-dtm/c-rules/t-rules-event-conditions.md#task_A122DE72110F4579A91F9D96D92D39FC).

## Variables globales - Description des champs {#section_2917F62FCC8D43F982B2612A702DEF81}

**[!UICONTROL *`Property`*]** &gt; ![](assets/settings_gear.png) **[!UICONTROL Modifier l’outil]** &gt; **[!UICONTROL Variables globales]**

| Élément | Description |
|--- |--- |
| Serveur | La variable prédéfinie renseigne la dimension Serveurs dans Adobe Analytics. Voir [Variables de page](/help/implement/js-implementation/c-variables/page-variables.md) |
| eVars | [Les variables eVar](/help/implement/js-implementation/c-variables/page-variables.md) sont utilisées pour créer des rapports de conversion personnalisés. |
| Propriétés | [Les variables de propriété (prop)](/help/implement/js-implementation/c-variables/page-variables.md) sont utilisées pour créer des rapports de trafic personnalisés. |
| Préfixe de variable dynamique | Préfixe spécial au début de la valeur. Le préfixe par défaut est « D= ». Voir [Variables dynamiques](/help/implement/js-implementation/c-variables/dynvars-overview.md) |
