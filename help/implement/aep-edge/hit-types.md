---
title: Types d’événements Edge Network dans Adobe Analytics
description: Comment Adobe Analytics interprète les événements reçus d’Edge Network.
feature: Implementation Basics
role: Admin, Developer
source-git-commit: 8d369bd3be3ae9c075e490e108666728a2cff5dc
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 28%

---

# Types d’événements Edge Network dans Adobe Analytics

Adobe Analytics traite les accès différemment selon les fonctions que vous appelez dans AppMeasurement. Par exemple, [`s.t`](/help/implement/vars/functions/t-method.md) et [`s.tl`](/help/implement/vars/functions/tl-method.md) incluent ou omettent certaines dimensions et incrémentent différemment les pages vues. Adobe Experience Platform contient uniquement la commande `sendEvent`. Des propriétés spécifiques au sein de la payload `xdm` déterminent la manière dont ces données sont interprétées dans Adobe Analytics.

Edge Network utilise la logique suivante pour déterminer les pages vues Adobe Analytics et les événements de lien :

| La payload XDM contient... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` ou `xdm.web.webPageDetails.URL` et pas `xdm.web.webInteraction.type` | considère que la payload est une **page vue** |
| `xdm.eventType = web.webPageDetails.pageViews` | considère que la payload est une **page vue** |
| `xdm.web.webInteraction.type` et (`xdm.web.webInteraction.name` ou `xdm.web.webInteraction.url`) | considère que la payload est un **événement de lien** |
| `xdm.web.webInteraction.type` et (`xdm.web.webPageDetails.name` ou `xdm.web.webPageDetails.url`) | considère la payload comme un **événement de lien** <br/> définit également `xdm.web.webPageDetails.name` et `xdm.web.webPageDetails.URL` sur `null` |
| pas `xdm.web.webInteraction.type` et (pas `xdm.webPageDetails.name` et pas `xdm.web.webPageDetails.URL`) | supprime la payload et ignore les données |

En plus de différencier les pages vues et les clics sur les liens, la logique suivante est en place pour déterminer si certains événements sont classés A4T ou sont ignorés.

| La payload XDM contient... | Adobe Analytics... |
| --- | --- |
| `xdm.eventType = display` ou <br/>`xdm.eventType = decisioning.propositionDisplay` ou <br/>`xdm.eventType = personalization.request` ou <br/>`xdm.eventType = decisioning.propositionFetch` et `xdm._experience.decisioning` | considère la payload comme un appel **A4T**. |
| `xdm.eventType = display` ou <br/>`xdm.eventType = decisioning.propositionDisplay` ou <br/>`xdm.eventType = personalization.request` ou <br/>`xdm.eventType = decisioning.propositionFetch` et aucune `xdm._experience.decisioning` | supprime la payload et ignore les données |
| `xdm.eventType = click` ou `xdm.eventType = decisioning.propositionInteract` et `xdm._experience.decisioning` et pas de `web.webInteraction.type` | considère la payload comme un appel **A4T**. |
| `xdm.eventType = click` ou `xdm.eventType = decisioning.propositionInteract` et pas de `xdm._experience.decisioning` et pas de `web.webInteraction.type` | supprime la payload et ignore les données. |

Pour plus d’informations, voir [Groupe de champs du schéma d’extension complète Adobe Analytics ExperienceEvent](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/field-groups/event/analytics-full-extension).
