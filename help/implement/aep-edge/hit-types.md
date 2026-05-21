---
title: Types d’événements Edge Network dans Adobe Analytics
description: Comment Adobe Analytics interprète les événements reçus d’Edge Network.
feature: Implementation Basics
role: Admin, Developer
exl-id: 31085025-9c38-4375-8dfb-4fded6542ca7
TQID: https://experienceleague.adobe.com/Bf-OnlQu7TFYb1V4uKCVVoQkaPP4MuhyVWSdgjlZ6e8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 478
ht-degree: 100%

---

# Types d’événements Edge Network dans Adobe Analytics

Adobe Analytics traite les accès différemment selon les fonctions que vous appelez dans AppMeasurement. Par exemple, les [`s.t`](/help/implement/vars/functions/t-method.md) et les [`s.tl`](/help/implement/vars/functions/tl-method.md) incluent ou omettent certaines dimensions et incrémentent les [pages vues](/help/components/metrics/page-views.md) différemment. Adobe Experience Platform contient uniquement la commande [`sendEvent`](https://experienceleague.adobe.com/fr/docs/experience-platform/collection/js/commands/sendevent/overview). Des propriétés spécifiques au sein de la payload [`xdm`](https://experienceleague.adobe.com/fr/docs/experience-platform/collection/js/commands/sendevent/xdm) ou [`data`](https://experienceleague.adobe.com/fr/docs/experience-platform/collection/js/commands/sendevent/data) déterminent la manière dont ces données sont interprétées dans Adobe Analytics.

Le réseau Edge Network utilise la logique suivante pour déterminer les [pages vues](/help/components/metrics/page-views.md) Adobe Analytics et les [événements de lien](/help/components/metrics/page-events.md).

## Pages vues et événements de lien utilisant l’objet `xdm`

| La payload XDM contient... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` ou `xdm.web.webPageDetails.URL` et pas `xdm.web.webInteraction.type` | considère que la payload est une **page vue** |
| `xdm.eventType = web.webpagedetails.pageViews` | considère que la payload est une **page vue** |
| `xdm.web.webInteraction.type` et (`xdm.web.webPageDetails.name` ou `xdm.web.webPageDetails.URL`) | considère que la payload est un **événement de lien** <br/>définit également `xdm.web.webPageDetails.name` et `xdm.web.webPageDetails.URL` sur `null` |
| `xdm.web.webInteraction.type` et (`xdm.web.webInteraction.name` ou `xdm.web.webInteraction.URL`) | considère que la payload est un **événement de lien** <br/>définit également `xdm.web.webPageDetails.name` et `xdm.web.webPageDetails.URL` sur `null` si présent |
| pas `xdm.web.webInteraction.type` et pas `xdm.web.webPageDetails.name` et pas `xdm.web.webPageDetails.URL` | supprime la payload et ignore les données |

>[!TIP]
>
>Les noms des champs XDM dans la payload sont sensibles à la casse (par exemple, `webPageDetails.URL`). Le champ `xdm.eventType` est une valeur de chaîne avec son propre ensemble de valeurs acceptées et la casse dans ces valeurs peut ne pas correspondre aux noms de champ XDM. Pour les valeurs acceptées, consultez le champ `eventType` dans la classe [XDM ExperienceEvent](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/classes/experienceevent#eventType).

+++Page vue minimale utilisant des champs `xdm`

```json
{
  "xdm": {
    "web": {
      "webPageDetails": {
        "name": "Example page",
        "URL": "https://example.com/page"
      }
    }
  }
}
```

+++

+++Page vue minimale utilisant `xdm.eventType`

```json
{
  "xdm": {
    "eventType": "web.webpagedetails.pageViews"
  }
}
```

+++

+++Événement de lien minimal utilisant les champs recommandés

```json
{
  "xdm": {
    "web": {
      "webInteraction": {
        "type": "other",
        "name": "Header nav: Pricing",
        "URL": "https://example.com/pricing"
      }
    }
  }
}
```

+++

## Pages vues et événements de lien utilisant l’objet `data`

| La payload de l’objet de données contient… | Adobe Analytics... |
|---|---|
| `data.__adobe.analytics.pageName` ou `data.__adobe.analytics.pageURL` et pas `data.__adobe.analytics.linkType` | considère que la payload est une **page vue** |
| `data.__adobe.analytics.linkType` et (`data.__adobe.analytics.linkName` ou `data.__adobe.analytics.linkURL`) | considère que la payload est un **événement de lien** <br/>définit également `data.__adobe.analytics.pageName` et `data.__adobe.analytics.pageURL` sur `null` |
| pas `data.__adobe.analytics.linkType` et pas `data.__adobe.analytics.pageName` et pas `data.__adobe.analytics.pageURL` | supprime la payload et ignore les données |

+++Page vue minimale utilisant des champs `data`

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "pageName": "Example page",
        "pageURL": "https://example.com/page"
      }
    }
  }
}
```

+++

+++Événement de lien minimal utilisant des champs `data`

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "linkType": "o",
        "linkName": "Header nav: Pricing",
        "linkURL": "https://example.com/pricing"
      }
    }
  }
}
```

+++

>[!NOTE]
>
>Si vous incluez un objet `xdm` et un objet `data` dans la même payload, Adobe Analytics recherche les champs respectifs des deux objets.

## A4T et événements liés à la prise de décision

En plus de différencier les pages vues et les événements de lien, la logique suivante détermine si certains événements de prise de décision sont classés comme A4T ou sont ignorés.

| La payload XDM contient... | Adobe Analytics... |
|---|---|
| `xdm.eventType = decisioning.propositionDisplay` et `xdm._experience.decisioning` | considère que la payload est un appel **A4T**. |
| `xdm.eventType = decisioning.propositionDisplay` et pas `xdm._experience.decisioning` | supprime la payload et ignore les données |
| `xdm.eventType = decisioning.propositionInteract` et `xdm._experience.decisioning` et pas `xdm.web.webInteraction.type` | considère que la payload est un appel **A4T**. |
| `xdm.eventType = decisioning.propositionInteract` et pas `xdm._experience.decisioning` et pas `xdm.web.webInteraction.type` | supprime la payload et ignore les données. |
| `xdm.eventType = decisioning.propositionFetch` | supprime la payload et ignore les données |

>[!TIP]
>
>Les valeurs `eventType` suivantes sont obsolètes. Notez que ces valeurs affectent la logique de la même manière que leurs homologues actuelles :
>
>* Le type d’événement `display` est obsolète. Utilisez `decisioning.propositionDisplay` à la place.
>* Le type d’événement `click` est obsolète. Utilisez `decisioning.propositionInteract` à la place.
>* Le type d’événement `personalization.request` est obsolète. Utilisez `decisioning.propositionFetch` à la place.

+++Affichage A4T minimal

```json
{
  "xdm": {
    "eventType": "decisioning.propositionDisplay",
    "_experience": {
      "decisioning": {
        "propositions": [
          {
            "id": "example-proposition-id",
            "scope": "example-scope",
            "scopeDetails": { "decisionProvider": "AJO" }
          }
        ],
        "propositionEventType": { "display": 1 }
      }
    }
  }
}
```

+++

+++Interaction A4T minimale

```json
{
  "xdm": {
    "eventType": "decisioning.propositionInteract",
    "_experience": {
      "decisioning": {
        "propositions": [
          {
            "id": "example-proposition-id",
            "scope": "example-scope",
            "scopeDetails": { "decisionProvider": "AJO" }
          }
        ],
        "propositionEventType": { "interact": 1 }
      }
    }
  }
}
```

+++

Pour plus d’informations, voir [Groupe de champs du schéma d’extension complète Adobe Analytics ExperienceEvent](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/field-groups/event/analytics-full-extension).
