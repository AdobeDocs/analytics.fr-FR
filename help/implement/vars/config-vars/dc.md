---
title: dc
description: Variable retirée qui vous permet de déterminer le centre de données à utiliser.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# dc

> [!IMPORTANT] Cette variable est retirée. Utilisez [`trackingServer`](trackingserver.md) plutôt.

Dans les versions précédentes d’Adobe Analytics, Adobe vous demandait de spécifier le centre de données auquel vous souhaitez envoyer des données. L’envoi d’accès vers un centre de données incorrect a entraîné une perte de données.

Adobe a amélioré cette expérience en permettant à toute implémentation d’envoyer des accès à `sc.omtrdc.net`. Il n’est plus nécessaire de spécifier le centre de données.
