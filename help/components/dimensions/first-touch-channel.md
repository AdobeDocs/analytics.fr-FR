---
title: Canal Première touche
description: Premier canal marketing dans l’expiration de l’engagement du visiteur.
feature: Dimensions
exl-id: cca9794c-1305-4e54-aa13-809b9ebc6230
TQID: https://experienceleague.adobe.com/1XBUjwxlZXmhXJtQZgpv9yU5Fwhns-bb9Q7BcP5S30Q
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
    internal-label: Marketing Channels
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
    internal-label: Report Suite settings
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 67%
---
# Canal Première touche

La [dimension](overview.md) « Canal Première touche » indique le premier canal marketing avec lequel un visiteur ou une visiteuse correspond au cours de sa période d’engagement (30 jours par défaut). Cette dimension est utile pour identifier les canaux marketing qui génèrent le trafic initial sur votre site, ce qui vous permet de concentrer les efforts marketing dans les domaines les plus efficaces.

## Renseignement de cette dimension avec des données

Cette dimension est dérivée des règles de traitement des canaux marketing. Il fait directement référence aux noms de canal que vous avez définis dans le [gestionnaire de canaux marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md). Chaque accès s’exécute dans l’ordre numérique des règles de traitement du canal marketing de votre suite de rapports jusqu’à ce qu’elle trouve une correspondance, ce qui lie ce canal marketing à l’accès. Aucune variable à définir.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucun (dérivé des règles de traitement des canaux marketing) |
| **Champ Web SDK/XDM** | Aucun (dérivé des règles de traitement des canaux marketing) |
| **Paramètre de requête** | S.O. |
| **Balise XML** | S.O. |
| **Limite d’octets** | S.O. |
| **Persistance** | Configurable |

Le canal Première touche persiste pour le visiteur jusqu’à ce qu’il ne consulte plus le site pendant une durée supérieure à la période d’engagement du visiteur (30 jours par défaut).

Pour définir une valeur spécifique sur cette dimension, procédez comme suit :

* Définissez l’élément de dimension de votre choix comme canal dans le gestionnaire de canaux marketing, sous Paramètres de suite de rapports.
* Définissez une règle de traitement des canaux marketing qui contient les critères de votre choix pour l’accès.
* Le hit du visiteur sur votre site doit correspondre aux critères décrits dans la règle de traitement des canaux marketing _et_ doit être la première valeur de canal marketing à le faire au cours de la période d’engagement du visiteur.

Si un accès ultérieur correspond à des critères sous un autre canal marketing, cette dimension n’est pas remplacée par le nouveau canal marketing.

## Éléments de dimension

Les éléments de dimension incluent tout nom de canal dans le gestionnaire de canaux marketing. Par défaut, les valeurs comprennent `"Paid search"`, `"Natural search"`, `"Display"`, `"Email"`, `"Affiliate"`, `"Direct"`, `"Internal"`, `"Social networks"` et `"Referring domains"`. Vous pouvez ajouter ou supprimer des canaux dans le gestionnaire de canaux marketing, ce qui affecte les valeurs de cette dimension.
