---
description: Cette fonction dirige le navigateur vers un nouvel emplacement sans intervention de l’utilisateur. Ces redirections ont lieu au niveau du navigateur (renvoi côté client) ou au niveau du serveur Web (renvoi côté serveur).
keywords: Analytics Implementation
subtopic: Redirects
title: Redirections et alias
topic: Developer and implementation
uuid: 11f9ad7a-5c45-410f-86dd-b7d2cec2aae3
translation-type: tm+mt
source-git-commit: dfe8409b13fcf67eae6a0c404f83c1209f89ae12

---


# Redirections et alias

Cette fonction dirige le navigateur vers un nouvel emplacement sans intervention de l’utilisateur. Ces redirections ont lieu au niveau du navigateur (renvoi côté client) ou au niveau du serveur Web (renvoi côté serveur).

## Redirections et alias {#concept_F4F1D53D473947FE8554897332545763}

Cette fonction dirige le navigateur vers un nouvel emplacement sans intervention de l’utilisateur. Ces redirections ont lieu au niveau du navigateur (renvoi côté client) ou au niveau du serveur Web (renvoi côté serveur).

L’intervention de l’utilisateur n’étant pas requise, les redirections ont souvent lieu sans même que l’utilisateur s’en rende compte. La barre d’adresse du navigateur est le seul indice indiquant qu’une redirection a eu lieu. La barre d’adresse affiche une URL différente du lien initialement demandé par le navigateur.

Il existe uniquement deux types de redirection, mais elles peuvent être implémentées de diverses façons. Par exemple, les redirections côté client peuvent avoir lieu si la page Web vers laquelle un utilisateur a pointé son navigateur contient un script ou un code HTML spécial qui redirige le navigateur vers une autre URL. Les redirections côté serveur surviennent quand la page contient un script côté serveur ou parce que le serveur Web a été configuré pour pointer l’utilisateur vers une autre URL.

## Analytics et redirections {#concept_F9132879D0CB4AC1BE7AF45E388A47F7}

[!DNL Analytics] rassemble certaines de ses données du navigateur et repose sur certaines propriétés du navigateur. Deux de ces propriétés, l’« URL de référence » (ou « référent ») et l’« URL active » peuvent être modifiées par une redirection côté serveur. Le navigateur sait qu’une URL a été demandée, mais qu’une autre URL a été renvoyée et il efface donc l’URL de référence. En conséquence, l’URL de référence est vide et [!DNL Analytics] peut signaler qu’il n’existe aucun référent pour la page.

## Exemple : navigation sans redirection {#section_5C835A4D665A4625A23333C2C21F152D}

Prenons l’hypothèse suivante, selon laquelle aucune redirection ne se présente à l’utilisateur :

1. L’utilisateur pointe son navigateur vers `www.google.com` et saisit « billets d’avion réduits » (discount airline tickets) dans le champ de recherche, puis clique sur le bouton **[!UICONTROL Recherche]**.
1. Le navigateur affiche les résultats de la recherche, notamment un lien vers votre site [!DNL https://www.example.com/]. Après avoir affiché les résultats de la recherche, la barre d’adresse du navigateur affiche les termes recherchés entrés par l’utilisateur dans le champ de recherche ( `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`). Notez que les termes recherchés sont inclus dans les paramètres de la chaîne de requête de l’URL qui suit `https://www.google.com/search?`.
1. L’utilisateur clique sur le lien vers votre site hypothétique [!DNL https://www.example.com/]. Lorsque l’utilisateur clique sur ce lien et arrive sur le site web [!DNL example.com], [!DNL Analytics] utilise JavaScript pour collecter l’URL de référence (`https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`) ainsi que l’URL active (`https://www.example.com/`).
1. [!DNL Analytics] rapporte les informations collectées durant cette interaction dans divers rapports, tels que [!UICONTROL Domaines référents], [!UICONTROL Moteurs de recherche] et [!DNL Search Keywords].

## Exemple : navigation avec redirections {#section_921DDD32932847848C4A901ACEF06248}

En raison des redirections, le navigateur peut masquer la véritable URL de référence. Prenons l’exemple suivant :

1. L’utilisateur pointe son navigateur vers `https://www.google.com` et saisit *billets d’avion réduits* (discount airline tickets) dans le champ de recherche, puis clique sur le bouton **[!UICONTROL Recherche]**.
1. La barre d’adresse du navigateur affiche les termes recherchés entrés par l’utilisateur dans le champ de recherche `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`. Notez que les termes recherchés sont inclus dans les paramètres de la chaîne de requête de l’URL qui suit `https://www.google.com/search?`. Le navigateur affiche également une page qui contient les résultats de recherche, y compris un lien vers l’un de vos noms de domaine : [!DNL https://www.flytohawaiiforfree.com/]. Ce domaine *de redirection vers un microsite* est configuré pour rediriger l’utilisateur vers `https://www.example.com/`.
1. L’utilisateur clique sur le lien `https://www.flytohawaiiforfree.com/` et est redirigé par le serveur vers votre site principal, `https://www.example.com`. Au moment de la redirection, les données importantes pour la collecte de données [!DNL Analytics] sont perdues puisque le navigateur efface l’URL de référence. En conséquence, les informations de la recherche d’origine utilisées dans les rapports [!DNL Analytics] (par exemple, [!UICONTROL Domaines référents], [!UICONTROL Moteurs de recherche], [!UICONTROL Mots-clés de la recherche]) sont perdues.

## Implémentation des redirections {#concept_5EC2EE9677A44CC5B90A38ECF28152E7}

Afin de capturer les données [!DNL Analytics][!DNL AppMeasurement] issues de redirections, quatre modifications mineures doivent être apportées au code qui crée la redirection et au fichier pour JavaScript.

<!-- 

redirects_implement.xml

 -->

Suivez la procédure suivante pour conserver les informations que le référent original (par exemple, `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets` dans le scénario ci-dessus) transmet à votre site :

## Configuration du code JavaScript de remplacement du référent {#section_87BB1D47D9C345C18339078824645CC4}

<!-- 

redirects_js_override.xml

 -->

Le fragment de code ci-dessous présente deux variables JavaScript, *`s_referrer`*et*`s_pageURL`*. Ce code est placé sur la page d’entrée finale de la redirection.

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
>Définissez *`s.referrer`*une seule fois sur la page. Sinon, chaque appel de suivi ou chaque clic sur un lien suivi dupliquera la comptabilisation du référent et des dimensions associées, tels les moteurs de recherche et les mots-clés.

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

## Modification du mécanisme de redirection {#section_2FF9921E8FCA4440B6FF90F15386E548}

<!-- 

redirects_modify_mechanism.xml

 -->

Le navigateur dépouille l’URL de référence ; vous devez donc configurer le mécanisme qui gère la redirection (par exemple, le serveur Web, le code côté serveur, le code côté client) afin de transmettre les informations du référent original. Si vous souhaitez enregistrer l’URL du lien alias, ceci doit également être transmis à la page d’entrée finale. Utilisez la variable *`s_pageURL`*pour remplacer l’URL active.

Il existe de nombreuses façons de mettre en œuvre une redirection. Identifiez avec votre groupe d’opérations Web ou votre partenaire de publicité en ligne les mécanismes spécifiques qui exécutent les redirections sur votre site Web.

## Capture du référent original {#section_7F1A77F447CF485385B456A64B174050}

<!-- 

redirects_referrer.xml

 -->

En règle générale, [!DNL Analytics] obtient l’URL de référence auprès de la propriété [!UICONTROL document.referrer] du navigateur et l’URL active auprès de la propriété [!UICONTROL document.location]. En transmettant des valeurs aux variables *`referrer`*et*`pageURL`*, vous pouvez remplacer le traitement par défaut. En transmettant une valeur à la variable du référent, vous indiquez à [!DNL Analytics] d’ignorer l’information du référent dans la propriété [!UICONTROL document.referrer] et d’utiliser plutôt une autre valeur que vous définissez.

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

## Vérification du référent à l’aide de l’Adobe Debugger {#section_B3E85941982E4E1698B271375AD669B9}

<!-- 

redirects_verify_referrer.xml

 -->

Exécutez un test afin de vérifier que le référent, l’URL d’origine (*`s_server`*) et les variables de campagne sont capturés.

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
   <td> <p> <span class="filepath"> https://www.google.com/search%3F hl%3Den %26ie%3DUTF826q%3 Ddiscount%2Bairline%2Btickets </span> </p> </td> 
   <td> <p> <span class="filepath"> r=https:/ref=www.google.com/search?hl=en&amp;ie=UTF -8&amp;q=discount+airline+tickets </span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>URL de la page </p> </td> 
   <td> <p> <span class="filepath"> https://www.flytohawaiiforfree.com </span> </p> </td> 
   <td> <p> <span class="filepath"> g=https://www.flytohawaiiforfree.com </span> </p> <p>Cette valeur apparaît dans le débogueur DigitalPulse si la variable <span class="varname"> pageURL </span> est utilisée. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>URL de page d’entrée finale </p> </td> 
   <td> <p> <span class="filepath"> https://www.example.com </span> </p> </td> 
   <td> <p>Cette valeur n’apparaît PAS dans le débogueur DigitalPulse si la variable <span class="varname"> pageURL </span> est utilisée. </p> </td> 
  </tr> 
 </tbody> 
</table>

Le texte affiché par le débogueur correspond normalement à l’exemple suivant :

```
Image 
 
https://examplecom.112.2o7.net/b/ss/examplecom/1/JS-1.4/s61944015791667?[AQB] 
ndh=1 
t=4/8/2014 13:34:28 4 360 
pageName=Welcome to example.com 
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

Après avoir vérifié que l’Adobe [!UICONTROL Debugger] affiche ces variables, il s’avère toujours utile de confirmer que les termes recherchés et le domaine référent d’origine (avant la redirection) enregistrent le trafic dans les rapports.
