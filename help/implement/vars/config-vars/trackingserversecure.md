---
title: trackingServerSecure
description: Domaine utilisé pour envoyer des données à Adobe via HTTPS.
feature: Appmeasurement Implementation
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
role: Admin, Developer
source-git-commit: 7918b18e73618368543a996ca121b64b7afb33ab
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 13%

---

# trackingServerSecure

La variable `trackingServerSecure` détermine le domaine utilisé par AppMeasurement pour envoyer des données à Adobe via HTTPS. Si cette variable n’est pas correctement définie, votre mise en œuvre peut entraîner une perte de données.

Avant le service d’identités [Adobe Experience Cloud](https://experienceleague.adobe.com/en/docs/id-service/using/home), cette variable déterminait également où les cookies tiers étaient définis. Adobe recommande vivement d’utiliser le service d’ID dans toutes les implémentations lorsque cela est possible.

## Domaine Edge utilisant l’extension Web SDK

Web SDK utilise le domaine [!UICONTROL Edge] pour gérer le serveur de suivi et le serveur de suivi sécurisé. Vous pouvez définir la valeur du domaine [!UICONTROL Edge souhaité] lors de la configuration de l’extension Web SDK.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Sélectionnez la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis sélectionnez le bouton **[!UICONTROL Configurer]** sous [!UICONTROL Adobe Experience Platform Web SDK].
1. Définissez le champ de texte **[!UICONTROL domaine Edge]** souhaité.

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
1. Accédez à l’onglet [!UICONTROL &#x200B; Extensions] puis sélectionnez le bouton **[!UICONTROL Configurer]** sous Adobe Analytics.
1. Développez l’accordéon [!UICONTROL Général], qui affiche le champ [!UICONTROL Serveur de suivi SSL].

Si ce champ n’est pas renseigné, la valeur par défaut est celle indiquée dans [!UICONTROL Serveur de suivi]. Si [!UICONTROL Serveur de suivi SSL] et [!UICONTROL Serveur de suivi] sont tous deux vides, la valeur par défaut est `[rsid].data.adobedc.net`.

## s.trackingServerSecure dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.trackingServerSecure` est une chaîne qui contient le domaine pour envoyer des données à Adobe. Il s’agit uniquement du domaine ; omettez le protocole, le chemin, le port et les barres obliques. Si cette variable est vide, elle utilise la valeur de la variable `s.trackingServer`. Si les champs `s.trackingServerSecure` et `s.trackingServer` sont vides, la valeur par défaut est `[rsid].2o7.net`.

```js
// Example value when participating in the Adobe-managed certificate program
s.trackingServerSecure = "data.example.com";

// Example value sending data directly to Adobe
s.trackingServerSecure = "example.data.adobedc.net";
```

## Considérations relatives à la détermination de la valeur de `trackingServerSecure`

La valeur que vous utilisez pour `trackingServerSecure` (ou `edgeDomain`) dépend de plusieurs facteurs :

* Votre participation au programme de certificat géré par Adobe [&#128279;](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/adobe-managed-cert)
* Si le service d’identités [Adobe Experience Cloud est implémenté et correctement configuré](https://experienceleague.adobe.com/en/docs/id-service/using/home)

**Si votre entreprise participe au programme de certificat géré par Adobe**, définissez la valeur sur le domaine propriétaire sélectionné lors de la configuration du certificat. En règle générale, cette valeur est un sous-domaine détenu par votre organisation. Par exemple : `data.example.com`. Les enregistrements CNAME de votre organisation redirigent ces données vers Adobe.

**Si vous ne participez pas au programme de certificat**, définissez la valeur sur un sous-domaine de `data.adobedc.net`. Adobe recommande d’utiliser l’identifiant de société de votre organisation par souci de cohérence. Par exemple : `example.data.adobedc.net`. Procédez comme suit pour déterminer l’ID de votre société :

1. Connectez-vous à [experience.adobe.com](https://experience.adobe.com) à l’aide de vos informations d’identification Adobe ID.
1. N’importe où dans l’interface d’Experience Cloud, appuyez sur `[Cmd]` + `[I]` (iOS) ou `[Ctrl]` + `[I]` (Windows).
1. Un **[!UICONTROL Débogueur de données utilisateur]** s’affiche. Sélectionnez l’onglet **[!UICONTROL Organisations affectées]**.
1. Développez l’organisation IMS souhaitée.
1. Recherchez le champ **[!UICONTROL Client]**. Cette valeur est le sous-domaine de `data.adobedc.net` recommandé à utiliser.

>[!NOTE]
>
>N’utilisez aucun sous-domaine plus profond que `example.data.adobedc.net`. Par exemple, `custom.example.data.adobedc.net` n’est pas un serveur de suivi valide.

Les implémentations plus anciennes peuvent avoir des valeurs telles que `sc.omtrdc.net` ou `2o7.net`. Ceux-ci étaient principalement utilisés dans les versions précédentes d’Adobe Analytics et sont toujours valides.

Adobe recommande vivement de conserver ces informations dans un [&#x200B; document de conception de solution](../../prepare/solution-design.md) afin d’assurer la cohérence au sein de votre entreprise.

## Ramifications de la non-utilisation du service d’identification des visiteurs

Adobe recommande vivement d’utiliser le service d’identités [Adobe Experience Cloud Identity](https://experienceleague.adobe.com/en/docs/id-service/using/home) dans toutes les implémentations. Le service d’ID peut être implémenté de plusieurs manières différentes :

* Les implémentations AppMeasurement manuelles utilisent `VisitorAPI.js` et appellent la méthode `getInstance` . Pour plus d’informations, voir [Implémentation d’Experience Cloud Identity Service for Analytics](https://experienceleague.adobe.com/en/docs/id-service/using/implementation/setup-analytics).
* Les implémentations utilisant l’extension de balise Adobe Analytics utilisent l’extension de balise de service [Adobe Experience Cloud ID](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/id-service/overview). Une fois ajouté, aucune configuration supplémentaire n’est nécessaire.
* Les implémentations utilisant n’importe quel format de Web SDK (`alloy.js` ou l’extension de balise Web SDK) disposent déjà du service d’ID intégré en mode natif. Aucune configuration n’est requise au-delà de la définition de la valeur `edgeDomain` .

**Si votre implémentation n’utilise pas le service d’identités** tenez compte des impacts suivants sur votre implémentation :

* Si vous n’utilisez pas le service d’identités, `trackingServerSecure` détermine l’emplacement du cookie. La définition de cette variable sur un domaine tiers force AppMeasurement à utiliser un cookie de secours, car la plupart des navigateurs modernes rejettent les cookies tiers.
* Le suivi des liens internes et Activity Map peuvent être moins fiables.
