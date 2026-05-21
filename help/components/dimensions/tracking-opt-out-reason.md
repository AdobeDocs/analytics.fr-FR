---
title: Suivi du motif d’exclusion
description: Affiche un aperçu des données qui seraient exclues si vous aviez activé les paramètres de confidentialité.
feature: Dimensions
exl-id: f0521f4f-b11e-4ce3-b0fe-60788be6b120
TQID: https://experienceleague.adobe.com/mFYYrj4iBWBi87sErHnWTYXce3lUhV0pwUt63x3vfnY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 281
ht-degree: 11%

---

# Suivi du motif d’exclusion

*Cette page fait référence à la [dimension](overview.md) qui vous permet de voir l’impact potentiel des données provenant de l’activation de certains paramètres de la suite de rapports. Il n&#39;est pas lié au service Opt-in de l&#39;ID Adobe Experience Cloud [&#128279;](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=fr).*

La dimension « Raison du désabonnement du suivi » sert d’aperçu des données qui seraient exclues si vous aviez activé les paramètres de confidentialité. Cette dimension est principalement utilisée pour déterminer si votre implémentation subirait un impact négatif si vous activiez [Paramètres de confidentialité](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html?lang=fr) sous Paramètres de la suite de rapports.

Les implémentations standard voient 1 % ou moins du trafic total de leurs suites de rapports sous cette dimension si les paramètres de confidentialité n’ont pas encore été activés. Des pourcentages supérieurs à 1 % de l’ensemble du trafic suggèrent un problème d’implémentation potentiel qui empêche AppMeasurement de définir des cookies propriétaires.

## Renseigner cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations qui n’ont pas encore activé [Paramètres de confidentialité](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html?lang=fr). Si votre organisation a déjà activé le paramètre **[!UICONTROL Supprimer les utilisateurs qui ont bloqué tous les cookies]** pour les navigateurs de bureau et mobiles, cette dimension ne contient pas de données.

## Éléments de dimension

Les éléments de dimension comprennent `"Cookies disabled by Desktop Browser"` et `"Cookies disabled by Mobile Browser"`.

* **Cookies désactivés par le navigateur de bureau** : le visiteur a bloqué les cookies à l’aide d’un navigateur de bureau et **[!UICONTROL Supprimer les utilisateurs qui ont bloqué tous les cookies sur les navigateurs de bureau]** est désactivé.
* **Cookies désactivés par le navigateur mobile** : le visiteur a bloqué les cookies à l’aide d’un navigateur mobile et **[!UICONTROL Supprimer les utilisateurs qui ont bloqué tous les cookies sur les navigateurs mobiles]** est désactivé.
