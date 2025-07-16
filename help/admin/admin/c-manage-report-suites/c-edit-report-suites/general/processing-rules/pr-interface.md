---
title: Interface des règles de traitement
description: Naviguez dans l’interface pour créer, modifier ou supprimer des règles de traitement.
feature: Processing Rules
role: Admin
source-git-commit: c2adf6d2e328378332cc290ba2dfd75ee6587ef6
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---

# Interface des règles de traitement

L’interface des règles de traitement vous permet de créer, modifier ou supprimer des règles de traitement.

**[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > Sélectionner une suite de rapports > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Général]** > **[!UICONTROL Règles de traitement]**

>[!WARNING]
>
>Les règles de traitement affectent directement la collecte de données et peuvent entraîner une perte de données si elles sont utilisées de manière incorrecte. Testez toujours les règles de traitement dans une suite de rapports de développement avant de les activer dans une suite de rapports de production afin de limiter les problèmes de qualité des données.

## Structure globale

Cette interface contient deux composants principaux :

* **[!UICONTROL Ordre de traitement]** : les règles s’exécutent exactement dans l’ordre que vous avez spécifié, à partir de la règle 1. Chaque accès passe par chaque règle ; il n’existe aucune condition de sortie anticipée. Assurez-vous que les conditions de chaque règle de traitement prennent en compte chaque accès envoyé à la suite de rapports.
* **[!UICONTROL Jeux de règles]** : les définitions de chacune de vos règles de traitement.

Vous pouvez avoir jusqu’à 150 règles de traitement et 30 conditions par règle de traitement. Il n’existe pas de limite raisonnable au nombre d’actions par règle de traitement.

## Structure de l’ensemble de règles

Chaque règle de traitement contient les sections suivantes :

* **Titre de la règle** : libellé de la règle. Cela n’a aucune incidence sur la logique des règles de traitement, mais s’avère utile pour effectuer le suivi de la fonction de la règle.
* **Condition** : affiché comme texte, « [!UICONTROL  Si l’une ou l’autre des conditions suivantes est vraie ] ». Si vous n’incluez pas de condition, la règle s’exécute toujours sur chaque accès.
* **Action** : si aucune condition n’existe, le texte s’affiche sous la forme « [!UICONTROL Toujours exécuter] ». S’il existe une condition, le texte s’affiche sous la forme « [!UICONTROL Procédez comme suit ] ». Si la condition ci-dessus est évaluée comme `true`, chaque action répertoriée dans cette section peut s’exécuter. Outre la condition d’une règle, vous pouvez _également_ associer des conditions à des actions individuelles. Les actions disponibles sont les suivantes :
   * **[!UICONTROL Remplacer la valeur de]** : remplace la variable souhaitée par une autre variable, une valeur statique ou une valeur concaténée.
   * **[!UICONTROL Supprimer la valeur de]** : supprime la valeur de variable souhaitée pour cet accès.
   * **[!UICONTROL Définir l’événement]** : déclenche l’événement souhaité. En règle générale, vous définissez les événements sur une valeur personnalisée de `1` ; la définition d’événements sur des valeurs autres que `1` ou même leur définition sur des valeurs définies dans des variables de données contextuelles est également autorisée.
* **Action sinon** : si une condition existe, cette section apparaît sous la forme « [!UICONTROL Sinon, procédez comme suit] ». Si la condition ci-dessus est évaluée comme `false`, chaque action répertoriée dans cette section peut s’exécuter. Cette section suit les mêmes actions de règle que ci-dessus, notamment la possibilité de remplacer des valeurs, de supprimer des valeurs et de définir des événements.
* **Raison** : enregistrez qui a demandé la règle et ce dont elle dépend. Cela n’a aucune incidence sur la logique des règles de traitement, mais est utile pour suivre la raison d’être de la règle.

Consultez [Dimensions et mesures disponibles pour les règles de traitement](pr-variables.md) pour obtenir une liste complète des variables que vous pouvez utiliser dans cette interface.

* Toute variable qui autorise la « lecture » peut être utilisée dans une condition.
* Toute variable qui autorise « Write » peut être utilisée dans une action.
