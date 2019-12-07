---
description: Mettez en œuvre le projet AMP (Accelerated Mobile Pages) dans Adobe Analytics.
keywords: Analytics Implementation;amp;amp-analytics;adobeanalytics template;adobeanalytics_nativeConfig template;click tracking;visitor inflation;id service
title: Accelerated Mobile Pages
topic: Developer and implementation
uuid: c86e4a80-7191-4ee7-ab20-787730026c4b
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Accelerated Mobile Pages

Mettez en œuvre le projet AMP (Accelerated Mobile Pages) dans Adobe Analytics.

Il s’agit d’un [projet Open Source](https://www.ampproject.org/) grâce auquel il est possible de créer des pages web pour du contenu statique restitué plus rapidement. Cette fonction est idéale pour les éditeurs qui souhaitent créer une fois un contenu optimisé pour les appareils mobiles et qui se chargera instantanément partout. Les sujets couverts sont les suivants :

* [Fonctionnement](/help/implement/js-implementation/accelerated-mobile-pages.md#section_21C2836D63104794BCEBEECB6593AFBF)
* [Utilisation de la balise amp-analytics avec le modèle "adobeanalytics"](/help/implement/js-implementation/accelerated-mobile-pages.md#section_2E4EBF4EF623440D95DE98E78C47244E)
* [Utilisation de la balise amp-analytics avec le modèle « adobeanalytics_nativeConfig »](/help/implement/js-implementation/accelerated-mobile-pages.md#section_3556B68304A4492991F439885727E9FF)
* [Résumé](/help/implement/js-implementation/accelerated-mobile-pages.md#section_4D8ED26084F249738A5C2BC66B933A07)
* [Questions fréquentes](/help/implement/js-implementation/accelerated-mobile-pages.md#section_5F57AA2DE0C5452FB65241058A924C73)

**Documentation et exemples supplémentaires**

* [Documentation](https://www.ampproject.org/docs/get_started/about-amp.html) du projet AMP Open Source externe
* [Exemples](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web/amphtml) de configuration

## Fonctionnement {#section_21C2836D63104794BCEBEECB6593AFBF}

Les projets AMP contiennent des pages HTML spécialement balisées mises en mémoire cache autour du web sur différents réseaux de diffusion de contenu d’éditeurs et de technologies partenaires participants. Ce faisant, le contenu AMP est diffusé depuis la source la plus proche possible avec la latence la plus faible possible. Ceci rend l’analyse plus complexe, car vous ne pouvez jamais être entièrement sûr d’où sera chargé le contenu d’un éditeur, tandis que les cookies tiers peuvent gêner l’identification des visiteurs.

En outre, afin de réduire considérablement le poids de la page et accélérer son temps de chargement, les projets AMP limitent le recours au code JavaScript et aux cookies. Cela est avantageux sur les appareils mobiles, puisque le temps de traitement est réduit. Toutefois, il devient alors plus difficile de mesurer précisément les visiteurs uniques et de comprendre l’acquisition et la rétention des utilisateurs.

Afin de résoudre ces problèmes, Adobe a collaboré avec les partenaires et les éditeurs AMP sur deux options parmi lesquelles un éditeur peut choisir en fonction de ses besoins professionnels. Ces deux options utilisent la balise `amp-analytics`. La première méthode consiste à utiliser le modèle de suivi `"adobeanalytics"` afin de construire la demande Analytics directement dans le projet AMP. La seconde méthode consiste à recourir au modèle de suivi `"analytics_nativeConfig"`, qui utilise un iframe contenant le code AppMeasurement que vous déployez sur votre site normal. Le tableau suivant présente les avantages et les aléas de chaque méthode.

|  | **modèle "adobeanalytics"** | **modèle "adobeanalytics_nativeConfig"** |
|---|---|---|
| Nombre de visiteurs/visites (dans la suite de rapports existante) | Gonflement élevé | Gonflement minimal |
| Utilisation d’une suite de rapports distincte | Recommandée | Pas nécessaire |
| Visiteurs nouveaux/récurrents | Non pris en charge | Pris en charge |
| Service d’identification des visiteurs | Non pris en charge | Pris en charge |
| Suivi des vidéos et des liens | Prise en charge partielle | Pas encore pris en charge |
| Difficulté de mise en œuvre | Parfois difficile | Relativement facile |
| [!DNL Experience Cloud] intégrations | Non pris en charge | Pris en charge avec des mises en garde |

## Utilisation de la balise amp-analytics avec le modèle "adobeanalytics" {#section_2E4EBF4EF623440D95DE98E78C47244E}

Le `"adobeanalytics"`modèle de suivi utilise la balise `amp-analytics` afin de construire directement une demande de suivi. En utilisant le modèle `"adobeanalytics"` dans la balise `amp-analytics`, vous pouvez spécifier des demandes d’accès qui se déclenchent lors d’événements de page spécifiques, par exemple si la page devient visible ou en cas de clic (et, à l’avenir, lors d’affichages de vidéos et plus encore). Les événements de clic peuvent être personnalisés afin de s’appliquer à certains identifiants ou classes d’élément en spécifiant un sélecteur. Adobe a simplifié le paramétrage de ces événements en utilisant le modèle `"adobeanalytics"`, spécialement conçu pour [!DNL Adobe Analytics]. Vous pouvez charger le modèle en ajoutant `type="adobeanalytics"` à la balise amp-analytics.

Dans l’exemple de code suivant, deux déclencheurs sont définis : `pageLoad` et `click`. Le déclencheur `pageLoad` se déclenche quand le document devient visible et comprend la variable `pageName`, comme défini dans la `vars section`. Le second déclencheur, `click`, se déclenche lors d’un clic sur un bouton. `eVar 1` est configurée pour cet événement avec la valeur `button clicked`.

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

Si vous souhaitez incorporer des variables DOM ou d’une technologie particulière (navigateur, taille de l’écran, appareil, référent, etc.), vous devez les ajouter explicitement à une demande, puisqu’elles ne sont pas générées automatiquement. Vous trouverez [ici](https://marketing.adobe.com/resources/help/en_US/sc/implement/query_parameters.html) une documentation sur chacun de nos paramètres de chaîne de requête disponibles utilisés pour le suivi.

En observant les accès créés par amp-analytics, vous remarquerez que dans chaque demande, Adobe a inclus le paramètre de requête `vid`. Ce paramètre `vid` est défini en fonction d’une fonction AMP intégrée afin de définir un identifiant de cookie Analytics personnalisé nommé `adobe_amp_id`. Cet identifiant ne dépend d’aucun autre identifiant défini ailleurs par [!DNL Adobe Analytics] (`s_vi cookie`, par exemple) et crée de nouveaux visiteurs dans n’importe quelle suite de rapports à laquelle sont envoyés les accès.

Voici toutefois quelques mises en garde à prendre en compte : Lorsque la balise amp-analytics est utilisée comme stipulé ci-dessus, les visiteurs ne dépendent pas de votre suivi régulier ; puisque l’AMP peut être chargée depuis n’importe quel réseau de diffusion de contenu, vous obtenez un visiteur unique pour chaque réseau de diffusion de contenu sur lequel un visiteur voit cette AMP (en raison du gonflement des visiteurs susmentionné). Pour cette raison, si vous utilisez le modèle `"adobeanalytics"` pour `amp-analytics`, Adobe recommande de placer les données dans une suite de rapports distincte spécifique à l’AMP. En outre, le service d’ID [!DNL Experience Cloud] (anciennement *`visitor ID service`*) n’est pas compatible avec cette méthode. Par conséquent, si d’autres intégrations [!DNL Experience Cloud] sont nécessaires pour votre entreprise ou le seront à l’avenir, cette option ne vous convient probablement pas.

Enfin, et peut-être surtout, cette solution `amp-analytics` nécessite que le serveur de suivi que vous spécifiez dans la section `vars` corresponde au serveur de suivi sur votre site principal, de sorte que vos contrôles de politique de confidentialité en place soient respectés. Sinon, vous devez créer une politique de confidentialité distincte propre aux AMP.

## Utilisation de la balise amp-analytics avec le modèle « adobeanalytics_nativeConfig » {#section_3556B68304A4492991F439885727E9FF}

La balise `"adobeanalytics_nativeConfig"` est plus facile à mettre en œuvre, car vous appliquez la même méthodologie de balisage que celle que vous utilisez sur vos pages web ordinaires. Pour y parvenir, ajoutez le code suivant à la balise `amp-analytics` :

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

Le modèle `"adobeanalytics_nativeConfig"` ajoute également des paramètres de chaîne de requête en fonction des variables répertoriées dans la section `extraUrlParams` de la balise amp-analytics. Dans ce cas, vous pouvez observer que nous avons spécifié les paramètres `pageName` et `v1`, qui seront utilisés par notre page [!DNL stats.html].

Gardez à l’esprit que vous pouvez utiliser un seul modèle `amp-analytics` à la fois et que vous ne pouvez pas utiliser le modèle `"adobeanalytics"` conjointement avec le modèle `"adobeanalytics_nativeConfig"` dans la même AMP. Sinon, une erreur risque de s’afficher dans la console du navigateur et le nombre des visiteurs sera gonflé.

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
s.referrer=s.Util.getQueryParam("ref"); 
s.t(); 
</script> 
</body> 
</html> 
```

Comme illustré ci-dessus, vous pouvez utiliser ou lier le modèle à vos fichiers [!DNL VisitorAPI.js] et [!DNL AppMeasurement.js] existants (comme dans notre exemple), ou à n’importe quel fichier utilisé par votre mise en œuvre existante, puis ajouter les paramètres de configuration corrects. Pour capturer les valeurs correctes dans les variables correctes, utilisez la fonction `s.Util.getQueryParam` fournie pour saisir les valeurs que vous avez transmises à partir de l’URL `iframeMessage`, puis définissez les variables appropriées, comme vous le feriez sur une page type. If you use tag management software like Adobe's [ [!DNL Dynamic Tag Manager] ](https://www.adobe.com/solutions/digital-marketing/dynamic-tag-management.html), the query string parameters should be straightforward to capture. Dans ce cas, `s.pageName` est paramétré sur la valeur transmise dans le paramètre de la chaîne de requête `pageName`. Ici, le nom de la page doit être défini sur *`Adobe Analytics Example 2`*.

>[!IMPORTANT]
>
>En raison de restrictions liées aux iframes dans l’infrastructure AMP, la page [!DNL stats.html] doit être hébergée dans un sous-domaine distinct du domaine où est hébergé l’AMP. L’infrastructure AMP n’autorise pas les iframes issues du même sous-domaine que celui où existe la page AMP même. Si, par exemple, votre AMP est hébergée sur [!DNL amp.example.com], veillez à héberger la page [!DNL stats.html] sur un sous-domaine distinct tel que [!DNL ampmetrics.example.com] ou autre sous-domaine du même type.

Puisque la page utilitaire est hébergée sur votre site d’origine, la prise en charge de votre politique de confidentialité existante à l’échelle de toutes les AMP ne nécessite aucune autre intervention. Ainsi, si un utilisateur se désabonne du suivi sur votre site principal, il est également désabonné du suivi sur toutes les AMP, sans aucune autre intervention de votre part. Le recours à cette page utilitaire signifie également qu’AMP peut prendre en charge le service [!DNL Experience Cloud] ID d’Adobe afin que vous puissiez intégrer la mesure capturée sur vos AMP au reste d’[!DNL Experience Cloud] (pour la publicité ciblée à l’aide d’[!DNL Adobe Audience Manager], par exemple).

En résumé, si votre organisation n’utilise pas encore le service [!DNL Experience Cloud] ID (ou si elle utilise un logiciel de gestion du type [!DNL Dynamic Tag Manager] d’Adobe), vous pouvez baliser la page [!DNL stats.html] à votre gré. Utilisez votre mise en œuvre existante comme point de référence. La seule différence par rapport à votre mise en œuvre standard réside dans le fait que vous obtiendrez les points de données applicables depuis l’URL `iframeMessage` amp-analytics (ou [!DNL document.URL] depuis la page [!DNL stats.html]) pour chacune des variables que vous souhaitez définir. De même, si vous souhaitez utiliser des [variables spécifiques à AMP](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md) (comme mentionné ci-dessus) comme référent AMP ou URL de page AMP, incluez-les dans l’objet iframeMessage comme illustré dans notre exemple ci-dessus.

Cette solution s’accompagne de quelques mises en garde, aussi pratique soit-elle. En raison des restrictions inhérentes dans l’ `amp-analytics` `iframeMessage`, elle peut être chargée en un chargement de page une fois seulement. Ceci signifie que vous ne pourrez pas effectuer de suivi des liens ou des vidéos avec le modèle `"adobeanalytics_nativeConfig"`. En outre, certaines valeurs DOM qui sont généralement capturées automatiquement par notre code [!DNL AppMeasurement], par exemple `referrer` (qui a des répercussions sur les rapports Mot-clé de moteur de recherche, Référent et Type de référent ou qui peuvent inclure un code de suivi de campagne marketing), devront être transmises manuellement à l’`iframeMessage` en utilisant les variables AMP [disponibles](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md). Pour cette raison, Adobe recommande de définir une variable personnalisée avec la valeur AMP si vous placez les données AMP dans une suite de rapports existante, de sorte que vous puissiez segmenter le trafic AMP lors de l’affichage des rapports susmentionnés. Ceci étant dit, les rapports des technologies standard (navigateur, appareil, taille d’écran ou résolution) fonctionnent normalement automatiquement.

Enfin, puisque l’iframe se charge comme une page distincte et exécute entièrement le code JavaScript sur cette page, l’AMP n’est pas aussi légère qu’elle le devrait selon la norme AMP. En réalité, ceci n’a aucune incidence sur le temps de chargement de la page (l’iframe se charge une fois la page entièrement chargée) mais l’UC et le réseau sont davantage mobilisés qu’ils ne le sont habituellement, ce qui peut avoir une incidence sur la fluidité du défilement. En pratique, nous n’avons pas constaté de répercussions significatives, mais nous collaborons actuellement avec Google pour réduire l’impact de cette méthode sur l’utilisateur.

## Résumé {#section_4D8ED26084F249738A5C2BC66B933A07}

Si vous avez besoin d’un suivi des clics et qu’il vous importe peu que les visiteurs soient comptabilisés comme des visiteurs entièrement nouveaux distincts de votre site, utilisez le modèle de suivi `"adobeanalytics"` ; nous vous recommandons aussi de placer les données dans une *`separate report suite`*. Si vous avez besoin du service [!DNL Experience Cloud] ID, que vous souhaitez éviter le gonflement du nombre de visiteurs ou de visites et que vous acceptez de déclencher Analytics seulement au chargement de la page, nous vous recommandons en revanche d’utiliser le modèle `"adobeanalytics_nativeConfig"`.

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
   <td colname="col1"> <p> Is video tracking available for either the <code> "adobeanalytics" </code> or <code> "adobeanalytics_nativeConfig" </code> template? </p> </td> 
   <td colname="col2"> <p> Pas encore, malheureusement. La norme AMP prend seulement en charge les déclencheurs « visible », « click » et « timer », mais pas encore les déclencheurs explicites pour le suivi vidéo qui peuvent être écoutés par la balise amp-analytics. Also, because the <code> "adobeanalytics_nativeConfig" </code> tag can only be loaded once, it is not compatible with video viewing which occurs after the AMP has loaded. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dans votre comparaison, vous mentionnez que le gonflement des visiteurs est inférieur pour le modèle <code> adobeanalytics_nativeConfig </code>". Qu’est-ce que cela signifie ? What would cause visitor inflation in either the <code> "adobeanalytics" </code> or the <code> "adobeanalytics_nativeConfig" </code> solution? </p> </td> 
   <td colname="col2"> <p>The <code> "adobeanalytics" </code> template does not allow Adobe Analytics to set a visitor identification cookie; this means all visits and visitors to your AMP page will be treated as a new and independent visit and visitor in your report suite. </p> <p>The <code> "adobeanalytics_nativeConfig" </code> template, however, allows the Adobe Analytics visitor identification cookie to be set in nearly all cases, except for new visitors using the Safari browser. En d’autres termes, les visiteurs de Safari qui n’ont pas encore visité le site d’un éditeur sont exagérés dans les rapports Adobe Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dois-je utiliser une suite de rapports distincte pour les AMP ? </p> </td> 
   <td colname="col2"> <p>Si vous utilisez le modèle adobeanalytics, nous vous recommandons d’utiliser une suite de rapports distincte pour les AMP en raison du problème de gonflement du nombre de visiteurs/visites. Toutefois, nous définirons également la version JavaScript sur « AMP vX.X » depuis le modèle de balise amp-analytics afin que vous puissiez segmenter ce trafic à partir d’une suite de rapports combinée si nécessaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Qu’est-ce que le service <span class="keyword">Experience Cloud</span> ID ? Est-ce que j’en ai besoin ? </p> </td> 
   <td colname="col2"> <p>Le service d’identité <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/"  > </a> (anciennement <span class="term"> service d’identification des visiteurs </span>) active les services principaux <span class="keyword">Experience Cloud </span> et permet l’intégration entre différentes solutions d’Adobe <span class="keyword"> Experience Cloud </span>. Si vous avez des intégrations avec <span class="keyword">Adobe Audience Manager</span> ou <span class="keyword">Adobe Target</span>, vous allez probablement utiliser ce service. Ce service est également le fondement de nombreuses fonctions <span class="keyword">Adobe Analytics</span> à venir. Si vous avez besoin de la prise en charge du service d’identification maintenant ou à l’avenir, nous vous recommander d’utiliser la solution <code> iframeMessage </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>For the <code> "adobeanalytics_nativeConfig" </code> template, where should I host my utility page? </p> </td> 
   <td colname="col2"> <p>La norme AMP n’autorise pas le chargement des iframes depuis les mêmes domaine et sous-domaine que le site AMP. C’est pourquoi nous vous recommandons d’héberger la page utilitaire sur un sous-domaine distinct depuis votre site principal, en particulier si votre entreprise possède son propre réseau de diffusion de contenu qui prévoit la mise en mémoire cache des pages AMP. Pour bénéficier d’une compatibilité maximale, choisissez un sous-domaine du type <span class="filepath">ampmetrics.publisher.com</span> distinct de l’emplacement où réside le contenu AMP réel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Est-ce que ça n’est pas similaire aux <span class="keyword">Instant Articles de Facebook</span> ? Comment configurer <span class="keyword">Adobe Analytics</span> avec les Instant Articles de Facebook ? </p> </td> 
   <td colname="col2"> <p> Les Instant Articles de Facebook prennent en charge une solution semblable à la solution nativeConfig décrite ci-dessus. En fait, la page stats.html créée ci-dessus peut servir vos besoins d’analyse simultanément pour les pages AMP et les Instant Articles de Facebook. Pour en savoir plus sur la mise en œuvre du suivi pour les Instant Articles de Facebook, voir <a href="/help/implement/js-implementation/analytics-facebook-instant-articles.md"  > Instant Articles de Facebook </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

