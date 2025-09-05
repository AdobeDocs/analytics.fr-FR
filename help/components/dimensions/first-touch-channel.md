---
title: Canal Première touche
description: Premier canal marketing dans l’expiration de l’engagement du visiteur.
feature: Dimensions
exl-id: cca9794c-1305-4e54-aa13-809b9ebc6230
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 91%

---

# Canal Première touche

La [dimension](overview.md) « Canal Première touche » indique le premier canal marketing avec lequel un visiteur ou une visiteuse correspond au cours de sa période d’engagement (30 jours par défaut). Cette dimension est utile pour identifier les canaux marketing qui génèrent le trafic initial sur votre site, ce qui vous permet de concentrer les efforts marketing dans les domaines les plus efficaces.

## Renseignement de cette dimension avec des données

Cette dimension fait directement référence aux noms de canal que vous avez définis dans le [gestionnaire de canaux marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md).

Chaque accès envoyé aux serveurs de collecte de données d’Adobe est traité par le biais des règles de traitement de canal marketing de votre suite de rapports. Il effectue une itération sur chaque règle dans l’ordre numérique jusqu’à ce qu’il trouve une correspondance, où le canal marketing est lié à l’accès. Le canal Première touche persiste pour le visiteur jusqu’à ce que le délai avant la prochaine visite du visiteur dépasse la période d’engagement du visiteur (30 jours par défaut).

Pour définir une valeur spécifique sur cette dimension, procédez comme suit :

* Définissez l’élément de dimension de votre choix comme canal dans le gestionnaire de canaux marketing, sous Paramètres de la suite de rapports.
* Définissez une règle de traitement des canaux marketing qui contient les critères de votre choix pour l’accès.
* L’accès du visiteur à votre site doit correspondre aux critères décrits dans la règle de traitement des canaux marketing _et_ doit être la première valeur de canal marketing à le faire au cours de la période d’engagement du visiteur.

Si un accès ultérieur correspond à des critères sous un autre canal marketing, cette dimension n’est pas remplacée par le nouveau canal marketing.

## Éléments de dimension

Les éléments de dimension incluent tout nom de canal dans le gestionnaire de canaux marketing. Par défaut, les valeurs comprennent `"Paid search"`, `"Natural search"`, `"Display"`, `"Email"`, `"Affiliate"`, `"Direct"`, `"Internal"`, `"Social networks"` et `"Referring domains"`. Vous pouvez ajouter ou supprimer des canaux dans le gestionnaire de canaux marketing, ce qui affecte les valeurs de cette dimension.
