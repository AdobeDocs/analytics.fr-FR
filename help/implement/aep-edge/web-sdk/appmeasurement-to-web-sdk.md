---
title: Migration d’AppMeasurement vers le SDK Web
description: Mettez à jour votre mise en oeuvre Adobe Analytics de la bibliothèque JavaScript AppMeasurement vers la bibliothèque JavaScript du SDK Web.
exl-id: c90246e8-0f04-4655-9204-33c0ef611b13
source-git-commit: 05690cc8c1ea0364cbab86f35666df1cc1b13e69
workflow-type: tm+mt
source-wordcount: '1334'
ht-degree: 7%

---

# Migration d’AppMeasurement vers le SDK Web

Ce chemin d’implémentation implique une approche de migration méthodique pour passer d’une implémentation d’AppMeasurement à une implémentation de bibliothèque JavaScript SDK Web. D’autres chemins de mise en oeuvre sont abordés sur des pages distinctes :

* [Extension Analytics vers l’extension SDK Web](analytics-extension-to-web-sdk.md) : adoptez une approche fluide et méthodique pour passer de l’extension de balise Adobe Analytics à l’extension de balise SDK Web. Cette approche élimine la nécessité d’utiliser XDM jusqu’à ce que votre entreprise soit prête à utiliser les services Adobe Experience Platform, tels que Customer Journey Analytics. Utilisez l’objet `data` au lieu de l’objet `xdm` pour envoyer des données à Adobe.
* [ Bibliothèque JavaScript SDK Web ](web-sdk-javascript-library.md) : nouvelle installation du SDK Web à l’aide de la bibliothèque JavaScript SDK Web (`alloy.js`). Gérez vous-même l’implémentation au lieu d’utiliser l’interface utilisateur des balises. Il nécessite que le groupe de champs ExperienceEvent d’Adobe Analytics, qui inclut des variables Analytics standard à inclure dans votre schéma XDM.
* [Extension de balise du SDK Web](web-sdk-tag-extension.md) : nouvelle installation du SDK Web dans laquelle vous gérez l’implémentation à l’aide de balises dans la collecte de données Adobe Experience Platform. Il nécessite que le groupe de champs ExperienceEvent d’Adobe Analytics, qui inclut des variables Analytics standard à inclure dans votre schéma XDM.

## Avantages et inconvénients de ce chemin de mise en oeuvre

L’utilisation de cette approche de migration présente des avantages et des inconvénients. Pesez soigneusement chaque option pour choisir la méthode qui convient le mieux à votre entreprise.

| Avantages | Inconvénients |
| --- | --- |
| <ul><li>**Utilise votre implémentation existante** : bien que cette approche nécessite quelques modifications d’implémentation, l’implémentation ne part pas de zéro. Vous pouvez utiliser votre couche de données et votre code existants avec un minimum de modifications de la logique d’implémentation.</li><li>**Ne nécessite pas de schéma** : pour cette étape de migration vers le SDK Web, vous n’avez pas besoin d’un schéma XDM. Vous pouvez à la place renseigner l’objet `data` qui envoie directement des données à Adobe Analytics. Une fois la migration vers le SDK Web terminée, vous pouvez créer un schéma pour votre organisation et utiliser le mappage de flux de données pour remplir les champs XDM applicables. Si un schéma était requis à ce stade du processus de migration, votre entreprise serait contrainte d’utiliser un schéma XDM Adobe Analytics. L’utilisation de ce schéma rend plus difficile l’utilisation de votre propre schéma par votre entreprise à l’avenir.</li></ul> | <ul><li>**Les modifications de mise en oeuvre nécessitent une intervention du développeur** : si vous souhaitez apporter des modifications à votre mise en oeuvre du SDK Web, vous devez travailler avec votre équipe de développement pour modifier le code sur votre site. L’approche que [migre vers l’extension de balise SDK Web](analytics-extension-to-web-sdk.md) évite cet inconvénient.</li><li>**Dette technique de mise en oeuvre** : comme cette approche utilise une forme modifiée de votre mise en oeuvre existante, il peut être plus difficile de suivre la logique de mise en oeuvre et d’effectuer des modifications ultérieurement, si nécessaire.</li><li>**Nécessite un mappage pour l’envoi de données à Platform** : lorsque votre organisation est prête à utiliser Customer Journey Analytics, vous devez envoyer des données à un jeu de données dans Adobe Experience Platform. Cette action nécessite que chaque champ de l’objet `data` soit une entrée dans l’outil de mappage de flux de données qui l’affecte à un champ de schéma XDM. Le mappage ne doit être effectué qu’une seule fois pour ce workflow, ce qui évite toute modification de l’implémentation. Cependant, il s’agit d’une étape supplémentaire qui n’est pas requise lors de l’envoi de données dans un objet XDM.</li></ul> |

Adobe recommande de suivre ce chemin d’implémentation dans les scénarios suivants :

* Vous disposez d’une mise en oeuvre existante à l’aide de la bibliothèque JavaScript Adobe Analytics AppMeasurement. Si vous disposez d’une implémentation à l’aide de l’extension de balise Adobe Analytics, suivez la procédure [Migration de l’extension de balise Adobe Analytics vers l’extension de balise SDK Web](analytics-extension-to-web-sdk.md) à la place.
* Vous prévoyez d’utiliser Customer Journey Analytics à l’avenir, mais ne souhaitez pas remplacer votre mise en oeuvre Analytics par une mise en oeuvre SDK Web de A à Z. Le remplacement de votre implémentation de A à Z sur le SDK Web nécessite le plus d’efforts, mais offre également l’architecture d’implémentation à long terme la plus viable. Si votre entreprise est disposée à entreprendre une implémentation propre du SDK Web, reportez-vous à la section [Ingestion de données via le SDK Web Adobe Experience Platform](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) du guide d’utilisation du Customer Journey Analytics.

## Procédure de migration vers le SDK Web

Les étapes suivantes contiennent des objectifs concrets. Cliquez sur chaque étape pour obtenir des instructions détaillées sur la manière d’y parvenir.

+++**1. Création et configuration d’un flux de données**

Créez un flux de données dans la collecte de données Adobe Experience Platform. Lorsque vous envoyez des données à ce flux de données, elles sont transférées à Adobe Analytics. À l’avenir, ce même flux de données transfère les données vers Customer Journey Analytics.

1. Accédez à [experience.adobe.com](https://experience.adobe.com) et connectez-vous à l’aide de vos informations d’identification.
1. Utilisez la page d’accueil ou le sélecteur de produits en haut à droite pour accéder à **[!UICONTROL Collecte de données]**.
1. Dans le volet de navigation de gauche, sélectionnez **[!UICONTROL Datastreams]**.
1. Sélectionnez **[!UICONTROL Nouveau flux de données]**.
1. Saisissez le nom de votre choix, puis sélectionnez **[!UICONTROL Enregistrer]**.
1. Une fois le flux de données créé, sélectionnez **[!UICONTROL Ajouter un service]**.
1. Dans le menu déroulant du service, sélectionnez **[!UICONTROL Adobe Analytics]**.
1. Saisissez le même identifiant de suite de rapports que le site auquel vous envoyez actuellement des données d’analyse. Cliquez sur **[!UICONTROL Enregistrer]**.

![Ajouter un service Adobe Analytics](assets/datastream-rsid.png) {style="border:1px solid lightslategray"}

Votre flux de données est maintenant prêt à recevoir et à transmettre des données à Adobe Analytics. Notez l’identifiant de la banque de données, car cet identifiant est requis lors de la configuration du SDK Web dans le code.

+++

+++**2. Installation de la bibliothèque JavaScript du SDK Web**

Référencez la dernière version de `alloy.js` afin que ses appels de méthode puissent être utilisés. Voir [Installation du SDK Web à l’aide de la bibliothèque JavaScript](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library) pour plus d’informations et les blocs de code à utiliser.

+++

+++**3. Configuration du SDK Web**

Configurez votre mise en oeuvre pour qu’elle pointe vers le flux de données créé à l’étape précédente à l’aide de la commande SDK Web [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) . La commande `configure` doit être définie sur chaque page afin que vous puissiez l’inclure avec le code d’installation de la bibliothèque.

Utilisez les propriétés [`datastreamId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/datastreamid) et [`orgId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/orgid) dans la commande du SDK Web `configure` :

* Définissez le `datastreamId` sur l’identifiant de la banque de données récupéré à l’étape précédente.
* Définissez le `orgId` sur l’organisation IMS de votre organisation.

```js
alloy("configure", {
    datastreamId: "ebebf826-a01f-4458-8cec-ef61de241c93",
    orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

Vous pouvez éventuellement définir d’autres propriétés dans la commande [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) en fonction des exigences d’implémentation de votre entreprise.

+++

+++**4. Mise à jour de la logique de code pour utiliser une charge utile JSON**

Modifiez votre mise en oeuvre Analytics de sorte qu’elle ne repose pas sur `AppMeasurement.js` ou l’objet `s`. Définissez plutôt des variables dans un objet JavaScript correctement formaté, qui est converti en objet JSON lorsqu’il est envoyé à l’Adobe. Disposer d’une [couche de données](../../prepare/data-layer.md) sur votre site aide considérablement lors de la définition de valeurs, car vous pouvez continuer à référencer ces mêmes valeurs.

Pour envoyer des données à Adobe Analytics, la charge utile du SDK Web doit utiliser `data.__adobe.analytics` avec toutes les variables d’analyse définies dans cet objet. Les variables de cet objet partagent les mêmes noms et formats que leurs équivalents de variable d’AppMeasurement. Par exemple, si vous définissez la variable `products`, ne la divisez pas en objets individuels comme vous le feriez avec XDM. Au lieu de cela, incluez-le comme chaîne si vous définissez la variable `s.products` :

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "products": "Shoes,Men's sneakers,1,49.99"
      }
    }
  }
}
```

En fin de compte, cette payload contient toutes les valeurs souhaitées et toutes les références à l’objet `s` dans votre mise en oeuvre sont supprimées. Vous pouvez utiliser n’importe quelle ressource fournie par JavaScript pour définir cet objet de charge utile, y compris la notation par points pour définir des valeurs individuelles.

```js
// Define the payload and set objects within it
var dataObj = {data: {__adobe: {analytics: {}}}};
dataObj.data.__adobe.analytics.pageName = window.document.title;
dataObj.data.__adobe.analytics.eVar1 = "Example value";

// Alternatively, set values in an object and use a spread operator to achieve identical results
var a = new Object;
a.pageName = window.document.title;
a.eVar1 = "Example value";
var dataObj = {data:{__adobe:{analytics:{...a}}}};
```

+++

+++**5. Mise à jour des appels de méthode pour utiliser le SDK Web**

Mettez à jour toutes les instances où vous appelez [`s.t()`](../../vars/functions/t-method.md) et [`s.tl()`](../../vars/functions/tl-method.md), en les remplaçant par la commande [`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview) . Trois scénarios sont à prendre en compte :

* **Suivi des pages vues** : remplacez l’appel de suivi des pages vues par la commande SDK Web `sendEvent` :

  ```js
  // If your current implementation has this line of code:
  s.t();
  
  // Replace it with this line of code. The dataObj object contains the variables to send.
  alloy("sendEvent", dataObj);
  ```

* **Suivi automatique des liens** : la propriété de configuration [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) est activée par défaut. Il définit automatiquement les variables de suivi des liens correctes pour envoyer des données à Adobe Analytics. Si vous souhaitez désactiver le suivi automatique des liens, définissez cette propriété sur `false` dans la commande [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview).

* **Suivi manuel des liens** : le SDK Web ne comporte pas de commandes distinctes entre les appels pageview et non pageview. Précisez cette distinction dans l’objet de charge utile.

  ```js
  // If your current implementation has this line of code:
  s.tl(true,"o","Example custom link");
  
  // Replace it with these lines of code. Add the required fields to the dataObj object.
  dataObj.data.__adobe.analytics.linkName = "Example custom link";
  dataObj.data.__adobe.analytics.linkType = "o";
  dataObj.data.__adobe.analytics.linkURL = "https://example.com";
  alloy("sendEvent", dataObj);
  ```

+++

+++**6. Validation et publication des modifications**

Une fois que vous avez supprimé toutes les références à AppMeasurement et à l’objet `s`, publiez vos modifications dans votre environnement de développement pour vérifier que la nouvelle mise en oeuvre fonctionne. Une fois que vous avez vérifié que tout fonctionne correctement, vous pouvez publier vos mises à jour en production.

Si la migration est effectuée correctement, `AppMeasurement.js` n’est plus nécessaire sur votre site et toutes les références à ce script peuvent être supprimées.

+++

À ce stade, votre mise en oeuvre d’Analytics se trouve entièrement sur le SDK Web et est prête à passer à Customer Journey Analytics ultérieurement.
