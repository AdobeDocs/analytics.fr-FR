---
title: Canal Dernière touche
description: Canal marketing le plus récent dans l’expiration de l’engagement du visiteur.
feature: Dimensions
exl-id: 62a47de5-ee1a-4394-aa63-75cdda92ba6a
source-git-commit: 31c3f83f1142a4ba92a390e35ca8dcae66dfa660
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 67%

---

# Canal Dernière touche

La [dimension](overview.md) « Canal Dernière touche » indique le canal marketing le plus récent auquel un visiteur ou une visiteuse correspond au cours de sa période d’engagement (30 jours par défaut). Cette dimension est utile pour identifier les canaux marketing qui génèrent du trafic et des conversions sur votre site, ce qui vous permet de concentrer les efforts marketing dans les domaines les plus efficaces.

## Renseignement de cette dimension avec des données

Cette dimension fait directement référence aux noms de canal que vous avez définis dans le [gestionnaire de canaux marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md).

Chaque accès envoyé aux serveurs de collecte de données d’Adobe est traité par le biais des règles de traitement de canal marketing de votre suite de rapports. Il effectue une itération sur chaque règle dans l’ordre numérique jusqu’à ce qu’il trouve une correspondance, où le canal marketing est lié à l’accès. Le canal Dernière touche persiste pour le visiteur jusqu’à ce que le délai avant la prochaine visite du visiteur dépasse la période d’engagement du visiteur (30 jours par défaut).

Pour définir une valeur spécifique sur cette dimension, procédez comme suit :

* Définissez l’élément de dimension de votre choix comme canal dans le gestionnaire de canaux marketing, sous Paramètres de la suite de rapports.
* Définissez une règle de traitement des canaux marketing qui contient les critères de votre choix pour l’accès.
* L’accès du visiteur à votre site doit correspondre aux critères décrits dans la règle de traitement des canaux marketing.

>[!TIP]
>
>L’utilisation de cette dimension avec des mesures qui utilisent l’[attribution de participation](/help/analyze/analysis-workspace/attribution/models.md) peut attribuer du crédit à des `None` lorsque d’autres modèles d’attribution ne le font pas. Les mesures de participation nécessitent un canal marketing [instance](../metrics/instances.md) dans la fenêtre de création de rapports pour recevoir du crédit. Si le canal marketing a été initialement défini en dehors de la fenêtre de création de rapports et que seule la valeur persistante existe dans la fenêtre de création de rapports, les mesures de participation attribuent du crédit à `None`. D’autres modèles d’attribution attribuent du crédit à la valeur persistante. Si vous souhaitez éviter l’attribution aux `None` dans ce scénario, pensez à utiliser un modèle d’attribution de non-participation.

## Éléments de dimension

Les éléments de dimension incluent tout nom de canal dans le gestionnaire de canaux marketing. Par défaut, les valeurs comprennent `"Paid search"`, `"Natural search"`, `"Display"`, `"Email"`, `"Affiliate"`, `"Direct"`, `"Internal"`, `"Social networks"` et `"Referring domains"`. Vous pouvez ajouter ou supprimer des canaux dans le gestionnaire de canaux marketing, ce qui affecte les valeurs de cette dimension.
