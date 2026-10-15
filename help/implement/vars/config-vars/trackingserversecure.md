---
title: trackingServerSecure
description: Domaine utilisé pour envoyer des données à Adobe via HTTPS.
feature: Appmeasurement Implementation
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
role: Admin, Developer
TQID: https://experienceleague.adobe.com/8-M-5apvXuUfQyxdd4Es8Lr5LkgXPK2UNHrhpTzT8xE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 832a3752ab758d573e5b15b2dc38dad120fe8300
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 11%
---
# trackingServerSecure

La variable `trackingServerSecure` détermine le domaine utilisé par AppMeasurement pour envoyer des données à Adobe via HTTPS. Si cette variable n’est pas correctement définie, votre mise en œuvre peut entraîner une perte de données.

>[!NOTE]
>
>[`trackingServer`](configuration-variables.md#retired-configuration-variables) est une variante retirée de cette variable. Il a spécifié le domaine pour les données envoyées via HTTP ; avec la prévalence de HTTPS, utilisez plutôt `trackingServerSecure`. Si `s.trackingServerSecure` n’est pas renseigné, AppMeasurement revient à la valeur `s.trackingServer`.

## Domaine Edge utilisant l’extension Web SDK

Web SDK utilise le domaine [!UICONTROL Edge] pour gérer le serveur de suivi et le serveur de suivi sécurisé. Vous pouvez définir la valeur du domaine [!UICONTROL Edge souhaité] lors de la configuration de l’extension Web SDK.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Sélectionnez la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis sélectionnez le bouton **[!UICONTROL Configurer]** sous [!UICONTROL Adobe Experience Platform Web SDK].
1. Définissez le champ de texte **[!UICONTROL domaine]** souhaité.

Voir [Configurer l’extension Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=fr) dans la documentation de Web SDK pour plus d’informations.

>[!TIP]
>
>Si votre organisation passe à Web SDK à partir d’une implémentation d’extension AppMeasurement ou Analytics, ce champ peut utiliser la même valeur contenue dans `trackingServerSecure` (ou `trackingServer`).

## Domaine Edge implémentant manuellement le SDK Web

Configurez le SDK à l’aide de [`edgeDomain`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/edgedomain). Le champ est une chaîne qui détermine le domaine vers lequel envoyer des données.

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## Serveur de suivi SSL utilisant l’extension Adobe Analytics

[!UICONTROL Le serveur de suivi SSL] est un champ sous l’accordéon [!UICONTROL Général] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Sélectionnez la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL  Extensions] puis sélectionnez le bouton **[!UICONTROL Configurer]** sous Adobe Analytics.
1. Développez l’accordéon [!UICONTROL Général], qui affiche le champ [!UICONTROL Serveur de suivi SSL].

Si ce champ n’est pas renseigné, la valeur par défaut est celle indiquée dans [!UICONTROL Serveur de suivi]. Si [!UICONTROL Serveur de suivi SSL] et [!UICONTROL Serveur de suivi] sont tous deux vides, la valeur par défaut est `[rsid].data.adobedc.net`.

## s.trackingServerSecure dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.trackingServerSecure` est une chaîne qui contient le domaine pour envoyer des données à Adobe. Il s’agit uniquement du domaine ; omettez le protocole, le chemin, le port et les barres obliques. Si cette variable est vide, elle utilise la valeur de la variable `s.trackingServer`. Si les champs `s.trackingServerSecure` et `s.trackingServer` sont vides, la valeur par défaut est `[rsid].2o7.net`.

```js
// Example value when using a first-party domain
s.trackingServerSecure = "data.example.com";

// Example value when using a third-party domain
s.trackingServerSecure = "example.data.adobedc.net";
```

## Considérations relatives à la détermination de la valeur de `trackingServerSecure`

La valeur que vous utilisez pour `trackingServerSecure` (ou `edgeDomain`) dépend de la manière dont votre organisation envoie les données à Adobe :

* **Si votre organisation utilise un domaine propriétaire** par exemple par le biais du [programme de certificat géré par Adobe](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/adobe-managed-cert) d’un [certificat géré par le client](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/customer-managed-cert) ou d’un [réseau de diffusion de contenu (CDN)](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cdn), définissez la valeur sur ce domaine. Par exemple : `data.example.com`.
* **Si votre organisation utilise un domaine tiers** définissez la valeur sur votre sous-domaine d’ID client de `data.adobedc.net`. Par exemple : `example.data.adobedc.net`.

Voir [Choisir un domaine de collecte de données](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/collection-domain) dans le guide d’interface et d’administration de CX Enterprise pour obtenir des détails sur chaque option, y compris sur la recherche de votre identifiant client.

Adobe recommande vivement de conserver ces informations dans un [ document de conception de solution](../../prepare/solution-design.md) afin d’assurer la cohérence au sein de votre entreprise.

## Ramifications de la non-utilisation du service d’identification des visiteurs ou du service Experience Platform Identity

Adobe recommande vivement d’utiliser l’ECID comme principale forme d’identité du visiteur dans toutes les implémentations. La collecte des ECID peut être implémentée de plusieurs manières différentes, en fonction du type d’implémentation :

* Les implémentations AppMeasurement manuelles utilisent `VisitorAPI.js` et appellent la méthode `getInstance` . Pour plus d’informations, voir [Implémentation du service d’identification des visiteurs pour Analytics](https://experienceleague.adobe.com/en/docs/id-service/using/implementation/setup-analytics).
* Les implémentations qui utilisent l’extension de balise Adobe Analytics utilisent l’extension de balise [[!UICONTROL Service Experience Cloud ID]](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/id-service/overview), qui met en œuvre le service d’identification des visiteurs. Une fois ajouté, aucune configuration supplémentaire n’est nécessaire.
* Les implémentations utilisant n’importe quel format de Web SDK (`alloy.js` ou l’extension de balise Web SDK) incluent automatiquement Experience Platform Identity Service. Aucune configuration n’est requise au-delà de la définition de la valeur `edgeDomain` .

**Si votre implémentation n’utilise pas d’ECID** tenez compte des impacts suivants sur votre implémentation :

* Si vous n’utilisez ni le service d’identification des visiteurs ni le service d’identification Experience Platform, `trackingServerSecure` détermine l’emplacement des cookies. La définition de cette variable sur un domaine tiers force AppMeasurement à utiliser un cookie de secours, car la plupart des navigateurs modernes rejettent les cookies tiers.
* Le suivi des liens internes et Activity Map peuvent être moins fiables.
