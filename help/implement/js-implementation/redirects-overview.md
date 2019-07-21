---
description: Cette fonction dirige le navigateur vers un nouvel emplacement sans intervention de l’utilisateur. Ces redirections ont lieu au niveau du navigateur (renvoi côté client) ou au niveau du serveur Web (renvoi côté serveur).
keywords: Mise en œuvre d’Analytics
seo-description: Cette fonction dirige le navigateur vers un nouvel emplacement sans intervention de l’utilisateur. Ces redirections ont lieu au niveau du navigateur (renvoi côté client) ou au niveau du serveur Web (renvoi côté serveur).
seo-title: Redirections et alias
solution: Analytics
subtopic: Redirections
title: Redirections et alias
topic: Développeur et mise en œuvre
uuid: 11 f 9 ad 7 a -5 c 45-410 f -86 dd-b 7 d 2 cec 2 aae 3
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Redirections et alias

Cette fonction dirige le navigateur vers un nouvel emplacement sans intervention de l’utilisateur. Ces redirections ont lieu au niveau du navigateur (renvoi côté client) ou au niveau du serveur Web (renvoi côté serveur).

## Redirects and aliases {#concept_F4F1D53D473947FE8554897332545763}

Cette fonction dirige le navigateur vers un nouvel emplacement sans intervention de l’utilisateur. Ces redirections ont lieu au niveau du navigateur (renvoi côté client) ou au niveau du serveur Web (renvoi côté serveur).

L’intervention de l’utilisateur n’étant pas requise, les redirections ont souvent lieu sans même que l’utilisateur s’en rende compte. La barre d’adresse du navigateur est le seul indice indiquant qu’une redirection a eu lieu. La barre d’adresse affiche une URL différente du lien initialement demandé par le navigateur.

Il existe uniquement deux types de redirection, mais elles peuvent être implémentées de diverses façons. Par exemple, les redirections côté client peuvent avoir lieu si la page Web vers laquelle un utilisateur a pointé son navigateur contient un script ou un code HTML spécial qui redirige le navigateur vers une autre URL. Les redirections côté serveur surviennent quand la page contient un script côté serveur ou parce que le serveur Web a été configuré pour pointer l’utilisateur vers une autre URL.

## Analytics and redirects {#concept_F9132879D0CB4AC1BE7AF45E388A47F7}

[!DNL Analytics] rassemble certaines de ses données du navigateur et repose sur certaines propriétés du navigateur. Deux de ces propriétés, l’« URL de référence » (ou « référent ») et l’« URL active » peuvent être modifiées par une redirection côté serveur. Le navigateur sait qu’une URL a été demandée, mais qu’une autre URL a été renvoyée et il efface donc l’URL de référence. En conséquence, l’URL de référence est vide et [!DNL Analytics] peut signaler qu’il n’existe aucun référent pour la page.

<!-- 

redirects_sc.xml

 -->

Les exemples suivants illustrent la façon dont la navigation est affectée sans ou avec des redirections :

* [Exemple : navigation sans redirection](../../implement/js-implementation/redirects-overview.md#section_5C835A4D665A4625A23333C2C21F152D)
* [Exemple : navigation avec redirections](../../implement/js-implementation/redirects-overview.md#section_921DDD32932847848C4A901ACEF06248)

## Exemple : navigation sans redirection {#section_5C835A4D665A4625A23333C2C21F152D}

Prenons l’hypothèse suivante, selon laquelle aucune redirection ne se présente à l’utilisateur :

1. L’utilisateur pointe son navigateur vers `www.google.com`**et saisit « billets d’avion réduits » (discount airline tickets) dans le champ de recherche, puis clique sur le bouton[!UICONTROL Recherche].**
1. Le navigateur affiche les résultats de la recherche, notamment un lien vers votre site [!DNL https://www.flywithus.com/]. After displaying the search results, the browser's address bar displays the search terms that the user entered in the search field ( `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`). Notez que les termes recherchés sont inclus dans les paramètres de la chaîne de requête de l’URL qui suit `https://www.google.com/search?`.
1. L’utilisateur clique sur le lien vers votre site hypothétique [!DNL https://www.flywithus.com/]. When the user clicks this link and lands on the [!DNL flywithus.com] website, [!DNL Analytics] uses JavaScript to collect the referring URL ( `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`) as well as the current URL ( `https://www.flywithus.com/`).
1. [!DNL Analytics] rapporte les informations collectées durant cette interaction dans divers rapports, tels que Domaines [!UICONTROL référents], [!UICONTROL Moteurs]de recherche et [!DNL Search Keywords].

## Exemple : navigation avec redirections {#section_921DDD32932847848C4A901ACEF06248}

En raison des redirections, le navigateur peut masquer la véritable URL de référence. Prenons l’exemple suivant :

1. User points his or her browser to `https://www.google.com`, and types, *discount airline tickets* into the search field, and then clicks the **[!UICONTROL Search]** button.
1. The browser window's address bar displays the search terms that the user typed into the search field `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`. Notez que les termes recherchés sont inclus dans les paramètres de la chaîne de requête de l’URL qui suit `https://www.google.com/search?`. Le navigateur affiche également une page qui contient les résultats de recherche, y compris un lien vers l’un de vos noms de domaine : [!DNL https://www.flytohawaiiforfree.com/]. Ce domaine *de redirection vers un microsite* est configuré pour rediriger l’utilisateur vers `https://www.flywithus.com/`.
1. The user clicks on the link `https://www.flytohawaiiforfree.com/` and is redirected by the server to your main site, `https://www.flywithus.com`. Au moment de la redirection, les données importantes pour la collecte de données [!DNL Analytics] sont perdues puisque le navigateur efface l’URL de référence. En conséquence, les informations de la recherche d’origine utilisées dans les rapports [!DNL Analytics] (par exemple, [!UICONTROL Domaines référents], [!UICONTROL Moteurs de recherche], [!UICONTROL Mots-clés de la recherche]) sont perdues.

[La section Implémentation de redirections](../../implement/js-implementation/redirects-overview.md#concept_5EC2EE9677A44CC5B90A38ECF28152E7) explique comment tirer profit des variables d’[!DNL Analytics] pour capturer les données perdues lors de la redirection. En particulier, elle explique comment corriger la situation « billets d’avion réduits » décrite ci-avant.

## Implement redirects {#concept_5EC2EE9677A44CC5B90A38ECF28152E7}

Afin de capturer les données [!DNL Analytics][!DNL AppMeasurement] issues de redirections, quatre modifications mineures doivent être apportées au code qui crée la redirection et au fichier  pour JavaScript.

<!-- 

redirects_implement.xml

 -->

Completing the following steps will retain the information that the original referrer (for example, `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets` in the scenario above) passes to your site:

## Configure referrer override JavaScript code {#section_87BB1D47D9C345C18339078824645CC4}

<!-- 

redirects_js_override.xml

 -->

The code snippet below shows two JavaScript variables, *`s_referrer`* and *`s_pageURL`*. Ce code est placé sur la page d’entrée finale de la redirection.

```js
<script language="JavaScript" src="//INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"></script> 
<script language="JavaScript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.campaign="" 
s.referrer="" 
s.pageURL=""
```

>[!IMPORTANT]
>
>Set *`s.referrer`* only once on the page. Sinon, chaque appel de suivi ou chaque clic sur un lien suivi dupliquera la comptabilisation du référent et des dimensions associées, tels les moteurs de recherche et les mots-clés.

## Redirections à l’aide de getQueryParam {#section_EE924E399F7A431C8FC8E8A2BEF84DEC}

[!UICONTROL getQueryParam] représente un moyen facile de renseigner les variables [!DNL Analytics] avec des valeurs de chaîne de requête. Il doit toutefois être implémenté en rapport avec une variable temporaire afin que les référents légitimes ne soient pas remplacés lorsque la chaîne de requête est vide. La meilleure façon d’utiliser [!UICONTROL getQueryParam] consiste à l’utiliser conjointement avec le module externe [!UICONTROL getValue], comme décrit avec le pseudo-code ci-après.

```js
// AppMeasurement 1.x 
var tempVar=s.Util.getQueryParam('origref') 
if(tempVar) 
  s.referrer=tempVar;
```

```js
// H Code 
var tempVar=s.getQueryParam('origref') 
if(tempVar) 
  s.referrer=tempVar;
```

## Modify the redirect mechanism {#section_2FF9921E8FCA4440B6FF90F15386E548}

<!-- 

redirects_modify_mechanism.xml

 -->

Le navigateur dépouille l’URL de référence ; vous devez donc configurer le mécanisme qui gère la redirection (par exemple, le serveur Web, le code côté serveur, le code côté client) afin de transmettre les informations du référent original. Si vous souhaitez enregistrer l’URL du lien alias, ceci doit également être transmis à la page d’entrée finale. Utilisez la variable *`s_pageURL`* pour remplacer l’URL active.

Il existe de nombreuses façons de mettre en œuvre une redirection. Identifiez avec votre groupe d’opérations Web ou votre partenaire de publicité en ligne les mécanismes spécifiques qui exécutent les redirections sur votre site Web.

## Capture the original referrer {#section_7F1A77F447CF485385B456A64B174050}

<!-- 

redirects_referrer.xml

 -->

En règle générale, [!DNL Analytics] obtient l’URL de référence auprès de la propriété [!UICONTROL document.referrer] du navigateur et l’URL active auprès de la propriété [!UICONTROL document.location]. By passing values to the *`referrer`* and *`pageURL`* variables, you can override the default processing. En transmettant une valeur à la variable du référent, vous indiquez à [!DNL Analytics] d’ignorer l’information du référent dans la propriété [!UICONTROL document.referrer] et d’utiliser plutôt une autre valeur que vous définissez.

En conséquence, la version finale de la page d’entrée doit contenir le code suivant pour corriger les problèmes introduits dans le scénario « billets d’avion réduits ».

```js
<script language="JavaScript" src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"></script> 
<script language="JavaScript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.campaign="" 
s.referrer="https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets" 
// Setting the s.pageURL variable is optional. 
s.pageURL="https://www.flytohawaiiforfree.com"
```

## Verify the referrer with the Adobe Debugger {#section_B3E85941982E4E1698B271375AD669B9}

<!-- 

redirects_verify_referrer.xml

 -->

Run a test to verify that the referrer, originating URL ( *`s_server`*) and campaign variables are being captured.

These variables will be represented as the following parameters in the [Experience Cloud Debugger](https://marketing.adobe.com/resources/help/en_US/experience-cloud-debugger/).

<table id="table_5F3B987D4D514CA283F7B9F52EBC2301"> 
 <thead> 
  <tr> 
   <th class="entry"> </th> 
   <th class="entry"> <b>URL ou valeur de chaîne de requête</b> </th> 
   <th class="entry"> <b>Valeur telle qu’affichée dans le DigitalPulse Debugger</b> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>Référent original </p> </td> 
   <td> <p> <span class="filepath"> https://www.google.com/search%3F hl % 3 Den % 26 ie % 3 DUTF 826 q % 3 Ddiscount % 2 Bairline % 2 Btickets </span> </p> </td> 
   <td> <p> <span class="filepath"> r = https:/ref=www.google.com/search?hl=en&amp;ie=UTF -8 &amp; q = discount + airline + tickets </span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>URL de la page </p> </td> 
   <td> <p> <span class="filepath"> https://www.flytohawaiiforfree.com </span> </p> </td> 
   <td> <p> <span class="filepath"> g = https://www.flytohawaiiforfree.com </span> </p> <p>This value will appear in the DigitalPulse Debugger if the <span class="varname"> pageURL </span> variable is used. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>URL de page d’entrée finale </p> </td> 
   <td> <p> <span class="filepath"> https://www.flywithus.com </span> </p> </td> 
   <td> <p>This value will NOT appear in the DigitalPulse Debugger if the <span class="varname"> pageURL </span> variable is used. </p> </td> 
  </tr> 
 </tbody> 
</table>

Le texte affiché par le débogueur correspond normalement à l’exemple suivant :

```
Image 
 
https://flywithuscom.112.2o7.net/b/ss/flywithuscom/1/JS-1.4/s61944015791667?[AQB] 
ndh=1 
t=4/8/2014 13:34:28 4 360 
pageName=Welcome to FlyWithUs.com 
r=https://ref=www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets 
cc=USD 
g=https://www.flytohawaiiforfree.com 
s=1280x1024 
c=32 
j=1.3 
v=Y 
k=Y 
bw=1029 
bh=716 
ct=lan 
hp=N 
[AQE]
```

After verifying that the Adobe [!UICONTROL Debugger] displays these variables, it is always helpful to confirm that the search terms and the original referring domain (prior to the redirect) are registering traffic in reports.
