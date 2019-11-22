---
description: Les variables de page renseignent directement un rapport (pageName, props de liste, variables de liste, etc.).
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variables de page
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---


# trackingServer

La variable est utilisée dans le cadre de l’implémentation des cookies propriétaires, afin d’indiquer le domaine au niveau duquel sont écrits le cookie et la demande d’image.


<!-- 

trackingServer.xml

 -->

Elle est utilisée pour les pages non sécurisées. If *`trackingServer`* is defined, nothing goes to 2o7.net. Si la variable *`trackingServer`* n’est pas définie (et si dc n’est pas défini), les données sont envoyées à 112.2o7.net.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | "" |

Vous trouverez une liste des centres de données Adobe [ici](https://helpx.adobe.com/analytics/kb/determining-data-center.html).