---
title: Identification des visiteurs à l’aide d’AppMeasurement
description: Identifier correctement les visiteurs et visiteuses lors de l’implémentation d’Adobe Analytics avec AppMeasurement.
source-git-commit: 779ba5b0a1d71467aaaf3872fd707cc323ae8af2
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%

---

# Identification des visiteurs à l’aide d’AppMeasurement

AppMeasurement est l’ancienne bibliothèque JavaScript d’Adobe Analytics pour la collecte de données. Bien qu’AppMeasurement offre en lui-même un moyen natif d’identifier les visiteurs, de nombreux navigateurs modernes rejettent les cookies tiers qu’il tente de définir. Adobe recommande vivement d’utiliser le service d’identification des visiteurs Adobe Experience Cloud dans toutes les mises en œuvre afin de se conformer aux normes modernes de confidentialité des navigateurs. Toutes les versions d’AppMeasurement sont fournies avec `VisitorAPI.js`, la bibliothèque JavaScript utilisée pour mettre en œuvre le service d’identification des visiteurs.

## Identification des visiteurs à l’aide du service d’identification des visiteurs (recommandé)

Assurez-vous d’être préparé avec les éléments suivants :

* Téléchargez la [dernière version d’AppMeasurement](https://github.com/adobe/appmeasurement). La bibliothèque téléchargée comprend à la fois `AppMeasurement.js` et `VisitorAPI.js`.
* Un développement [identifiant de suite de rapports](/help/admin/tools/manage-rs/new-rs/new-report-suite.md).
* Le domaine Edge souhaité pour [`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md).
* Votre identifiant de l’organisation IMS :
   1. Connectez-vous à [experience.adobe.com](https://experience.adobe.com) à l’aide de vos informations d’identification Adobe ID.
   1. N’importe où dans l’interface d’Experience Cloud, appuyez sur `[Cmd]` + `[I]` (iOS) ou `[Ctrl]` + `[I]` (Windows).
   1. Un **[!UICONTROL Débogueur de données utilisateur]** s’affiche. Sélectionnez l’onglet **[!UICONTROL Organisations affectées]**.
   1. Développez l’organisation IMS souhaitée.
   1. Recherchez le champ **[!UICONTROL ID]**.

Une fois que vous disposez des ressources ci-dessus, la page d’exemple de base suivante contient le minimum d’appels requis pour envoyer des données à Adobe Analytics :

```html
<html>
  <head>
    <title>Example AppMeasurement implementation page</title>
    <script src="AppMeasurement.js"></script>
    <script src="VisitorAPI.js"></script>
  </head>
  <body>
    <h1>Hello world!</h1>
    <script>
      var s = s_gi("examplersid"); // Include development report suite ID here
      s.trackingServerSecure = "example.data.adobedc.net"; // Include edge domain here
      s.visitor = Visitor.getInstance("ADB3LETTERSANDNUMBERS@AdobeOrg"); // Include IMS org ID here
      s.pageName = document.title;
      s.t();
    </script>
  </body>
</html>
```

>[!TIP]
>
>Vous pouvez déterminer si un accès utilise le service d’identification des visiteurs en attribuant la présence de `Visitor` à une variable personnalisée dans [`doPlugins`](/help/implement/vars/functions/doplugins.md) :
>
>```js
>s.doPlugins = function() {
>   s.prop1 = typeof(Visitor) != "undefined" ? "VisitorAPI present" : "VisitorAPI missing";
>};
>```

## Identification des visiteurs à l’aide du cookie `s_vi` (déconseillé)

>[!IMPORTANT]
>
>Adobe déconseille d&#39;utiliser cette méthode pour identifier les visiteurs.

Si votre entreprise n’utilise pas le service d’identification des visiteurs, AppMeasurement utilise sa propre forme d’identification des visiteurs. Lorsqu’un visiteur ou une visiteuse arrive sur votre site pour la première fois, la bibliothèque recherche un cookie [`s_vi`](https://experienceleague.adobe.com/fr/docs/core-services/interface/data-collection/cookies/analytics). Ce cookie est défini sur le domaine correspondant à [`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md) (pour HTTPS) ou [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md) (pour HTTP).

* Si vous participez au [programme de certificat géré](https://experienceleague.adobe.com/fr/docs/core-services/interface/data-collection/adobe-managed-cert), votre serveur de suivi est généralement un domaine propriétaire, ce qui rend les cookies `s_vi` propriétaires.
* Si vous ne participez pas au programme de certificat géré, le serveur de suivi est généralement un sous-domaine de `adobedc.net`, `omtrdc.net` ou `2o7.net`, ce qui fait du cookie `s_vi` un cookie tiers. En raison des normes modernes de confidentialité des navigateurs, les cookies tiers sont rejetés par la plupart des navigateurs. Une fois rejeté, AppMeasurement tente de définir un cookie de secours propriétaire (`fid`) à la place.

Si vous définissez correctement `trackingServerSecure`, aucune autre mesure d’identification des visiteurs n’est requise.

## Identification des visiteurs à l’aide de `visitorID` (déconseillé)

>[!IMPORTANT]
>
>Adobe déconseille d&#39;utiliser cette méthode pour identifier les visiteurs.

L’utilisation de la variable [`visitorID`](/help/implement/vars/config-vars/visitorid.md) permet à votre organisation de réaliser un contrôle indépendant et d’identifier les visiteurs. Si vous utilisez `visitorID`, notez les restrictions suivantes :

* Chaque accès doit contenir la même valeur `visitorID` pour être comptabilisé comme un seul visiteur.
   * Tous les accès qui omettent `visitorID` tentent automatiquement d’utiliser une autre méthode d’identification des visiteurs, en les traitant comme un visiteur distinct.
   * Tous les accès contenant une valeur de `visitorID` différente d’un accès précédent sont traités comme un visiteur distinct.
   * Adobe n’offre aucun moyen d’assembler des accès à l’aide de différents identifiants visiteur.
* Les audiences partagées, Analytics for Target et les attributs du client ne sont pas pris en charge avec les visiteurs identifiés à l’aide de `visitorID`.

Voir [`visitorID`](/help/implement/vars/config-vars/visitorid.md) pour obtenir des instructions d’implémentation à l’aide de cette variable.
