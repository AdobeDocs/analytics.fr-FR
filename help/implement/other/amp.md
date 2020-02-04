---
title: Implémentation avec AMP
description: Implémentez Adobe Analytics sur les pages AMP.
translation-type: tm+mt
source-git-commit: 9d2007bead6a4963022f8ea884169802b1c002ff

---


# Implémentation avec AMP

[AMP](https://amp.dev) est une structure HTML open-source qui fournit une méthode simple pour créer des pages Web à chargement rapide et fluide.

Dans la mesure où Adobe Analytics utilise une bibliothèque JavaScript pour compiler et envoyer une demande d’image, des ajustements sont nécessaires dans votre implémentation pour envoyer des données à Adobe sur les pages utilisant AMP.

## Déterminer la méthode d’implémentation d’Adobe Analytics sur les pages utilisant AMP

Adobe a créé deux méthodes pour implémenter Adobe Analytics sur les pages utilisant AMP. Tous deux utilisent la balise `<amp-analytics>` HTML. Voir la balise [](https://github.com/ampproject/amphtml/tree/master/extensions/amp-analytics) amp-analytics sur le GitHub ampproject pour plus d’informations.

* **Utilisez le modèle`"adobeanalytics"`de** suivi : Générer la requête Analytics directement sur la page
* **Utilisez le modèle`"analytics_nativeConfig"`de** suivi : Utiliser un iframe contenant le même code AppMeasurement que celui que vous déployez sur votre site normal

Le tableau suivant compare ces deux méthodes :

|  | **modèle &quot;adobeanalytics&quot;** | **modèle &quot;adobeanalytics_nativeConfig&quot;** |
|---|---|---|
| Nombre de visiteurs/visites dans la suite de rapports existante | Gonflement élevé | Gonflement minimal |
| Utilisation d’une suite de rapports distincte | Recommandée | Pas nécessaire |
| Visiteurs nouveaux/récurrents | Non pris en charge | Pris en charge |
| Service d’identification des visiteurs | Non pris en charge | Pris en charge |
| Suivi des vidéos et des liens | Prise en charge partielle | Pas encore pris en charge |
| Difficulté de mise en œuvre | Parfois difficile | Relativement facile |
| Intégrations d’Adobe Experience Cloud | Non pris en charge | Prise en charge partielle |

Pesez les avantages et les inconvénients au sein de votre organisation pour déterminer la méthode à utiliser. Pour obtenir un exemple de code, reportez-vous aux exemples [](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web) AMP du référentiel GitHub d’Adobe.

> [!WARNING] N’utilisez pas à la fois les modèles `"adobeanalytics"` et `"adobeanalytics_nativeConfig"` les modèles de la même page à l’aide d’AMP. Si vous tentez de le faire, vous pouvez générer des erreurs dans la console du navigateur et comptabiliser deux fois les visiteurs.

## Méthode 1 : Utilisez la balise amp-analytics avec le modèle &quot;adobeanalytics&quot;.

The `"adobeanalytics"` tracking template uses the `<amp-analytics>` HTML tag to construct a tracking request directly. Vous pouvez spécifier des requêtes d’accès qui se déclenchent sur des événements de page spécifiques, comme la page qui devient visible ou sur un clic. Les événements de clic peuvent être personnalisés afin de s’appliquer à certains identifiants ou classes d’élément en spécifiant un sélecteur. Vous pouvez charger le modèle en ajoutant `type="adobeanalytics"` à la balise amp-analytics.

Dans l’exemple de code suivant, deux déclencheurs sont définis : `pageLoad` et `click`. Le `pageLoad` déclencheur se déclenche lorsque le document devient visible et inclut la `pageName` variable définie dans la `vars` section. The second trigger `click` fires when a button is clicked. `eVar1` est définie pour cet événement avec la valeur `button clicked`.

```html
<amp-analytics type="adobeanalytics">
  <script type="application/json">
    {
      "requests": {
        "myClick": "${click}&v1=${eVar1}",
      },
      "vars": {
        "host": "example.sc.omtrdc.net",
        "reportSuites": "reportSuiteID",
        "pageName": "Adobe Analytics Using amp-analytics tag"
      },
      "triggers": {
        "pageLoad": {
          "on": "visible",
          "request": "pageView"
        },
        "click": {
          "on": "click",
          "selector": "button",
          "request": "myClick",
          "vars": {
            "eVar1": "button clicked"
          }
        }
      }
    }
  </script>
</amp-analytics>
```

In the `click` trigger, you can specify a selector to ensure that whenever the specific DOM element is clicked (in this case, any button), the `buttonClick` request is fired and is automatically set to denote this hit as a link tracking call.

En outre, `amp-analytics` prend en charge un certain nombre de substitutions de variables de sorte que le projet AMP puisse fournir des valeurs de données qu’il connaît. Pour plus d’informations, voir [variables prises en charge dans amp-analytics](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md) sur GitHub.

> [!NOTE] Les demandes d’image envoyées à Adobe à l’aide de cette méthode n’incluent pas les données de nombreux rapports par défaut (navigateur, taille d’écran ou référent, par exemple). Si vous souhaitez inclure ces informations dans les accès, veillez à les inclure dans la chaîne de requête de demande d’image. Voir Paramètres [de requête de collecte de](../validate/query-parameters.md) données pour plus d’informations.

Adobe identifie les visiteurs à l’aide d’une fonction AMP intégrée et définit le cookie `adobe_amp_id`. Cet identifiant visiteur est unique à tout autre identifiant défini par Adobe Analytics (le `s_vi` cookie, par exemple). Le service Adobe Experience Cloud ID n’est pas pris en charge à l’aide de cette méthode d’implémentation.

> [!NOTE] AMP utilise des CDN pour diffuser du contenu. Il est structuré de manière à comptabiliser un visiteur unique différent pour chaque réseau de diffusion de contenu à partir duquel un visiteur récupère du contenu, ce qui peut gonfler le nombre de visiteurs uniques.

Il est recommandé d’utiliser une suite de rapports distincte pour les pages AMP en raison de la manière dont AMP identifie les visiteurs uniques.

This solution requires that the tracking server you specify in the `host` property matches the tracking server on your main site, so that your existing privacy policy controls are respected. Sinon, créez une stratégie de confidentialité distincte pour les pages utilisant AMP.

## Méthode 2 : Utilisez la balise amp-analytics avec le modèle &quot;adobeanalytics_nativeConfig&quot;.

The `"adobeanalytics_nativeConfig"` tag is easier to implement, as it uses the same tagging methodology you use on your normal web pages. Ajoutez les éléments suivants à votre `amp-analytics` balise :

```html
<amp-analytics type="adobeanalytics_nativeConfig">
  <script type="application/json">
    {
      "requests": {
        "base": "https://${host}",
        "iframeMessage": "${base}/stats.html?campaign=${queryParam(campaign)}&pageURL=${ampdocUrl}&ref=${documentReferrer}"
      },
      "vars": {
        "host": "example.sc.omtrdc.net"
      },
      "extraUrlParams": {
      "pageName": "Example AMP page",
      "v1": "eVar1 example value"
      }
    }
 </script>
</amp-analytics>
```

Une page HTML hébergée sur vos serveurs Web est également requise :

```html
<html>
  <head>
    <title>Stats Example</title>
    <script language="JavaScript" type="text/javascript" src="VisitorAPI.js"></script>
    <script language="JavaScript" type="text/javascript" src="AppMeasurement.js"></script>
  </head>
  <body>
    <script>
      var v_orgId = "INSERT-ORG-ID-HERE";
      var s_account = "examplersid";
      var s_trackingServer = "example.sc.omtrdc.net";
      var visitor = Visitor.getInstance(v_orgId);
      visitor.trackingServer = s_trackingServer;
      var s = s_gi(s_account);
      s.account = s_account;
      s.trackingServer = s_trackingServer;
      s.visitorNamespace = s_visitorNamespace;
      s.visitor = visitor;
      s.pageName = s.Util.getQueryParam("pageName");
      s.eVar1 = s.Util.getQueryParam("v1");
      s.campaign = s.Util.getQueryParam("campaign");
      s.pageURL = s.Util.getQueryParam("pageURL");
      s.referrer = s.Util.getQueryParam("ref");
      s.t();
    </script>
  </body>
</html>
```

This approach sends data to a utility web page through query string parameters added to the `iframeMessage` request parameter. These query string parameters can be named whatever you like, as long as your `stats.html` page is configured to collect data from them.

Le modèle `"adobeanalytics_nativeConfig"` ajoute également des paramètres de chaîne de requête en fonction des variables répertoriées dans la section `extraUrlParams` de la balise amp-analytics. Dans l’exemple ci-dessus, les paramètres `pageName` et `v1` sont inclus.

> [!IMPORTANT] Votre `stats.html` page doit être hébergée sur un sous-domaine distinct du domaine sur lequel l’AMP elle-même est hébergée. L’infrastructure AMP n’autorise pas les iframes issues du même sous-domaine que celui où existe la page AMP même. Par exemple, si votre fichier AMP est hébergé sur `amp.example.com`, hébergez votre `stats.html` page sur un sous-domaine distinct, tel que `ampmetrics.example.com`.

Avec cette méthode, si un utilisateur choisit de ne pas effectuer le suivi sur votre site principal, il est également désabonné du suivi sur tous vos fichiers AMP. L’utilisation de cette page utilitaire signifie également qu’AMP peut prendre en charge le service Adobe Experience Cloud ID. Une suite de rapports distincte n’est pas requise.

Le suivi des liens et des vidéos ne peuvent pas être utilisés avec cette méthode. La `iframeMessage` balise AMP ne peut se charger qu’une seule fois par page. Vous ne pouvez donc pas envoyer d’autres demandes d’image après le chargement du cadre. Cette méthode nécessite également davantage de ressources de traitement à exécuter, ce qui peut avoir un impact sur les performances de défilement. Cette méthode n’affecte pas le temps de chargement des pages, car toutes les ressources se chargent de manière asynchrone.

## FAQ

**Le suivi vidéo est-il disponible pour l’une ou l’autre méthode ?**

Non. La norme AMP ne prend en charge que les déclencheurs pour &quot;visible&quot;, &quot;click&quot; et &quot;timer&quot;. Il ne prend pas encore en charge les déclencheurs explicites pour le suivi vidéo que la `amp-analytics` balise peut écouter. En outre, le `"adobeanalytics_nativeConfig"` modèle ne peut se charger qu’une seule fois, de sorte que les demandes d’image ultérieures après le chargement d’une page ne sont pas possibles.

**Comment puis-je différencier les visiteurs AMP des autres dans mes données ?**

Pour toutes les pages AMP, la dimension Version [!UICONTROL de] JavaScript collecte une valeur similaire à `AMP vX.X`. Vous pouvez également définir une dimension personnalisée sur &quot;AMP&quot; afin de segmenter ces visiteurs.

**En quoi cette méthode d’implémentation est-elle comparée aux Instant Articles de Facebook ?**

Les Instant Articles de Facebook prennent en charge une solution similaire à la `"adobeanalytics_nativeConfig"` méthode. La `stats.html` page de cette méthode peut répondre simultanément à vos besoins d’analyse pour AMP et FIA. Pour plus d’informations sur l’implémentation du suivi sur FIA, voir Instant Articles [de](fb-instant-articles.md)Facebook.
