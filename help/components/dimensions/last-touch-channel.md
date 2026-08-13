---
title: Canal Dernière touche
description: Canal marketing le plus récent dans l’expiration de l’engagement du visiteur.
feature: Dimensions
exl-id: 62a47de5-ee1a-4394-aa63-75cdda92ba6a
TQID: https://experienceleague.adobe.com/wUNsv-0snBfk6EE6yeCEuT8-hGvBu9U8tjKDfxhVRA0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705cid: f836f655-eebe-4b76-82bc-697955ec1ce3id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 337
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
