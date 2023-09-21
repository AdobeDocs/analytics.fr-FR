---
title: Système d’exploitation
description: Système d’exploitation du visiteur.
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 22%

---

# Système d’exploitation

Le &quot;Système d&#39;exploitation&quot; [dimension](overview.md) affiche le système d’exploitation et la version utilisés par le visiteur. Si votre propriété Web comporte des fonctionnalités spécifiques au système d’exploitation, cette dimension vous permet d’identifier les systèmes d’exploitation les plus courants.

## Renseignement de cette dimension avec des données

Cette dimension fait référence à une table de recherche interne à Adobe. La valeur de recherche est basée sur l’en-tête HTTP `User-Agent` dans les demandes d’image. Si vous utilisez une bibliothèque AppMeasurement (par le biais des balises dans Adobe Experience Platform, par exemple), cette dimension est prête à l’emploi.

## Éléments de dimension

Les éléments de dimension incluent les systèmes d’exploitation utilisés par les visiteurs. Par exemple, `"Windows 10"`, `"OS X 10.15"` et `"Android 9"`.

## Modifications de l’étiquetage et de la définition

Vous trouverez ci-dessous une liste des problèmes spécifiques liés à la représentation du système d’exploitation dans l’agent utilisateur et dans les rapports Adobe Analytics.

### Modification de la granularité du système d’exploitation

Le 2 mars 2023, nous avons mis à jour nos rapports afin d’inclure plus de détails dans le système d’exploitation. Après cette date, nous incluons la version du correctif du système d’exploitation. Ainsi, par exemple, un utilisateur avec OS X 10.15.7 apparaîtrait sous la forme &quot;OS X 10.15&quot; avant le 2 mars. Après le 2 mars, elles apparaîtront sous la forme &quot;OS X 10.15.7&quot;.

### Modification de la convention d’affectation des noms pour le système d’exploitation Apple :

À partir de la version 11, nous utiliserons MacOS plutôt que OS X pour faire référence au système d’exploitation Apple.

Exemples :

* &quot;OS X 10.15&quot; (voir la note ci-dessous sur la version 10.15.7 sur la représentation dans les chaînes UA).
* &quot;MacOS 11.0.0

### La version de Mac OS est incorrecte dans l’agent utilisateur après la version 10.15.7 

L’agent utilisateur sur les ordinateurs Apple affiche la version du système d’exploitation comme 10.15.7, même pour les versions plus récentes. Cela a été fait parce que l&#39;inclusion de la version 11 dans l&#39;UA a apparemment causé des problèmes avec certains sites web. C’est vrai pour *tous les navigateurs* et n’est pas lié Google le &quot;blocage&quot; de l’agent utilisateur sur les navigateurs Chromium.

Notez que les conseils du client incluent la version correcte dans l’indice de version de la plateforme (&quot;Sec-CH-UA-Platform-Version&quot;). Il s’agit d’un indice à forte entropie qui n’est donc pas collecté automatiquement par Adobe. Voir [FAQ sur les astuces Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) pour plus d’informations sur la collecte d’indices à forte entropie.

### La version de Windows est incorrecte dans l’agent utilisateur à partir de Windows 11.

Depuis janvier 2023, l’agent utilisateur de tous les navigateurs affiche Windows 11 comme Windows 10.

Notez que les conseils du client incluent la version correcte dans l’indice de version de la plateforme (&quot;Sec-CH-UA-Platform-Version&quot;). Il s’agit d’un indice à forte entropie qui n’est donc pas collecté automatiquement par Adobe. Voir [FAQ sur les astuces Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) pour plus d’informations sur la collecte d’indices à forte entropie.
