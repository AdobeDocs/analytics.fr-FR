---
title: Migration d’AppMeasurement vers le SDK Web
description: Mettez à jour votre mise en oeuvre Adobe Analytics de la bibliothèque JavaScript AppMeasurement vers la bibliothèque JavaScript du SDK Web.
exl-id: c90246e8-0f04-4655-9204-33c0ef611b13
source-git-commit: 7bd4a188e5a2171260f1f0696d8bebad854dba4a
workflow-type: tm+mt
source-wordcount: '1334'
ht-degree: 0%

---

# Migration d’AppMeasurement vers le SDK Web

Ce chemin d’implémentation implique une approche de migration méthodique pour passer d’une implémentation d’AppMeasurement à une implémentation de bibliothèque JavaScript SDK Web. D’autres chemins de mise en oeuvre sont abordés sur des pages distinctes :

* [Extension Analytics vers l’extension SDK Web](analytics-extension-to-web-sdk.md): adoptez une approche fluide et méthodique pour passer de l’extension de balise Adobe Analytics à l’extension de balise SDK web. Cette approche élimine la nécessité d’utiliser XDM jusqu’à ce que votre entreprise soit prête à utiliser les services Adobe Experience Platform, tels que Customer Journey Analytics. Utilisez la variable `data` au lieu de l’objet `xdm` pour envoyer des données à Adobe.
* [Bibliothèque JavaScript du SDK Web](web-sdk-javascript-library.md): nouvelle installation du SDK Web à l’aide de la bibliothèque JavaScript du SDK Web (`alloy.js`). Gérez vous-même l’implémentation au lieu d’utiliser l’interface utilisateur des balises. Il nécessite que le groupe de champs ExperienceEvent d’Adobe Analytics, qui inclut des variables Analytics standard à inclure dans votre schéma XDM.
* [Extension de balise SDK Web](web-sdk-tag-extension.md): nouvelle installation du SDK Web où vous gérez l’implémentation à l’aide de balises dans la collecte de données Adobe Experience Platform. Il nécessite que le groupe de champs ExperienceEvent d’Adobe Analytics, qui inclut des variables Analytics standard à inclure dans votre schéma XDM.

## Avantages et inconvénients de ce chemin de mise en oeuvre

L’utilisation de cette approche de migration présente des avantages et des inconvénients. Pesez soigneusement chaque option pour choisir la méthode qui convient le mieux à votre entreprise.

| Avantages | Inconvénients |
| --- | --- |
| <ul><li>**Utilise votre mise en oeuvre existante**: bien que cette approche nécessite quelques modifications de mise en oeuvre, elle ne nécessite pas une mise en oeuvre entièrement nouvelle de toutes pièces. Vous pouvez utiliser votre couche de données et votre code existants avec un minimum de modifications de la logique d’implémentation.</li><li>**Ne nécessite pas de schéma**: pour cette étape de la migration vers le SDK Web, vous n’avez pas besoin d’un schéma XDM. Vous pouvez plutôt renseigner la variable `data` , qui envoie directement des données à Adobe Analytics. Une fois la migration vers le SDK Web terminée, vous pouvez créer un schéma pour votre organisation et utiliser le mappage de flux de données pour remplir les champs XDM applicables. Si un schéma était requis à ce stade du processus de migration, votre entreprise serait contrainte d’utiliser un schéma XDM Adobe Analytics. L’utilisation de ce schéma rend plus difficile l’utilisation de votre propre schéma par votre entreprise à l’avenir.</li></ul> | <ul><li>**Les modifications de mise en oeuvre nécessitent une intervention du développeur**: si vous souhaitez apporter des modifications à la mise en oeuvre de votre SDK Web, vous devez travailler avec votre équipe de développement pour modifier le code sur votre site. L&#39;approche [migre vers l’extension de balise SDK Web](analytics-extension-to-web-sdk.md) évite ce désavantage.</li><li>**Dette technique de mise en oeuvre**: comme cette approche utilise une forme modifiée de votre mise en oeuvre existante, il peut être plus difficile de suivre la logique de mise en oeuvre et d’effectuer des modifications ultérieurement, si nécessaire.</li><li>**Nécessite un mapping pour envoyer des données à Platform**: lorsque votre entreprise est prête à utiliser Customer Journey Analytics, vous devez envoyer des données à un jeu de données dans Adobe Experience Platform. Cette action requiert que chaque champ de la variable `data` être une entrée dans l’outil de mappage de flux de données qui l’affecte à un champ de schéma XDM ; Le mappage ne doit être effectué qu’une seule fois pour ce workflow, ce qui n’implique pas d’effectuer des modifications de mise en oeuvre. Cependant, il s’agit d’une étape supplémentaire qui n’est pas requise lors de l’envoi de données dans un objet XDM.</li></ul> |

Adobe recommande de suivre ce chemin d’implémentation dans les scénarios suivants :

* Vous disposez d’une mise en oeuvre existante à l’aide de la bibliothèque JavaScript Adobe Analytics AppMeasurement. Si vous disposez d’une implémentation à l’aide de l’extension de balise Adobe Analytics, suivez [Migration de l’extension de balise Adobe Analytics vers l’extension de balise SDK Web](analytics-extension-to-web-sdk.md) au lieu de .
* Vous prévoyez d’utiliser Customer Journey Analytics à l’avenir, mais ne souhaitez pas remplacer votre mise en oeuvre Analytics par une mise en oeuvre SDK Web de A à Z. Le remplacement de votre implémentation de A à Z sur le SDK Web nécessite le plus d’efforts, mais offre également l’architecture d’implémentation à long terme la plus viable. Si votre entreprise est disposée à entreprendre une implémentation propre du SDK Web, reportez-vous à la section [Ingestion de données via le SDK Web de Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) dans le guide d’utilisation du Customer Journey Analytics.

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

![Ajout du service Adobe Analytics](assets/datastream-rsid.png) {style="border:1px solid lightslategray"}

Votre flux de données est maintenant prêt à recevoir et à transmettre des données à Adobe Analytics. Notez l’identifiant de la banque de données, car cet identifiant est requis lors de la configuration du SDK Web dans le code.

+++

+++**2. Installation de la bibliothèque JavaScript du SDK Web**

Référencez la dernière version de `alloy.js` ses appels de méthode peuvent donc être utilisés. Voir [Installation du SDK Web à l’aide de la bibliothèque JavaScript](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library) pour plus de détails et des blocs de code à utiliser.

+++

+++**3. Configuration du SDK Web**

Configurez votre mise en oeuvre de manière à ce qu’elle pointe vers le flux de données créé à l’étape précédente à l’aide du SDK Web. [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) . La variable `configure` doit être définie sur chaque page afin que vous puissiez l’inclure avec le code d’installation de la bibliothèque.

Utilisez la variable [`edgeConfigId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/edgeconfigid) et [`orgId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/orgid) propriétés dans le SDK Web `configure` command :

* Définissez la variable `edgeConfigId` à l’identifiant du flux de données récupéré à l’étape précédente.
* Définissez la variable `orgId` à l’organisation IMS de votre entreprise.

```js
alloy("configure", {
    "edgeConfigId": "ebebf826-a01f-4458-8cec-ef61de241c93",
    "orgId": "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

Vous pouvez éventuellement définir d’autres propriétés dans la variable [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) en fonction des exigences de mise en oeuvre de votre entreprise.

+++

+++**4. Mise à jour de la logique de code pour utiliser une payload JSON**

Modifiez votre mise en oeuvre Analytics de sorte qu’elle ne repose pas sur `AppMeasurement.js` ou le `s` . Définissez plutôt des variables dans un objet JavaScript correctement formaté, qui est converti en objet JSON lorsqu’il est envoyé à Adobe. Pour [Couche de données](../../prepare/data-layer.md) sur votre site vous aide considérablement lors de la définition de valeurs, car vous pouvez continuer à référencer ces mêmes valeurs.

Pour envoyer des données à Adobe Analytics, la charge utile du SDK Web doit utiliser `data.__adobe.analytics` avec toutes les variables analytics définies dans cet objet. Les variables de cet objet partagent les mêmes noms et formats que leurs équivalents de variable d’AppMeasurement. Par exemple, si vous définissez la variable `products` , ne le divisez pas en objets individuels comme vous le feriez avec XDM. Au lieu de cela, incluez-le comme chaîne si vous avez défini la variable `s.products` variable :

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

En fin de compte, cette payload contient toutes les valeurs souhaitées et toutes les références au `s` dans votre mise en oeuvre sont supprimés. Vous pouvez utiliser n’importe quelle ressource fournie par JavaScript pour définir cet objet de payload, y compris la notation par points pour définir des valeurs individuelles.

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

Mettre à jour toutes les instances où vous appelez [`s.t()`](../../vars/functions/t-method.md) et [`s.tl()`](../../vars/functions/tl-method.md), en les remplaçant par [`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview) . Trois scénarios sont à prendre en compte :

* **Suivi des pages vues**: remplacez l’appel de suivi des pages vues par le SDK Web. `sendEvent` command :

  ```js
  // If your current implementation has this line of code:
  s.t();
  
  // Replace it with this line of code. The dataObj object contains the variables to send.
  alloy("sendEvent", dataObj);
  ```

* **Suivi automatique des liens**: la variable [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) La propriété de configuration est activée par défaut. Il définit automatiquement les variables de suivi des liens correctes pour envoyer des données à Adobe Analytics. Pour désactiver le suivi automatique des liens, définissez cette propriété sur `false` dans la fonction [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) .

* **Suivi manuel des liens**: le SDK Web ne comporte pas de commandes distinctes entre les appels pageview et non pageview. Précisez cette distinction dans l’objet de charge utile.

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

Une fois que vous avez supprimé toutes les références à AppMeasurement et au `s` , publiez vos modifications dans votre environnement de développement pour vérifier que la nouvelle mise en oeuvre fonctionne. Une fois que vous avez vérifié que tout fonctionne correctement, vous pouvez publier vos mises à jour en production.

Si la migration est correcte, `AppMeasurement.js` n’est plus nécessaire sur votre site et toutes les références à ce script peuvent être supprimées.

+++

À ce stade, votre mise en oeuvre d’Analytics se trouve entièrement sur le SDK Web et est prête à passer à Customer Journey Analytics ultérieurement.
