---
description: Mettez en œuvre le projet AMP (Accelerated Mobile Pages) dans Adobe Analytics.
keywords: Implémentation d'Analytics ; amp ; amp-analytics ; adobeanalytics, modèle ; adobeanalytics_ nativeconfig modèle ; suivi des clics ; augmentation du nombre de visiteurs ; ID d'ID
seo-description: Mettez en œuvre le projet AMP (Accelerated Mobile Pages) dans Adobe Analytics.
seo-title: Accelerated Mobile Pages
solution: Analytics
title: Accelerated Mobile Pages
topic: Développeur et mise en œuvre
uuid: c 86 e 4 a 80-7191-4 ee 7-ab 20-787730026 c 4 b
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Accelerated Mobile Pages

Mettez en œuvre le projet AMP (Accelerated Mobile Pages) dans Adobe Analytics.

Il s’agit d’un [projet Open Source](https://www.ampproject.org/) grâce auquel il est possible de créer des pages web pour du contenu statique restitué plus rapidement. Cette fonction est idéale pour les éditeurs qui souhaitent créer une fois un contenu optimisé pour les appareils mobiles et qui se chargera instantanément partout. Les sujets couverts sont les suivants :

* [Fonctionnement](../../implement/js-implementation/accelerated-mobile-pages.md#section_21C2836D63104794BCEBEECB6593AFBF)
* [Utilisation de la balise amp-analytics avec le modèle "adobeanalytics"](../../implement/js-implementation/accelerated-mobile-pages.md#section_2E4EBF4EF623440D95DE98E78C47244E)
* [Utilisation de la balise amp-analytics avec le modèle « adobeanalytics_nativeConfig »](../../implement/js-implementation/accelerated-mobile-pages.md#section_3556B68304A4492991F439885727E9FF)
* [Résumé](../../implement/js-implementation/accelerated-mobile-pages.md#section_4D8ED26084F249738A5C2BC66B933A07)
* [Questions fréquentes](../../implement/js-implementation/accelerated-mobile-pages.md#section_5F57AA2DE0C5452FB65241058A924C73)

**Documentation et exemples supplémentaires**

* [Documentation](https://www.ampproject.org/docs/get_started/about-amp.html) du projet AMP Open Source externe
* [Exemples](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web/amphtml) de configuration

## Fonctionnement {#section_21C2836D63104794BCEBEECB6593AFBF}

Les projets AMP contiennent des pages HTML spécialement balisées mises en mémoire cache autour du web sur différents réseaux de diffusion de contenu d’éditeurs et de technologies partenaires participants. Ce faisant, le contenu AMP est diffusé depuis la source la plus proche possible avec la latence la plus faible possible. Ceci rend l’analyse plus complexe, car vous ne pouvez jamais être entièrement sûr d’où sera chargé le contenu d’un éditeur, tandis que les cookies tiers peuvent gêner l’identification des visiteurs.

En outre, afin de réduire considérablement le poids de la page et accélérer son temps de chargement, les projets AMP limitent le recours au code JavaScript et aux cookies. Cela est avantageux sur les appareils mobiles, puisque le temps de traitement est réduit. Toutefois, il devient alors plus difficile de mesurer précisément les visiteurs uniques et de comprendre l’acquisition et la rétention des utilisateurs.

Afin de résoudre ces problèmes, Adobe a collaboré avec les partenaires et les éditeurs AMP sur deux options parmi lesquelles un éditeur peut choisir en fonction de ses besoins professionnels. Ces deux options utilisent la balise `amp-analytics`. The first approach uses the `"adobeanalytics"` tracking template to construct the Analytics request directly from within the AMP. The second approach uses the `"analytics_nativeConfig"` tracking template, which uses an iframe containing the AppMeasurement code you deploy on your normal site. Le tableau suivant présente les avantages et les aléas de chaque méthode.

|  | **modèle "adobeanalytics"** | ** Modèle adobeanalytics_ nativeconfig** |
|---|---|---|
| Nombre de visiteurs/visites (dans la suite de rapports existante) | Gonflement élevé | Gonflement minimal |
| Utilisation d’une suite de rapports distincte | Recommandée | Pas nécessaire |
| Visiteurs nouveaux/récurrents | Non pris en charge | Pris en charge |
| Service d’identification des visiteurs | Non pris en charge | Pris en charge |
| Suivi des vidéos et des liens | Prise en charge partielle | Pas encore pris en charge |
| Difficulté de mise en œuvre | Parfois difficile | Relativement facile |
| [!DNL Experience Cloud] intégrations | Non pris en charge | Pris en charge avec des mises en garde |

## Utilisation de la balise amp-analytics avec le modèle "adobeanalytics" {#section_2E4EBF4EF623440D95DE98E78C47244E}

The `"adobeanalytics"`tracking template utilizes the `amp-analytics` tag to construct a tracking request directly. Using the `"adobeanalytics"` template in the `amp-analytics` tag, you can specify hit requests that fire on specific page events, like the page becoming visible or on a click (and in the future, video views and more). Les événements de clic peuvent être personnalisés afin de s’appliquer à certains identifiants ou classes d’élément en spécifiant un sélecteur. Adobe has made this easy to set up using the `"adobeanalytics"` template specifically designed for [!DNL Adobe Analytics]. You can load the template by adding `type="adobeanalytics"` to the amp-analytics tag.

Dans l’exemple de code suivant, deux déclencheurs sont définis : `pageLoad` et `click`. `pageLoad` Le déclencheur se déclenche lorsque le document devient visible et inclut `pageName` la variable comme défini dans `vars section`la section. Le second déclencheur, `click`, se déclenche lors d’un clic sur un bouton. `eVar 1` est définie pour cet événement avec la valeur `button clicked`.

```
  <amp-analytics type="adobeanalytics"> 
  <script type="application/json"> 
  { 
        "requests": { 
      "myClick": "${click}&v1=${eVar1}", 
  }, 
  "vars": { 
      "host": "metrics.example.com", 
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

Dans le déclencheur `click`, vous pouvez spécifier un sélecteur afin de vous assurer qu’à chaque clic sur un élément DOM spécifique (dans ce cas, un bouton), la demande `buttonClick` est déclenchée et automatiquement définie pour consigner cet accès comme événement hors scène (par ex. un appel `trackLink`).

En outre, `amp-analytics` prend en charge un certain nombre de substitutions de variables de sorte que le projet AMP puisse fournir des valeurs de données qu’il connaît. Pour en apprendre davantage à ce sujet et plus encore, consultez la [documentation sur les variables amp-analytics](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md).

Si vous souhaitez incorporer des variables DOM ou d’une technologie particulière (navigateur, taille de l’écran, appareil, référent, etc.), vous devez les ajouter explicitement à une demande, puisqu’elles ne sont pas générées automatiquement. Vous trouverez [ici](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=query_parameters) une documentation sur chacun de nos paramètres de chaîne de requête disponibles utilisés pour le suivi.

En observant les accès créés par amp-analytics, vous remarquerez que dans chaque demande, Adobe a inclus le paramètre de requête `vid`. We set the `vid` based on a built-in AMP function to set a custom Analytics cookie ID named `adobe_amp_id`. This ID is independent of any other ID being set by [!DNL Adobe Analytics] elsewhere (e.g. `s_vi cookie`) and creates new visitors in any report suite the hits are sent to.

Voici toutefois quelques mises en garde à prendre en compte : Lorsque la balise amp-analytics est utilisée comme stipulé ci-dessus, les visiteurs ne dépendent pas de votre suivi régulier ; puisque l’AMP peut être chargée depuis n’importe quel réseau de diffusion de contenu, vous obtenez un visiteur unique pour chaque réseau de diffusion de contenu sur lequel un visiteur voit cette AMP (en raison du gonflement des visiteurs susmentionné). For this reason, Adobe recommends that if you use the `"adobeanalytics"` template for `amp-analytics`, you put your data into a separate report suite specific to AMP. Also, the [!DNL Experience Cloud] ID service (formerly, *`visitor ID service`*) is not supported using this method, so if your business requires additional [!DNL Experience Cloud] integrations, or will in the future, this is probably not the option for you.

Enfin, et peut-être surtout, cette solution `amp-analytics` nécessite que le serveur de suivi que vous spécifiez dans la section `vars` corresponde au serveur de suivi sur votre site principal, de sorte que vos contrôles de politique de confidentialité en place soient respectés. Sinon, vous devez créer une politique de confidentialité distincte propre aux AMP.

## Utilisation de la balise amp-analytics avec le modèle « adobeanalytics_nativeConfig » {#section_3556B68304A4492991F439885727E9FF}

`"adobeanalytics_nativeConfig"` La balise est plus facile à implémenter, car elle utilisera la même méthodologie de balisage que celle que vous utilisez sur vos pages Web normales. Pour y parvenir, ajoutez le code suivant à la balise `amp-analytics` :

```
<amp-analytics type="adobeanalytics_nativeConfig"> 
 <script type="application/json"> 
 { 
  "requests": { 
   "base": "https://${host}", 
   "iframeMessage": "${base}/stats.html?campaign=${queryParam(campaign)}&pageURL=${ampdocUrl}&ref=${documentReferrer}" 
  }, 
  "vars": { 
   "host": "statshost.publishersite.com" 
  }, 
  "extraUrlParams": { 
   "pageName": "Adobe Analytics Using amp-analytics tag", 
   "v1": "eVar1 test value" 
  } 
 } 
 </script> 
</amp-analytics>  
```

Cette méthode envoie des données à une page web utilitaire au moyen de paramètres spéciaux de chaîne de requête ajoutés au paramètre de demande `iframeMessage`. Dans ce cas, vous pouvez observer que nous avons ajouté la variable `ampdocUrl AMP` et le référent `documentReferrer` aux paramètres de chaîne de requête `pageURL`, en renvoyant respectivement à la demande `iframeMessage` ci-dessus. Vous pouvez nommer comme bon vous semble ces paramètres de chaîne de requête supplémentaires, à condition que la page [!DNL stats.html] (comme illustré ci-dessous) soit configurée pour collecter les données appropriées depuis ces paramètres.

The `"adobeanalytics_nativeConfig"` template also adds query string parameters based on the variables listed in the `extraUrlParams` section of the amp-analytics tag. Dans ce cas, vous pouvez observer que nous avons spécifié les paramètres `pageName` et `v1`, qui seront utilisés par notre page [!DNL stats.html].

Be aware that you can only use a single `amp-analytics` template at a time and can not use the `"adobeanalytics"` template as well as the `"adobeanalytics_nativeConfig"` template on the same AMP. Sinon, une erreur risque de s’afficher dans la console du navigateur et le nombre des visiteurs sera gonflé.

```
<html> 
<head> 
<title>Stats Test</title> 
<script language="JavaScript" type="text/javascript" src="VisitorAPI.js"></script> 
<script language="JavaScript" type="text/javascript" src="AppMeasurement.js"></script> 
<html> 
<head> 
<title>Stats Test</title> 
<script language="JavaScript" type="text/javascript" src="VisitorAPI.js"></script> 
<script language="JavaScript" type="text/javascript" src="AppMeasurement.js"></script> 
</head> 
<body> 
<script> 
var v_orgId = "1234567@PublisherOrg"; 
var s_account = "reportSuite"; 
var s_trackingServer = "metrics.publisher.com"; 
var s_visitorNamespace = "publisherNamespace"; 
var visitor = Visitor.getInstance(v_orgId); 
visitor.trackingServer = s_trackingServer; 
var s = s_gi(s_account); 
s.account = s_account; 
s.trackingServer = s_trackingServer; 
s.visitorNamespace = s_visitorNamespace; 
s.visitor = visitor; 
s.pagename = s.Util.getQueryParam("pageName"); 
s.eVar1=s.Util.getQueryParam("v1"); 
s.campaign=s.Util.getQueryParam("campaign"); 
s.pageURL=s.Util.getQueryParam("pageURL"); 
s.referrer=s.Util.getQueryParam(“ref”); 
s.t(); 
</script> 
</body> 
</html> 
```

Comme illustré ci-dessus, vous pouvez utiliser ou lier le modèle à vos fichiers [!DNL VisitorAPI.js] et [!DNL AppMeasurement.js] existants (comme dans notre exemple), ou à n’importe quel fichier utilisé par votre mise en œuvre existante, puis ajouter les paramètres de configuration corrects. Pour capturer les valeurs correctes dans les variables correctes, utilisez la fonction `s.Util.getQueryParam` fournie pour saisir les valeurs que vous avez transmises à partir de l’URL `iframeMessage`, puis définissez les variables appropriées, comme vous le feriez sur une page type. If you use tag management software like Adobe's [ [!DNL Dynamic Tag Manager] ](https://www.adobe.com/solutions/digital-marketing/dynamic-tag-management.html), the query string parameters should be straightforward to capture. Dans ce cas, `s.pageName` est paramétré sur la valeur transmise dans le paramètre de la chaîne de requête `pageName`. Ici, le nom de la page doit être défini sur *`Adobe Analytics Example 2`*.

>[!IMPORTANT]
>
>Due to restrictions on iframes in the AMP framework, your [!DNL stats.html] page must be hosted on a separate subdomain from the domain the AMP itself is hosted on. L’infrastructure AMP n’autorise pas les iframes issues du même sous-domaine que celui où existe la page AMP même. Si, par exemple, votre AMP est hébergée sur [!DNL amp.example.com], veillez à héberger la page [!DNL stats.html] sur un sous-domaine distinct tel que [!DNL ampmetrics.example.com] ou autre sous-domaine du même type.

Puisque la page utilitaire est hébergée sur votre site d’origine, la prise en charge de votre politique de confidentialité existante à l’échelle de toutes les AMP ne nécessite aucune autre intervention. Ainsi, si un utilisateur se désabonne du suivi sur votre site principal, il est également désabonné du suivi sur toutes les AMP, sans aucune autre intervention de votre part. Le recours à cette page utilitaire signifie également qu’AMP peut prendre en charge le service [!DNL Experience Cloud] ID d’Adobe afin que vous puissiez intégrer la mesure capturée sur vos AMP au reste d’[!DNL Experience Cloud] (pour la publicité ciblée à l’aide d’[!DNL Adobe Audience Manager], par exemple).

To reiterate, if your organization is not yet using the [!DNL Experience Cloud] ID service (or has tag management software like Adobe's [!DNL Dynamic Tag Manager]), you can tag the [!DNL stats.html] page however you want. Utilisez votre mise en œuvre existante comme point de référence. La seule différence par rapport à votre mise en œuvre standard réside dans le fait que vous obtiendrez les points de données applicables depuis l’URL `iframeMessage` amp-analytics (ou [!DNL document.URL] depuis la page [!DNL stats.html]) pour chacune des variables que vous souhaitez définir. De même, si vous souhaitez utiliser des [variables spécifiques à AMP](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md) (comme mentionné ci-dessus) comme référent AMP ou URL de page AMP, incluez-les dans l’objet iframeMessage comme illustré dans notre exemple ci-dessus.

Cette solution s’accompagne de quelques mises en garde, aussi pratique soit-elle. En raison des restrictions inhérentes dans l’  `amp-analytics``iframeMessage`, elle peut être chargée en un chargement de page une fois seulement. This means you will not be able to do link tracking or video tracking with the `"adobeanalytics_nativeConfig"` template. Moreover, some DOM values that are typically captured automatically by our [!DNL AppMeasurement] code, such as `referrer` (which impacts the Search Engine Keyword reports, Referrer, and Referrer Type reports, or may include a marketing campaign tracking code) will have to be passed manually to the `iframeMessage` using whatever AMP variables [are available](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md). Pour cette raison, Adobe recommande de définir une variable personnalisée avec la valeur AMP si vous placez les données AMP dans une suite de rapports existante, de sorte que vous puissiez segmenter le trafic AMP lors de l’affichage des rapports susmentionnés. Ceci étant dit, les rapports des technologies standard (navigateur, appareil, taille d’écran ou résolution) fonctionnent normalement automatiquement.

Enfin, puisque l’iframe se charge comme une page distincte et exécute entièrement le code JavaScript sur cette page, l’AMP n’est pas aussi légère qu’elle le devrait selon la norme AMP. En réalité, ceci n’a aucune incidence sur le temps de chargement de la page (l’iframe se charge une fois la page entièrement chargée) mais l’UC et le réseau sont davantage mobilisés qu’ils ne le sont habituellement, ce qui peut avoir une incidence sur la fluidité du défilement. En pratique, nous n’avons pas constaté de répercussions significatives, mais nous collaborons actuellement avec Google pour réduire l’impact de cette méthode sur l’utilisateur.

## Résumé {#section_4D8ED26084F249738A5C2BC66B933A07}

If you need click tracking and don't mind visitors being counted as entirely new visitors separate from your site, use the `"adobeanalytics"` tracking template, with our recommendation that you put the data into a *`separate report suite`*. If you need the [!DNL Experience Cloud] ID service, do not want visitor or visit inflation, and are okay with only firing Analytics on page load, we recommend using the `"adobeanalytics_nativeConfig"` solution.

Adobe Analytics est ravie de collaborer avec Google et nos éditeurs afin de proposer aux éditeurs des capacités d’analyse de pointe sur le web mobile, dans un environnement utilisateur étonnamment rapide. Même si ces solutions s’accompagnent actuellement de quelques compromis, nous nous efforçons de créer une solution à long terme de pointe afin de répondre à l’évolution des besoins d’analyse de nos clients.

Le projet AMP évolue rapidement et fréquemment. Revenez fréquemment [ici](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web/amphtml) pour y trouver des mises à jour de nos exemples. Ce que nous vous avons présenté ici devrait suffire à vous aider à commencer, mais attendez-vous à des changements tandis que nous perfectionnons nos intégrations et que les éditeurs adoptent la norme AMP au fil du temps.

Si vous avez des questions ou des problèmes, consultez votre conseiller ou l’assistance clientèle Adobe.

## Questions fréquentes {#section_5F57AA2DE0C5452FB65241058A924C73}

<table id="table_9A2ED5E482E8423CB54F99613C04BEA0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Réponse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Le suivi vidéo est-il disponible pour le modèle <code>"adobeanalytics"</code> ou <code>"adobeanalytics_nativeConfig"</code> ? </p> </td> 
   <td colname="col2"> <p> Pas encore, malheureusement. La norme AMP prend seulement en charge les déclencheurs « visible », « click » et « timer », mais pas encore les déclencheurs explicites pour le suivi vidéo qui peuvent être écoutés par la balise amp-analytics. Par ailleurs, puisque la balise <code>"adobeanalytics_nativeConfig"</code> peut être chargée une seule fois, elle n’est pas compatible avec l’affichage vidéo qui survient après le chargement de la page AMP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dans votre comparaison, vous mentionnez que le gonflement des visiteurs est inférieur pour le modèle <code>"adobeanalytics_nativeConfig"</code>. Qu’est-ce que cela signifie ? Quelle serait la cause du gonflement des visiteurs dans la solution <code>"adobeanalytics"</code> ou <code>"adobeanalytics_nativeConfig"</code> ? </p> </td> 
   <td colname="col2"> <p>Le modèle <code>"adobeanalytics"</code> ne permet pas à Adobe Analytics de définir un cookie d’identification des visiteurs ; ce qui signifie que toutes les visites et tous les visiteurs de votre page AMP sont traités comme des visites et des visiteurs nouveaux et indépendants dans votre suite de rapports. </p> <p>En revanche, le modèle <code>"adobeanalytics_nativeConfig"</code> permet de définir le cookie d’identification des visiteurs Adobe Analytics dans presque tous les cas, hormis pour les nouveaux visiteurs utilisant le navigateur Safari. Cela signifie que tout visiteur sur Safari qui n’avait jamais visité le site d’un éditeur sera exagéré dans les rapports Adobe Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dois-je utiliser une suite de rapports distincte pour les AMP ? </p> </td> 
   <td colname="col2"> <p>Si vous utilisez le modèle adobeanalytics, nous vous recommandons d’utiliser une suite de rapports distincte pour les AMP en raison du problème de gonflement du nombre de visiteurs/visites. Toutefois, nous définirons également la version JavaScript sur « AMP vX.X » depuis le modèle de balise amp-analytics afin que vous puissiez segmenter ce trafic à partir d’une suite de rapports combinée si nécessaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Qu’est-ce que le service <span class="keyword">Experience Cloud</span> ID ? Est-ce que j’en ai besoin ? </p> </td> 
   <td colname="col2"> <p>The <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Identity Service </a> (formerly <span class="term"> visitor ID service </span>) enables <span class="keyword"> Experience Cloud </span> core services and allows integrations between different Adobe <span class="keyword"> Experience Cloud </span> solutions. Si vous avez des intégrations avec <span class="keyword">Adobe Audience Manager</span> ou <span class="keyword">Adobe Target</span>, vous allez probablement utiliser ce service. Ce service est également le fondement de nombreuses fonctions <span class="keyword">Adobe Analytics</span> à venir. Si vous avez besoin de la prise en charge du service d’identification maintenant ou à l’avenir, nous vous recommander d’utiliser la solution <code>iframeMessage</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dans le cas du modèle <code>"adobeanalytics_nativeConfig"</code>, où dois-je héberger ma page utilitaire ? </p> </td> 
   <td colname="col2"> <p>La norme AMP n’autorise pas le chargement des iframes depuis les mêmes domaine et sous-domaine que le site AMP. C’est pourquoi nous vous recommandons d’héberger la page utilitaire sur un sous-domaine distinct depuis votre site principal, en particulier si votre entreprise possède son propre réseau de diffusion de contenu qui prévoit la mise en mémoire cache des pages AMP. Pour bénéficier d’une compatibilité maximale, choisissez un sous-domaine du type <span class="filepath">ampmetrics.publisher.com</span> distinct de l’emplacement où réside le contenu AMP réel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Est-ce que ça n’est pas similaire aux <span class="keyword">Instant Articles de Facebook</span> ? Comment configurer <span class="keyword">Adobe Analytics</span> avec les Instant Articles de Facebook ? </p> </td> 
   <td colname="col2"> <p> Les Instant Articles de Facebook prennent en charge une solution semblable à la solution nativeConfig décrite ci-dessus. En fait, la page stats.html créée ci-dessus peut servir vos besoins d’analyse simultanément pour les pages AMP et les Instant Articles de Facebook. Pour en savoir plus sur la mise en œuvre du suivi pour les Instant Articles de Facebook, voir <a href="../../implement/js-implementation/analytics-facebook-instant-articles.md#concept_AC9AD1431CD14F919E329A161A80AA08" format="dita" scope="local"> Instant Articles de Facebook </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

