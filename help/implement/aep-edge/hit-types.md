---
title: Types d’événements Edge Network dans Adobe Analytics
description: Comment Adobe Analytics interprète les événements reçus d’Edge Network.
feature: Implementation Basics
role: Admin, Developer
exl-id: 31085025-9c38-4375-8dfb-4fded6542ca7
source-git-commit: 6e500007e10086c0ff8108856a3563d7702f1130
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 25%

---

# Types d’événements Edge Network dans Adobe Analytics

Adobe Analytics traite les accès différemment selon les fonctions que vous appelez dans AppMeasurement. Par exemple, [`s.t`](/help/implement/vars/functions/t-method.md) et [`s.tl`](/help/implement/vars/functions/tl-method.md) incluent ou omettent certaines dimensions et incrémentent différemment les pages vues. Adobe Experience Platform contient uniquement la commande `sendEvent`. Des propriétés spécifiques au sein de la payload `xdm` déterminent la manière dont ces données sont interprétées dans Adobe Analytics.

Edge Network utilise la logique suivante pour déterminer les pages vues Adobe Analytics et les événements de lien :

| La payload XDM contient... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` ou `xdm.web.webPageDetails.URL` et pas `xdm.web.webInteraction.type` | considère que la payload est une **page vue** |
| `xdm.eventType = web.webPageDetails.pageViews` | considère que la payload est une **page vue** |
| `xdm.web.webInteraction.type` et (`xdm.web.webPageDetails.name` ou `xdm.web.webPageDetails.url`) | considère la payload comme un **événement de lien** <br/> définit également `xdm.web.webPageDetails.name` et `xdm.web.webPageDetails.URL` sur `null` |
| pas de `xdm.web.webInteraction.type`, pas de `xdm.webPageDetails.name` et pas de `xdm.web.webPageDetails.URL` | supprime la payload et ignore les données |

| La payload de l’objet de données contient... | Adobe Analytics... |
|---|---|
| `data.__adobe.analytics.pageName` ou `data.__adobe.analytics.pageURL` et pas `data.__adobe.analytics.linkType` | considère que la payload est une **page vue** |
| `data.__adobe.analytics.linkType` et (`data.__adobe.analytics.linkName` ou `data.__adobe.analytics.linkURL`) | considère la payload comme un **événement de lien** <br/> définit également `data.__adobe.analytics.pageName` et `data.__adobe.analytics.pageURL` sur `null` |
| pas de `data.__adobe.analytics.linkType`, pas de `data.__adobe.analytics.pageName` et pas de `data.__adobe.analytics.pageURL` | supprime la payload et ignore les données |

>[!NOTE]
>
>Si vous incluez un objet `xdm` et un objet `data` dans la même payload, Adobe Analytics recherche les champs respectifs des deux objets.

En plus de différencier les pages vues et les clics sur les liens, la logique suivante est en place pour déterminer si certains événements sont classés A4T ou sont ignorés.

| La payload XDM contient... | Adobe Analytics... |
|---|---|
| `xdm.eventType = display` ou <br/>`xdm.eventType = decisioning.propositionDisplay` ou <br/>`xdm.eventType = personalization.request` ou <br/>`xdm.eventType = decisioning.propositionFetch` et `xdm._experience.decisioning` | considère la payload comme un appel **A4T**. |
| `xdm.eventType = display` ou <br/>`xdm.eventType = decisioning.propositionDisplay` ou <br/>`xdm.eventType = personalization.request` ou <br/>`xdm.eventType = decisioning.propositionFetch` et aucune `xdm._experience.decisioning` | supprime la payload et ignore les données |
| `xdm.eventType = click` ou `xdm.eventType = decisioning.propositionInteract` et `xdm._experience.decisioning` et pas de `web.webInteraction.type` | considère la payload comme un appel **A4T**. |
| `xdm.eventType = click` ou `xdm.eventType = decisioning.propositionInteract` et pas de `xdm._experience.decisioning` et pas de `web.webInteraction.type` | supprime la payload et ignore les données. |

Pour plus d’informations, voir [Groupe de champs du schéma d’extension complète Adobe Analytics ExperienceEvent](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/field-groups/event/analytics-full-extension).
