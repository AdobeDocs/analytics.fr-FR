---
title: Migration d’AppMeasurement vers le SDK Web
description: Mettez à jour votre implémentation Adobe Analytics de la bibliothèque AppMeasurement JavaScript vers la bibliothèque Web SDK JavaScript.
exl-id: c90246e8-0f04-4655-9204-33c0ef611b13
source-git-commit: 05690cc8c1ea0364cbab86f35666df1cc1b13e69
workflow-type: tm+mt
source-wordcount: '1334'
ht-degree: 7%

---

# Migration d’AppMeasurement vers le SDK Web

Ce chemin d’implémentation implique une approche de migration méthodique pour passer d’une implémentation d’AppMeasurement à une implémentation de bibliothèque JavaScript Web SDK. D’autres chemins d’implémentation sont abordés sur des pages distinctes :

* [Extension Analytics vers l’extension Web SDK](analytics-extension-to-web-sdk.md) : adoptez une approche fluide et méthodique pour passer de l’extension de balise Adobe Analytics à l’extension de balise Web SDK. Cette approche supprime la nécessité d’utiliser XDM jusqu’à ce que votre entreprise soit prête à utiliser les services Adobe Experience Platform, tels que Customer Journey Analytics. Utilisez l’objet `data` au lieu de l’objet `xdm` pour envoyer des données à Adobe.
* [Bibliothèque Web SDK JavaScript](web-sdk-javascript-library.md) : nouvelle installation de Web SDK à l’aide de la bibliothèque Web SDK JavaScript (`alloy.js`). Gérez la mise en œuvre vous-même au lieu d’utiliser l’interface utilisateur des balises. Le groupe de champs Adobe Analytics ExperienceEvent, qui comprend des variables Analytics standard à inclure dans votre schéma XDM, est nécessaire.
* [Extension de balise Web SDK](web-sdk-tag-extension.md) : nouvelle installation de Web SDK dans laquelle vous gérez l’implémentation à l’aide de balises dans la collecte de données Adobe Experience Platform. Le groupe de champs Adobe Analytics ExperienceEvent, qui comprend des variables Analytics standard à inclure dans votre schéma XDM, est nécessaire.

## Avantages et inconvénients de ce chemin de mise en œuvre

L’utilisation de cette approche de migration présente à la fois des avantages et des inconvénients. Évaluez soigneusement chaque option pour décider quelle approche est la meilleure pour votre organisation.

| Avantages | Inconvénients |
| --- | --- |
| <ul><li>**Utilise votre implémentation existante** : bien que cette approche nécessite quelques modifications d’implémentation, l’implémentation ne part pas de zéro. Vous pouvez utiliser votre couche de données et votre code existants avec un minimum de modifications de la logique d’implémentation.</li><li>**Ne nécessite pas de schéma** : pour cette étape de la migration vers le Web SDK, vous n’avez pas besoin de schéma XDM. Vous pouvez plutôt renseigner l’objet `data` , qui envoie directement les données à Adobe Analytics. Une fois la migration vers Web SDK terminée, vous pouvez créer un schéma pour votre organisation et utiliser le mappage des flux de données pour renseigner les champs XDM applicables. Si un schéma était requis à cette étape du processus de migration, votre organisation serait forcée d’utiliser un schéma XDM Adobe Analytics. L’utilisation de ce schéma rend plus difficile, pour votre organisation, l’utilisation de votre propre schéma à l’avenir.</li></ul> | <ul><li>**Les modifications d’implémentation nécessitent l’intervention d’un développeur** : si vous souhaitez apporter des modifications à votre implémentation de Web SDK, vous devez collaborer avec votre équipe de développement pour modifier le code sur votre site. L’approche qui [migre vers l’extension de balise Web SDK](analytics-extension-to-web-sdk.md) évite cet inconvénient.</li><li>**Dette technique d’implémentation** : étant donné que cette approche utilise une forme modifiée de votre implémentation existante, il peut être plus difficile de suivre la logique d’implémentation et d’effectuer des modifications à l’avenir si nécessaire.</li><li>**Nécessite un mappage pour l’envoi de données à Platform** : lorsque votre organisation est prête à utiliser Customer Journey Analytics, vous devez envoyer des données à un jeu de données dans Adobe Experience Platform. Cette action nécessite que chaque champ de l’objet `data` soit une entrée dans l’outil de mappage de flux de données qui l’affecte à un champ de schéma XDM. Le mappage ne doit être effectué qu’une seule fois pour ce workflow, ce qui évite toute modification de l’implémentation. Cependant, il s’agit d’une étape supplémentaire qui n’est pas requise lors de l’envoi de données dans un objet XDM.</li></ul> |

Adobe recommande de suivre ce chemin d’implémentation dans les scénarios suivants :

* Vous disposez déjà d’une implémentation utilisant la bibliothèque JavaScript Adobe Analytics AppMeasurement. Si vous disposez d’une implémentation utilisant l’extension de balise Adobe Analytics, suivez [Migration de l’extension de balise Adobe Analytics vers l’extension de balise Web SDK](analytics-extension-to-web-sdk.md) à la place.
* Vous avez l’intention d’utiliser Customer Journey Analytics à l’avenir, mais vous ne souhaitez pas remplacer votre implémentation Analytics par une implémentation de SDK Web à partir de zéro. Le remplacement de votre implémentation à partir de zéro sur le Web SDK nécessite le plus d’efforts, mais offre également l’architecture d’implémentation à long terme la plus viable. Si votre entreprise est prête à passer par une implémentation propre de Web SDK, consultez [Ingestion de données via le SDK web Adobe Experience Platform](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) dans le guide d’utilisation de Customer Journey Analytics.

## Étapes requises pour migrer vers Web SDK

Les étapes suivantes contiennent des objectifs concrets à atteindre. Cliquez sur chaque étape pour obtenir des instructions détaillées sur la manière de procéder.

+++**1. Créer et configurer un flux de données**

Créez un flux de données dans la collecte de données Adobe Experience Platform. Lorsque vous envoyez des données à ce flux de données, il transfère les données vers Adobe Analytics. À l’avenir, ce même flux de données transfèrera des données à Customer Journey Analytics.

1. Accédez à [experience.adobe.com](https://experience.adobe.com) et connectez-vous à l’aide de vos informations d’identification.
1. Utilisez la page d’accueil ou le sélecteur de produits en haut à droite pour accéder à **[!UICONTROL Collecte de données]**.
1. Dans le volet de navigation de gauche, sélectionnez **[!UICONTROL Flux de données]**.
1. Sélectionnez **[!UICONTROL Nouveau flux de données]**.
1. Saisissez le nom souhaité, puis sélectionnez **[!UICONTROL Enregistrer]**.
1. Une fois le flux de données créé, sélectionnez **[!UICONTROL Ajouter un service]**.
1. Dans le menu déroulant Service, sélectionnez **[!UICONTROL Adobe Analytics]**.
1. Saisissez le même identifiant de suite de rapports que le site auquel vous envoyez actuellement des données d’analyse. Cliquez sur **[!UICONTROL Enregistrer]**.

![Ajouter un service Adobe Analytics](assets/datastream-rsid.png) {style="border:1px solid lightslategray"}

Votre flux de données est maintenant prêt à recevoir et à transmettre des données à Adobe Analytics. Notez l’identifiant du flux de données, car il est obligatoire lors de la configuration de Web SDK dans le code.

+++

+++**2. Installez la bibliothèque JavaScript de Web SDK**

Référencez la dernière version de `alloy.js` afin que ses appels de méthode puissent être utilisés. Voir [Installer le SDK Web à l’aide de la bibliothèque JavaScript](https://experienceleague.adobe.com/fr/docs/experience-platform/web-sdk/install/library) pour plus d’informations et connaître les blocs de code à utiliser.

+++

+++**3. Configurez le SDK Web**

Configurez votre implémentation pour pointer vers le flux de données créé à l’étape précédente à l’aide de la commande Web SDK [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview). La commande `configure` doit être définie sur chaque page afin que vous puissiez l’inclure avec le code d’installation de la bibliothèque.

Utilisez les propriétés [`datastreamId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/datastreamid) et [`orgId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/orgid) dans la commande `configure` de Web SDK :

* Définissez la `datastreamId` sur l’identifiant du flux de données récupéré à l’étape précédente.
* Définissez le `orgId` sur l’organisation IMS de votre organisation.

```js
alloy("configure", {
    datastreamId: "ebebf826-a01f-4458-8cec-ef61de241c93",
    orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

Vous pouvez éventuellement définir d’autres propriétés dans la commande [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) en fonction des exigences d’implémentation de votre entreprise.

+++

+++**4. Mettez à jour la logique de code pour utiliser une payload JSON**

Modifiez votre implémentation Analytics de sorte qu’elle ne repose pas sur `AppMeasurement.js` ou l’objet `s`. Au lieu de cela, définissez des variables dans un objet JavaScript correctement formaté, qui est converti en objet JSON lorsqu’il est envoyé à Adobe. Le fait d’avoir une [ couche de données ](../../prepare/data-layer.md) sur votre site est extrêmement utile lors de la définition de valeurs, car vous pouvez continuer à référencer ces mêmes valeurs.

Pour envoyer des données à Adobe Analytics, la payload de Web SDK doit utiliser `data.__adobe.analytics` avec toutes les variables d’analyse définies dans cet objet. Les variables au sein de cet objet partagent des noms et des formats identiques à leurs équivalents de variables AppMeasurement. Par exemple, si vous définissez la variable `products`, ne la divisez pas en objets individuels comme vous le feriez avec XDM. Au lieu de cela, incluez-le en tant que chaîne, exactement comme si vous définissiez la variable `s.products` :

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

Cette payload contient toutes les valeurs souhaitées et toutes les références à l’objet `s` dans votre implémentation sont supprimées. Vous pouvez utiliser n’importe quelle ressource fournie par JavaScript pour définir cet objet de payload, y compris la notation par points pour définir des valeurs individuelles.

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

+++**5. Appels de méthode de mise à jour pour utiliser le SDK Web**

Mettez à jour toutes les instances où vous appelez [`s.t()`](../../vars/functions/t-method.md) et [`s.tl()`](../../vars/functions/tl-method.md), en les remplaçant par la commande [`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview). Trois scénarios sont à prendre en compte :

* **Suivi des pages vues** : remplacez l’appel de suivi des pages vues par la commande `sendEvent` de Web SDK :

  ```js
  // If your current implementation has this line of code:
  s.t();
  
  // Replace it with this line of code. The dataObj object contains the variables to send.
  alloy("sendEvent", dataObj);
  ```

* **Suivi automatique des liens** : la propriété de configuration [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) est activée par défaut. Il définit automatiquement les variables de suivi des liens appropriées pour envoyer des données à Adobe Analytics. Si vous souhaitez désactiver le suivi automatique des liens, définissez cette propriété sur `false` dans la commande [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview).

* **Suivi manuel des liens** : le SDK Web ne dispose pas de commandes distinctes entre les appels pageview et non-pageview. Fournissez cette distinction dans l’objet de payload.

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

+++**6. Validez et publiez les modifications**

Une fois que vous avez supprimé toutes les références à AppMeasurement et à l’objet `s`, publiez vos modifications dans votre environnement de développement afin de vérifier que la nouvelle implémentation fonctionne. Une fois que vous avez validé que tout fonctionne correctement, vous pouvez publier vos mises à jour en production.

Si la migration est correcte, `AppMeasurement.js` n’est plus nécessaire sur votre site et toutes les références à ce script peuvent être supprimées.

+++

À ce stade, votre implémentation Analytics se trouve entièrement sur le Web SDK et est correctement préparée pour passer à Customer Journey Analytics à l’avenir.
