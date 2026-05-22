---
title: trackingServer
description: Domaine utilisé pour envoyer des données à Adobe via HTTP.
feature: Appmeasurement Implementation
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/6H8uZ4J-mT8NcC4OiiTgtBnP8eAgaMMzxzUHkS-9kGs'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 120
ht-degree: 19%

---

# trackingServer

>[!IMPORTANT]
>
>Cette variable est obsolète. Avec la prévalence du HTTPS, utilisez plutôt [`trackingServerSecure`](trackingserversecure.md).

La variable `trackingServer` détermine le domaine utilisé par AppMeasurement pour envoyer des données à Adobe via HTTP. Si cette variable n’est pas correctement définie, votre mise en œuvre peut entraîner une perte de données.

Avant le service d’identités [&#128279;](https://experienceleague.adobe.com/fr/docs/id-service/using/home), cette variable déterminait également où les cookies tiers étaient définis. Adobe recommande vivement d’utiliser le service d’ID dans toutes les implémentations lorsque cela est possible.

AppMeasurement utilise `trackingServer` comme solution de secours si [`trackingServerSecure`](trackingserversecure.md) n’est pas défini. De nombreuses implémentations plus anciennes ne définissent pas de `trackingServerSecure`, en utilisant `trackingServer` comme solution de secours sur les pages sécurisées. Compte tenu de la prévalence du HTTPS, Adobe recommande d’utiliser `trackingServerSecure` si possible.
