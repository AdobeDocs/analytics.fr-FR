---
description: Description des champs et informations sur les variables lors de l’utilisation de Dynamic Tag Management pour déployer Adobe Analytics.
keywords: Dynamic Tag Management;global variables;server variable;evar;props;dynamic variable prefix;dynamic variable
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: Variables globales
uuid: d759320a-96ee-4073-b5fd-5257b7033003
translation-type: ht
source-git-commit: 664d0cde8b8b17c86b47858611d459026aab0bef

---


# Variables globales

Description des champs et informations sur les variables lors de l’utilisation de Dynamic Tag Management pour déployer Adobe Analytics.

Ces variables se déclenchent sur toutes les balises de règle de chargement de page. Vous pouvez obtenir le même effet en utilisant une [règle de chargement de page](/help/implement/other/dtm/c-rules/t-rules-page-conditions.md) définie pour se déclencher sur toutes les pages. Il se peut que ces variables ne se déclenchent pas dans les règles [d’appel direct](/help/implement/other/dtm/c-rules/t-rules-direct-conditions.md) et [basées sur un événement](/help/implement/other/dtm/c-rules/t-rules-event-conditions.md).

## Variables globales - Description des champs {#section_2917F62FCC8D43F982B2612A702DEF81}

**[!UICONTROL *`Property`*]** > ![](assets/settings_gear.png)**[!UICONTROL  Modifier l’outil ]** > **[!UICONTROL  Variables globales ]**

| Élément | Description |
|--- |--- |
| Serveur | La variable prédéfinie renseigne la dimension Serveurs dans Adobe Analytics. Voir [Serveur](../../../vars/page-vars/server.md). |
| eVars | [Les variables eVar](../../../vars/page-vars/evar.md) sont utilisées pour créer des rapports de conversion personnalisés. |
| Propriétés | [Les variables de propriété (prop)](../../../vars/page-vars/prop.md) sont utilisées pour créer des rapports de trafic personnalisés. |
| Préfixe de variable dynamique | Préfixe spécial au début de la valeur. Le préfixe par défaut est « D= ». Voir [Variables dynamiques](../../../vars/page-vars/dynamic-variables.md). |
