---
title: Types d’événements Edge Network dans Adobe Analytics
description: Comment Adobe Analytics interprète les événements reçus d’Edge Network.
feature: Implementation Basics
role: Admin, Developer
exl-id: 31085025-9c38-4375-8dfb-4fded6542ca7
source-git-commit: 0096a53505b3b1bc925c813c2c6c11ee3c7ee0c0
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 20%

---

# Types d’événements Edge Network dans Adobe Analytics

Adobe Analytics traite les accès différemment selon les fonctions que vous appelez dans AppMeasurement. Par exemple, les [`s.t`](/help/implement/vars/functions/t-method.md) et les [`s.tl`](/help/implement/vars/functions/tl-method.md) incluent ou omettent certaines dimensions et incrémentent [pages vues](/help/components/metrics/page-views.md) différemment. Adobe Experience Platform contient uniquement la commande [`sendEvent`](https://experienceleague.adobe.com/fr/docs/experience-platform/collection/js/commands/sendevent/overview). Des propriétés spécifiques au sein de la payload [`xdm`](https://experienceleague.adobe.com/fr/docs/experience-platform/collection/js/commands/sendevent/xdm) ou [`data`](https://experienceleague.adobe.com/fr/docs/experience-platform/collection/js/commands/sendevent/data) déterminent la manière dont ces données sont interprétées dans Adobe Analytics.

Edge Network utilise la logique suivante pour déterminer Adobe Analytics [pages vues](/help/components/metrics/page-views.md) et [événements de lien](/help/components/metrics/page-events.md) :

## Pages vues et événements de lien utilisant l’objet `xdm`

| La payload XDM contient... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` ou `xdm.web.webPageDetails.URL` et pas `xdm.web.webInteraction.type` | considère que la payload est une **page vue** |
| `xdm.eventType = web.webpagedetails.pageViews` | considère que la payload est une **page vue** |
| `xdm.web.webInteraction.type` et (`xdm.web.webPageDetails.name` ou `xdm.web.webPageDetails.URL`) | considère la payload comme un **événement de lien** <br/> définit également `xdm.web.webPageDetails.name` et `xdm.web.webPageDetails.URL` sur `null` |
| `xdm.web.webInteraction.type` et (`xdm.web.webInteraction.name` ou `xdm.web.webInteraction.URL`) | considère la payload comme un **événement de lien** <br/>définit également `xdm.web.webPageDetails.name` et `xdm.web.webPageDetails.URL` sur `null` si présent |
| pas de `xdm.web.webInteraction.type`, pas de `xdm.web.webPageDetails.name` et pas de `xdm.web.webPageDetails.URL` | supprime la payload et ignore les données |

>[!TIP]
>
>Les noms des champs XDM dans la payload sont sensibles à la casse (par exemple, `webPageDetails.URL`). Le champ `xdm.eventType` est une valeur de chaîne avec son propre ensemble de valeurs acceptées et la casse dans ces valeurs peut ne pas correspondre aux noms de champ XDM. Pour les valeurs acceptées, consultez le champ `eventType` dans la classe [XDM ExperienceEvent](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/classes/experienceevent#eventType).

+++Page minimale vue à l’aide de champs `xdm`

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

+++Page minimale vue à l’aide de `xdm.eventType`

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

| La payload de l’objet de données contient... | Adobe Analytics... |
|---|---|
| `data.__adobe.analytics.pageName` ou `data.__adobe.analytics.pageURL` et pas `data.__adobe.analytics.linkType` | considère que la payload est une **page vue** |
| `data.__adobe.analytics.linkType` et (`data.__adobe.analytics.linkName` ou `data.__adobe.analytics.linkURL`) | considère la payload comme un **événement de lien** <br/> définit également `data.__adobe.analytics.pageName` et `data.__adobe.analytics.pageURL` sur `null` |
| pas de `data.__adobe.analytics.linkType`, pas de `data.__adobe.analytics.pageName` et pas de `data.__adobe.analytics.pageURL` | supprime la payload et ignore les données |

+++Page minimale vue à l’aide de champs `data`

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

+++Événement de lien minimal à l’aide de champs `data`

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
>Si vous incluez un objet `xdm` et un objet `data` dans la même payload, Adobe Analytics recherche les champs respectifs des deux objets.

## A4T et événements liés à la prise de décision

En plus de différencier les pages vues et les événements de lien, la logique suivante détermine si certains événements de prise de décision sont classés comme A4T ou sont ignorés.

| La payload XDM contient... | Adobe Analytics... |
|---|---|
| `xdm.eventType = decisioning.propositionDisplay` et `xdm._experience.decisioning` | considère la payload comme un appel **A4T**. |
| `xdm.eventType = decisioning.propositionDisplay` et pas de `xdm._experience.decisioning` | supprime la payload et ignore les données |
| `xdm.eventType = decisioning.propositionInteract` et `xdm._experience.decisioning` et pas de `xdm.web.webInteraction.type` | considère la payload comme un appel **A4T**. |
| `xdm.eventType = decisioning.propositionInteract` et pas de `xdm._experience.decisioning` et pas de `xdm.web.webInteraction.type` | supprime la payload et ignore les données. |
| `xdm.eventType = decisioning.propositionFetch` | supprime la payload et ignore les données |

>[!TIP]
>
>Les valeurs de `eventType` suivantes sont obsolètes. Notez que ces valeurs affectent la logique de la même manière que leurs homologues actuelles :
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
