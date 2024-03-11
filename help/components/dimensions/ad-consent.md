---
title: Consentement de la publicité
description: Voir la configuration du consentement publicitaire pour les fournisseurs tiers.
feature: Dimensions
source-git-commit: 31f61c64fef707e2d2499b853a9b54caf847634b
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 1%

---

# Consentement de la publicité

Le &quot;consentement publicitaire&quot; [dimension](overview.md) indique si le consentement est collecté pour envoyer des données à des fournisseurs de publicité tiers, tels que Google, Meta, etc.

Actuellement, cette dimension est utilisée uniquement pour Google. En vertu de la réglementation européenne sur la protection des données, la loi sur les marchés numériques (DMA), Google exige que les données envoyées à ses serveurs et collectées en Europe indiquent si le consentement est collecté. Certains clients Analytics envoient des données d’événement par Adobe Advertising en tant qu’événements de conversion vers Google.

À l’avenir, cette dimension peut être utilisée pour prendre en charge le codage d’informations de consentement supplémentaires pour d’autres fournisseurs de publicité tiers.


## Renseigner cette dimension avec des données

Cette dimension collecte les données des éléments suivants [Variables de données contextuelles](/help/implement/vars/page-vars/contextdata.md)

* `contextData.['adConsent']`

Vous renseignez la variable de données contextuelles avec les valeurs appropriées pour les champs de consentement Google.

* `ad_user_data` (1er caractère) et
* `ad_personalization` (2e caractère).

Voir [Consentement dans la référence de l’API Google Ads](https://developers.google.com/google-ads/api/reference/rpc/v15/Consent) pour plus d’informations.

Les valeurs possibles pour chacun de ces champs peuvent être les suivantes :

| Valeur | ad_user_data | ad_personalization |
|:-:|---|---|
| `Y` | Octroi du consentement à Google pour les données utilisateur des publicités. | Accorder le consentement à Google pour la personnalisation des publicités. |
| `N` | Refuser le consentement à Google pour les données utilisateur de l’annonce. | Consentement à jour de Google pour la personnalisation des publicités. |
| `U` | Non spécifié. | Non spécifié. |

L’exemple ci-dessous accorde le consentement à Google pour les données utilisateur publicitaires, mais pas pour la personnalisation publicitaire :

```
contextData.['adConsent'] = "YN..."
```

Les caractères situés au-delà du premier et du deuxième caractère sont actuellement ignorés.

## Utiliser les données

Vous pouvez utiliser les données de consentement de publicité collectées :

* Flux de données : les données de consentement pour la publicité sont disponibles à l’aide de la variable `dataprivacydmaconsent` [column](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md).
* Rapports de l’entrepôt de données : les données de consentement pour la publicité sont disponibles à l’aide de la variable **[!UICONTROL Consentement de la plateforme publicitaire]** dimension.


Votre entreprise détermine la logique de mise en oeuvre de cette variable de données contextuelles. La valeur ne persiste pas au-delà de l’accès sur lequel elle est définie. Vous devez donc définir la variable de données contextuelles sur chaque page.

Lorsque vous envoyez des données publicitaires d’Adobe Analytics via Adobe Advertising en tant qu’événements de conversion vers Google, consultez l’équipe d’Adobe Advertising pour faciliter l’intégration.
