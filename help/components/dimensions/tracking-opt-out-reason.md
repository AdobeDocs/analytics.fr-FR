---
title: Suivi du motif d’exclusion
description: Affiche un aperçu des données qui seraient exclues si vous aviez activé les paramètres de confidentialité.
feature: Dimensions
exl-id: f0521f4f-b11e-4ce3-b0fe-60788be6b120
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 7%

---

# Suivi du motif d’exclusion

*Cette page fait référence à la [dimension](overview.md) qui vous permet de voir l’impact potentiel des données provenant de l’activation de certains paramètres de la suite de rapports. Il n&#39;est pas lié au service Opt-in de l&#39;ID Adobe Experience Cloud [](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=fr).*

La dimension « Raison du désabonnement du suivi » sert d’aperçu des données qui seraient exclues si vous aviez activé les paramètres de confidentialité. Cette dimension est principalement utilisée pour déterminer si votre implémentation subirait un impact négatif si vous activiez [Paramètres de confidentialité](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html) sous Paramètres de la suite de rapports.

Les implémentations standard voient 1 % ou moins du trafic total de leurs suites de rapports sous cette dimension si les paramètres de confidentialité n’ont pas encore été activés. Des pourcentages supérieurs à 1 % de l’ensemble du trafic suggèrent un problème d’implémentation potentiel qui empêche AppMeasurement de définir des cookies propriétaires.

## Renseigner cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations qui n’ont pas encore activé [Paramètres de confidentialité](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html). Si votre organisation a déjà activé le paramètre **[!UICONTROL Supprimer les utilisateurs qui ont bloqué tous les cookies]** pour les navigateurs de bureau et mobiles, cette dimension ne contient pas de données.

## Éléments de dimension

Les éléments de dimension comprennent `"Cookies disabled by Desktop Browser"` et `"Cookies disabled by Mobile Browser"`.

* **Cookies désactivés par le navigateur de bureau** : le visiteur a bloqué les cookies à l’aide d’un navigateur de bureau et **[!UICONTROL Supprimer les utilisateurs qui ont bloqué tous les cookies sur les navigateurs de bureau]** est désactivé.
* **Cookies désactivés par le navigateur mobile** : le visiteur a bloqué les cookies à l’aide d’un navigateur mobile et **[!UICONTROL Supprimer les utilisateurs qui ont bloqué tous les cookies sur les navigateurs mobiles]** est désactivé.
