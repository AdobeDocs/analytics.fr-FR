---
title: trackingServer
description: Domaine utilisé pour envoyer des données à Adobe via HTTP.
feature: Appmeasurement Implementation
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
role: Admin, Developer
source-git-commit: 35675c2e65456a175d1516dd421b80d2af809286
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 13%

---

# trackingServer

>[!IMPORTANT]
>
>Cette variable est obsolète. Avec la prévalence du HTTPS, utilisez plutôt [`trackingServerSecure`](trackingserversecure.md).

La variable `trackingServer` détermine le domaine utilisé par AppMeasurement pour envoyer des données à Adobe via HTTP. Si cette variable n’est pas correctement définie, votre mise en œuvre peut entraîner une perte de données.

Avant le service d’identités [Adobe Experience Cloud](https://experienceleague.adobe.com/fr/docs/id-service/using/home), cette variable déterminait également où les cookies tiers étaient définis. Adobe recommande vivement d’utiliser le service d’ID dans toutes les implémentations lorsque cela est possible.

AppMeasurement utilise `trackingServer` comme solution de secours si [`trackingServerSecure`](trackingserversecure.md) n’est pas défini. De nombreuses implémentations plus anciennes ne définissent pas de `trackingServerSecure`, en utilisant `trackingServer` comme solution de secours sur les pages sécurisées. Compte tenu de la prévalence du HTTPS, Adobe recommande d’utiliser `trackingServerSecure` si possible.
