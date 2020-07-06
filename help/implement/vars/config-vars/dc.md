---
title: dc
description: Variable abandonnée qui vous permet de déterminer le centre de données à utiliser.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 100%

---


# dc

>[!IMPORTANT]
>
>Cette variable a été abandonnée. Utilisez [`trackingServer`](trackingserver.md) à la place.

Dans les versions précédentes d’Adobe Analytics, Adobe vous demandait de spécifier le centre de données auquel vous souhaitiez envoyer des données. L’envoi d’accès vers un centre de données incorrect a entraîné une perte de données.

Adobe a amélioré cette expérience en permettant à toute mise en œuvre d’envoyer des accès à `sc.omtrdc.net`. Il n’est plus nécessaire de spécifier le centre de données.
