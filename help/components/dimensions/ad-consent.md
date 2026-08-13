---
title: Consentement pour la plateforme publicitaire
description: Consultez la configuration du consentement des publicités pour les fournisseurs de publicité tiers.
feature: Dimensions
exl-id: bf63112d-7d20-4e35-9a59-5be21135ae51
TQID: https://experienceleague.adobe.com/Ou6-B5pFx-ku9H2iEqLN0Ly6-t01CzQUODo0poMk8Bs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 342
ht-degree: 3%

---

# Consentement pour la plateforme publicitaire

La [dimension](overview.md) « Consentement de la plateforme publicitaire » indique si le consentement est collecté pour envoyer des données à des fournisseurs publicitaires tiers, tels que Google, Meta, etc.

Actuellement, cette dimension est utilisée uniquement pour Google. En raison des réglementations européennes en matière de confidentialité, la loi sur les marchés numériques (DMA), Google exige que les données envoyées à ses serveurs et collectées en Europe indiquent si le consentement est collecté. Certains clients Analytics envoient des données d’événement via Adobe Advertising en tant qu’événements de conversion vers Google.

À l’avenir, cette dimension pourra être utilisée pour prendre en charge l’encodage d’informations de consentement supplémentaires pour d’autres fournisseurs de publicité tiers.

## Renseigner cette dimension avec des données

Cette dimension collecte les données des [variables de données contextuelles](/help/implement/vars/page-vars/contextdata.md) suivantes

* `contextData.['adConsent']`

Vous renseignez la variable de données contextuelles avec les valeurs appropriées pour les champs de consentement Google

* `ad_user_data` (1er caractère) et
* `ad_personalization` (2e caractère).

Voir [&#x200B; Consentement dans la référence de l’API Google Ads](https://developers.google.com/google-ads/api/reference/rpc/v15/Consent) pour plus d’informations.

Les valeurs possibles pour chacun de ces champs peuvent être :

| Valeur | ad_user_data | ad_personalization |
|:-:|---|---|
| `Y` | Accordez le consentement à Google pour les données utilisateur de la publicité. | Accordez le consentement à Google pour la personnalisation des annonces publicitaires. |
| `N` | Refuser le consentement à Google pour les données utilisateur de la publicité. | Ne donnez pas votre consentement à Google pour la personnalisation des annonces publicitaires. |
| `U` | Non spécifié. | Non spécifié. |

L’exemple ci-dessous accorde le consentement à Google pour les données d’utilisateur de la publicité, mais pas pour la personnalisation de la publicité :

```
contextData.['adConsent'] = "YN..."
```

Les caractères au-delà du premier et du deuxième caractère sont actuellement ignorés.

## Utiliser les données

Vous pouvez utiliser les données de consentement et collectées :

* Flux de données : les données de consentement des publicités sont disponibles dans la `dataprivacydmaconsent` [colonne](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md).
* Rapports Data Warehouse : les données de consentement des annonces sont disponibles à l’aide de la dimension **[!UICONTROL Consentement de la plateforme publicitaire]**.

Votre entreprise détermine la logique d’implémentation de cette variable de données contextuelles. La valeur ne persiste pas au-delà de l’accès sur lequel elle est définie. Vous devez donc définir la variable de données contextuelles sur chaque page.

Lorsque vous envoyez des données publicitaires d’Adobe Analytics via Adobe Advertising en tant qu’événements de conversion vers Google, consultez l’équipe d’Adobe Advertising pour faciliter l’intégration.

Pour plus d’informations, consultez [Compte rendu des performances sur la confidentialité](/help/admin/tools/manage-rs/edit-settings/privacy-reporting.md).
