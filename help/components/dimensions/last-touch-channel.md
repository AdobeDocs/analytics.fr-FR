---
title: canal Dernière touche
description: canal marketing le plus récent dans l’expiration de l’engagement du visiteur.
translation-type: tm+mt
source-git-commit: 2c262e5345c39a71a6a54062c607273528294b24
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---


# canal Dernière touche

La dimension &quot;canal Dernière touche&quot; signale le canal marketing le plus récent auquel un visiteur correspond au cours de la période d’engagement de ce visiteur (30 jours par défaut). Cette dimension est utile pour identifier les canaux marketing qui génèrent des conversions sur votre site, ce qui vous permet de concentrer les efforts marketing dans les domaines les plus efficaces.

## Renseigner cette dimension avec des données

Cette dimension fait directement référence aux noms de canal que vous avez définis dans le gestionnaire [de canaux](/help/admin/admin/marketing-channels-admin.md)marketing.

Chaque accès envoyé aux serveurs de collecte de données Adobe s’exécute par le biais des règles de traitement du canal marketing de votre suite de rapports. Il effectue une itération sur chaque règle dans l’ordre numérique jusqu’à ce qu’il trouve une correspondance, dans laquelle ce canal marketing est lié à l’accès. Le canal Dernière touche persiste avec le visiteur jusqu’à ce qu’il ne visite pas le site plus longtemps que la période d’engagement du visiteur (30 jours par défaut).

Pour définir cette dimension sur une valeur spécifique, procédez comme suit :

* Définissez la valeur de dimension souhaitée en tant que canal dans le Gestionnaire de canaux marketing sous Paramètres de la suite de rapports.
* Définissez une règle de traitement du canal marketing qui contient les critères de votre choix pour l’accès.
* L’visiteur qui a accédé à votre site doit correspondre aux critères décrits dans la règle de traitement du canal marketing.

## Valeurs de dimension

Les valeurs de dimension incluent tout nom de canal dans le Gestionnaire de canaux marketing. Par défaut, les valeurs comprennent `"Paid search"`, `"Natural search"`, `"Display"`, `"Email"`, `"Affiliate"`, `"Direct"`, `"Internal"`,  et . `"Social networks"``"Referring domains"` Vous pouvez ajouter ou supprimer des canaux dans le Gestionnaire de canaux marketing, ce qui affecte les valeurs de cette dimension.
