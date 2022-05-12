---
title: Suivi du motif d’exclusion
description: prévisualise les données qui seraient exclues si vous avez activé les paramètres de confidentialité.
feature: Dimensions
exl-id: f0521f4f-b11e-4ce3-b0fe-60788be6b120
source-git-commit: 4c896fe930b52e440f8b91725fa6451faaa76fc8
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 7%

---

# Suivi du motif d’exclusion

La dimension &quot;Raison de l’exclusion du suivi&quot; agit comme un aperçu des données qui seraient exclues si vous avez activé les paramètres de confidentialité. Cette dimension est principalement utilisée pour déterminer si votre implémentation serait affectée négativement si vous avez activé [Paramètres de confidentialité](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html) sous Paramètres de la suite de rapports.

Les mises en oeuvre standard voient 1 % ou moins du trafic global de leur suite de rapports sous cette dimension si les paramètres de confidentialité n’ont pas encore été activés. Les pourcentages supérieurs à 1 % de tout le trafic suggèrent un problème de mise en oeuvre potentiel qui empêche AppMeasurement de définir des cookies propriétaires.

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations qui n’ont pas encore été activées. [Paramètres de confidentialité](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html). Si votre entreprise a déjà activé la variable **[!UICONTROL Supprimer les utilisateurs qui ont bloqué tous les cookies]** pour les navigateurs de bureau et mobiles, cette dimension ne contient aucune donnée.

## Éléments de dimension

Les éléments de dimension comprennent `"Cookies disabled by Desktop Browser"` et `"Cookies disabled by Mobile Browser"`.

* **Cookies désactivés par le navigateur de bureau**: le visiteur a bloqué les cookies à l’aide d’un navigateur de bureau ; et **[!UICONTROL Suppression des utilisateurs qui ont bloqué tous les cookies dans les navigateurs de bureau]** est désactivée.
* **Cookies désactivés par le navigateur mobile**: le visiteur a bloqué les cookies à l’aide d’un navigateur mobile ; et **[!UICONTROL Suppression des utilisateurs qui ont bloqué tous les cookies dans les navigateurs mobiles]** est désactivée.
