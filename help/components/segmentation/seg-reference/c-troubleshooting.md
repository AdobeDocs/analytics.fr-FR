---
description: Comprendre comment résoudre les problèmes liés aux segments.
title: Résolution des problèmes
feature: Segmentation
exl-id: ca51110e-1ba7-4182-b5b2-baf9b0c017af
TQID: https://experienceleague.adobe.com/-9XPy2cFezGBFnygKW4gbHG2zuNBfn5Z29InEDF58ZM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 181
ht-degree: 42%

---

# Résolution des problèmes

Cet article répertorie certains problèmes courants liés aux segments et explique comment les résoudre.

<!--
Looks like this is not part anymore of the current UI.

## Error: "Incompatible elements in this segment" {#incompatible}

This error occurs when you try to save a segment in the Data Warehouse folder where the segment contains elements not compatible with Data Warehouse. To resolve this error, do one of two things:

* Save the segment in a different folder 
* Remove or change the incompatible portions of the segment.
-->

## Pourquoi mon segment ne renvoie-t-il aucune donnée ? {#no-data}

Raisons possibles :

* Imbrication inverse : par exemple, imbrication d’un conteneur ![Utilisateur](/help/assets/icons/User.svg) **[!UICONTROL Visiteur]** sous un conteneur ![Visite](/help/assets/icons/Visit.svg) **[!UICONTROL Visite]**.
* Le rapport ne prend pas en charge la segmentation.
* Aucune donnée ne correspond aux critères de segmentation.

## Pourquoi ne puis-je pas voir le segment que j’ai créé dans le Gestionnaire de segments ? {#invisible}

Raisons possibles :

* Certaines dimensions sont disponibles uniquement dans Data Warehouse et non dans le gestionnaire de segments.
* Le segment n’est vérifié que pour une suite de rapports spécifique.
* Il est possible qu’un segment partagé ait été supprimé par un autre utilisateur.
* Les segments n’ont pas pu être chargés en raison d’un problème de cache du centre de données ou du navigateur.
* Le segment n’a pas été enregistré.
* L’adresse IP est peut-être bloquée du côté de l’utilisateur.

## Pourquoi les données affichées après avoir appliqué un segment semblent-elles incorrectes ? {#page-data}

Raisons possibles :

* Les règles ou les opérateurs sont incorrects pour le résultat requis.
* Utilisation incorrecte des conteneurs dans le segment.
* Les variables de trafic utilisées pour la segmentation ne sont pas configurées correctement ou ont expiré.
