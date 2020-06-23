---
title: dc
description: Variable abandonnée qui vous permet de déterminer le centre de données à utiliser.
translation-type: ht
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# dc

>[!IMPORTANT] Cette variable a été abandonnée. Utilisez [`trackingServer`](trackingserver.md) à la place.

Dans les versions précédentes d’Adobe Analytics, Adobe vous demandait de spécifier le centre de données auquel vous souhaitiez envoyer des données. L’envoi d’accès vers un centre de données incorrect a entraîné une perte de données.

Adobe a amélioré cette expérience en permettant à toute mise en œuvre d’envoyer des accès à `sc.omtrdc.net`. Il n’est plus nécessaire de spécifier le centre de données.
