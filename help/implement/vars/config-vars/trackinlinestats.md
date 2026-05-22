---
title: trackInlineStats
description: (Retiré) Activez ou désactivez ClickMap dans votre mise en œuvre.
keywords: désactiver clickmap
feature: Appmeasurement Implementation
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/UoeOR4qNKfuectzZJVKJ2gCNhSxMSBOggMEj9Z9v08g'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 194
ht-degree: 29%

---

# trackInlineStats

>[!IMPORTANT]
>
>Cette variable a été retirée et n’est plus utilisée.

ClickMap est une fonctionnalité retirée d’Adobe Analytics qui collecte des données sur l’emplacement où cliquent les visiteurs et ce sur quoi ils cliquent. La fonctionnalité a été remplacée par [&#128279;](/help/analyze/activity-map/overview.md).

Lorsqu’il est activé, AppMeasurement collecte des informations sur le lien et envoie ces données dans la demande d’image suivante. Les informations de chaque clic sont stockées dans un cookie intitulé `s_sq`.

## Activation de ClickMap à l’aide de l’extension Adobe Analytics

[!UICONTROL Activer ClickMap] est une case à cocher située sous l’accordéon [!UICONTROL Suivi des liens] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Suivi des liens] qui affiche la case à cocher [!UICONTROL Activer ClickMap].

>[!NOTE]
>
>Cette case à cocher est différente de la case [!UICONTROL Utiliser Activity Map], qui se trouve sous l’accordéon [!UICONTROL Gestion des bibliothèques].

## s.trackInlineStats dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La `s.trackInlineStats` est une valeur booléenne qui active ou désactive le suivi ClickMap. Cette fonction ayant été abandonnée, Adobe ne recommande pas de définir cette variable. Sa valeur par défaut est `false`.

```js
s.trackInlineStats = false;
```
