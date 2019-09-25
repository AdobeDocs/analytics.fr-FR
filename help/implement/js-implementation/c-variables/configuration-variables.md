---
description: Variables de configuration définies dans AppMeasurement.js.
keywords: Mise en œuvre d’Analytics
seo-description: Configuration variables set in AppMeasurement.js for Adobe Analytics
seo-title: Variables de configuration
solution: Analytics
subtopic: Variables
title: Variables de configuration
topic: Développeur et mise en œuvre
uuid: a19484b6-e350-4c12-b4d6-a31c79a42db0
translation-type: tm+mt
source-git-commit: 755909e0d3c3be60f911fe80acad7baaff248c13

---


# Variables de configuration

Les variables de configuration contrôlent le mode de collecte et de traitement des données dans les rapports. Variables de configuration les plus courantes généralement définies dans le fichier principal (global JavaScript AppMeasurement.js). Ces variables peuvent être définies dans le code de niveau page et les liens Analytics, le cas échéant.

Not all of these variables appear in the code by default when you generate code through the **[!UICONTROL Admin Tool]** &gt; **[!UICONTROL Code Manager]**. Certaines de ces variables de configuration peuvent ne pas s’appliquer aux besoins de mise en œuvre de votre site.

Ces variables de configuration peuvent être utilisées aux fins suivantes :

* Suivi de plusieurs sites/domaines
* Utilisation de n’importe quelle devise pour les achats
* Collecte de données sans tenir compte de la langue
* Suivi des liens (nombre de fichiers téléchargés, liens vers des sites externes)
* Suivi des liens personnalisés à des fins uniques

>[!NOTE]
>
>[!DNL AppMeasurement] requires that all configuration variables are set before the initial call to the track function, `t()`. If configuration variables are set after the call to `t()`, unexpected results may occur. To ensure proper data collection, all configuration variables must be above the `doPlugins` function.


## s.dynamicAccountSelection {#concept_FAD499DB357148DB8BD74F08093D3E35}

La variable vous permet de sélectionner dynamiquement la suite de rapports en fonction de l’URL de chaque page.

>[!NOTE]
>
>`dynamicAccountSelection` ne fonctionne pas avec le suivi personnalisé des liens.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | False |

>[!NOTE]
>
>Both `dynamicAccountList` and `dynamicAccountMatch` are ignored if the `dynamicAccountSelection` variable is not declared or set to 'false.'

**Syntaxe et valeurs possibles** {#section_36E5D0E2170345F5A652B44CE85DFED1}

```js
s.dynamicAccountSelection=[true|false]
```

Only 'true' and 'false' are allowed as values of *`dynamicAccountSelection`*.

**Exemples** {#section_E8CE8BA62C7545889531495E2521663D}

```js
s.dynamicAccountSelection=true
```

```js
s.dynamicAccountSelection=false
```

**Paramètres de configuration** {#section_F052FA38144B4F84B015A263A8E711CF}

Aucune

**Pièges, questions et conseils** {#section_62F0B0895BC84A05840AEEED0643DE60}

* Dynamic account selection is not supported by [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8).
* Utilisez toujours le [!DNL DigitalPulse Debugger] pour déterminer la suite de rapports qui reçoit des données de chaque page.

## s.dynamicAccountList {#concept_19715BA0AD4D41748E0C4A4A6B71AB51}

[!DNL AppMeasurement] pour JavaScript peut sélectionner, de manière dynamique, la suite de rapports à laquelle envoyer les données. La variable contient les règles utilisées pour déterminer la suite de rapports de destination.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | "" |

Cette variable est utilisée conjointement avec les variables *`dynamicAccountSelection`* and *`dynamicAccountMatch`* variables. The rules in  are applied if  is set to 'true,' and they apply to the section of the URL specified in .*`dynamicAccountList`**`dynamicAccountSelection`**`dynamicAccountMatch`*

If none of the rules in  matches the URL of the page, the report suite identified in  is used. *`dynamicAccountList`*`s_account` Les règles répertoriées dans cette variable sont appliquées de gauche à droite. Si l’URL de la page correspond à plusieurs règles, celle qui est située le plus à gauche est utilisée pour déterminer la suite de rapports. Par conséquent, vos règles plus génériques doivent être déplacées vers la droite de la liste.

In the following examples, the page URL is  and  is set to true and  is set to `www.mycompany.com/path1/?prod_id=12345``dynamicAccountSelection`**`s_account``mysuitecom.`

| Valeur DynamicAccountList | Valeur DynamicAccountMatch | Suite de rapports qui recevra les données |
|---|---|---|
| `mysuite2=www2.mycompany.com;mysuite1=mycompany.com` | window.location.host | mysuite1 |
| "mysuite1=path4,path1;mysuite2=path2" | window.location.pathname | mysuite1, mysuite2 |
| "mysuite1=path5" | window.location.pathname | mysuitecom, mysuite1 |
| "myprodsuite=prod_id" | window.location.search?window.location.search:"?") | myprodsuite |

**Syntaxe et valeurs possibles** {#section_7360E4354ED345E8BAAE210DBD58A7EC}

The `dynamicAccountList` variable is a semicolon-separated list of name=value pairs (rules). Chaque entrée de la liste doit contenir les éléments suivants :

* Un ou plusieurs identifiants de suite de rapports (séparés par des virgules)
* Un signe égal (=)
* Un ou plusieurs filtres URL (séparés par des virgules)

```js
s.dynamicAccountList=rs1[,rs2]=domain1.com[,domain2.com/path][;...]
```

La chaîne accepte uniquement les caractères ASCII standard (pas d’espaces).

**Exemples** {#section_49936D14EF6D45859B666C9E7A4CBA9E}

```js
s.dynamicAccountList="mysuite2=www2.mycompany.com;mysuite1=mycompany.com"
```

```js
s.dynamicAccountList="ms1,ms2=site1.com;ms1,ms3=site3.com"
```

**Paramètres de configuration** {#section_9F99CD741BC7449B8CCC108094B2EB85}

Aucune

**Pièges, questions et conseils** {#section_3E10534FCC05457AB67147BB480C8BB3}

* Dynamic account selection is not supported by AppMeasurement for JavaScript.[](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8)
* Si l’URL de la page correspond à plusieurs règles, celle qui est située le plus à gauche est utilisée.
* Si aucune correspondance n’est trouvée, la suite de rapports par défaut est utilisée.
* Si votre page est enregistrée sur le disque dur d’un utilisateur ou traduite au moyen d’un moteur de traduction Web (c’est le cas des pages traduites par Google, par exemple), il y a de fortes chances que la sélection de comptes dynamique ne fonctionne pas. Pour effectuer un suivi plus précis, renseignez la variable `s_account` côté serveur.
* The `dynamicAccountSelection` rules apply only to the section of the URL specified in `dynamicAccountMatch`.

* When using dynamic account selection, be sure to update  every time you obtain a new domain.*`dynamicAccountList`*
* Utilisez le [!DNL DigitalPulse Debugger] pour tenter d’identifier la suite de rapports de destination. The `dynamicAccountSelection` variable always overrides the value of `s_account`.

## s.dynamicAccountMatch {#concept_718171E602214CCC9905C749708BBE52}

La variable utilise l’objet DOM pour récupérer la section de l’URL à laquelle s’appliquent toutes les règles indiquées dans 

This variable is only valid when *`dynamicAccountSelection`* is set to 'True.' Comme la valeur par défaut est [!DNL window.location.host], cette variable n’est pas requise pour le bon fonctionnement de la [!UICONTROL sélection de compte dynamique]. For additional information, see dynamicAccountList.[](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_19715BA0AD4D41748E0C4A4A6B71AB51)

The rules found in  are applied to the value of . `dynamicAccountList``dynamicAccountMatch` If  only contains  (default), the rules in  apply only to the domain of the page.`dynamicAccountMatch`[!DNL window.location.host]`dynamicAccountList`

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | window.location.host |

**Syntaxe et valeurs possibles** {#section_95CD81972C22419B80A921CA137D3841}

The `dynamicAccountMatch` variable is usually populated by the Adobe consultant who provides the AppMeasurement for JavaScript file. Les valeurs répertoriées ci-dessous peuvent cependant être appliquées à tout moment.

```js
s.dynamicAccountMatch=[DOM object]
```

| Description | Valeur |
|---|---|
| Domaine (par défaut) | window.location.host |
| Chemin d’accès | window.location.pathname |
| Chaîne de requête | (window.location.search?window.location.search:"?") |
| Domaine et chemin d’accès | window.location.host+window.location.pathname |
| Chemin et chaîne de requête | window.location.pathname+(window.location.search?window.location.search:"?") |
| URL complète | window.location.href |

**Exemples** {#section_924687CCE255421AA2223A3D4B8B6A30}

```js
s.dynamicAccountMatch=window.location.pathname
```

```js
s.dynamicAccountMatch=window.location.host+window.location.pathname
```

**Paramètres de configuration** {#**section_43BCE13B1ADD4D418DF7CBB9DD7A6472}

Aucune

**Pièges, questions et conseils** {#section_EF9B2977BC21497D8C5EEB9BAD731E17}

* Dynamic account selection is not supported by AppMeasurement for JavaScript.[](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8)
* Lorsque des pages sont enregistrées sur un disque dur, [!DNL window.location.host] est vide. Ces pages vues sont alors envoyées à la suite de rapports par défaut (dans `s_account`).

* •Lorsqu’une page est traduite au moyen d’un moteur de traduction Web, tel que Google, la [!UICONTROL sélection de compte dynamique] ne fonctionne pas comme prévu. Pour effectuer un suivi plus précis, renseignez la variable [!UICONTROL s_account ] côté serveur.

## s.dynamicVariablePrefix {#concept_38C1F2452DDB47FCA8F458BE1398E276}

La variable permet au déploiement de marquer les variables qui doivent être renseignées de manière dynamique.

Les cookies, en-têtes de requête et paramètres de chaîne de requête d’image peuvent être renseignés de cette manière.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | D= | Quelconque | D= |

**Syntaxe et valeurs possibles** {#section_D0669899567F46B6A081C7661362BA81}

```js
s.prop1="D=User-Agent”
```

OU UTILISER UN INDICATEUR PERSONNALISE POUR LES VARIABLES DYNAMIQUES

```js
s.dynamicVariablePrefix=".."
```

**Exemples** {#section_DD148560F9E8416EBCF159194FA427AC}

```js
s.prop1="D=User-Agent”
```

OU UTILISER UN INDICATEUR PERSONNALISE POUR LES VARIABLES DYNAMIQUES

```js
s.dynamicVariablePrefix=".."
```

```js
s.prop1="..User-Agent"
```

**Pièges, questions et conseils** {#section_6889908FBD78488D955F67DDB17617B1}

* Vous pouvez utiliser des variables dynamiques afin de réduire sensiblement la longueur totale de l’URL en copiant des valeurs dans d’autres variables.
* Vous pouvez utiliser des variables dynamiques pour collecter, dans des en-têtes et des cookies, des données qui autrement ne seraient pas disponibles dans le cadre de la collecte de données.

## s.charSet {#concept_E65B9A8F75C3482C87D0D455805F89BD}

La propriété charSet, qui est normalement définie dans le fichier JavaScript, est utilisée par Analytics pour convertir les données entrantes au format UTF-8 en vue de les stocker et de créer des rapports par Analytics.

>[!N] Remarque : La propriété charSet est requise lors de l’envoi de données vers une suite de rapports multioctet et ne doit jamais être utilisée avec une suite de rapports standard. L’utilisation de la propriété charSet avec une suite de rapports ISO standard peut provoquer une troncature de la variable ou une conversion inattendue des caractères.

La valeur de la propriété charSet doit correspondre à l’encodage de la page Web utilisé dans la balise META ou l’en-tête http, même si la syntaxe est légèrement différente. Bien que la balise META utilise un alias pour l’encodage, la valeur de charSet doit utiliser le nom recommandé (ou officiel) de l’encodage.

Le tableau suivant répertorie certains des encodages les plus fréquents avec leur nom recommandé et leurs alias.

| Nom recommandé | Alias |
|--- |--- |
| ISO-8859-1 | ISO_8859-1, CP819, latin1 |
| ISO-8859-2 | ISO_8859-2, latin2 |
| ISO-8859-5 | ISO_8859-5, cyrillic |
| Big5 | Big-5 |
| Shift_JIS | SJIS |

Comme il existe de nombreux encodages et alias, contactez votre conseiller en implémentation ou le service à la clientèle Adobe pour vérifier la valeur appropriée de charSet si elle n’apparaît pas dans le tableau ci-dessus.

If a site has different web encodings on different pages, or a single JavaScript file is used for multiple sites, the charSet property can be set to a default value in the JavaScript file and then reset on specific pages as needed to override the default; for example, `s.charSet="UTF-8"` or `s.charSet="SJIS"`.

Toute valeur non vide du paramètre charSet provoque la conversion des données en UTF-8 pour le stockage. Tous les caractères de la plage 128 à 255 sont convertis dans la séquence UTF-8 sur deux octets correcte puis stockés. Ces caractères ne s’afficheront pas correctement dans une suite de rapports standard. La propriété charSet ne doit donc jamais être utilisée avec une suite de rapports standard.

De même, une valeur vide du paramètre charSet contourne le processus de conversion de données et tous les caractères de la plage 128 à 255 sont alors stockés sur un seul octet. Ces caractères ne s’affichent pas correctement dans une suite de rapports multioctet, puisque les codes mono-octets de ces caractères ne sont pas des valeurs UTF-8 correctes. Le paramètre charSet ne doit donc jamais être utilisé avec une suite de rapports standard. De plus, la valeur exacte d’encodage de la page Web doit être utilisée.

If the *`charSet`* variable contains an incorrect value, the data in all other variables are translated incorrectly. If JavaScript variables on your pages (e.g. *`pageName`*, [!UICONTROL prop1], or *`channel`*) contain only ASCII characters, *`charSet`* does not need to be defined. However, if the variables on your pages contain non-ASCII characters, the  variable must be populated.*`charSet`*

**Paramètres**

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|--- |--- |--- |--- |
| N/D | CE | N/D | "" |

**Syntaxe et valeurs possibles** {#section_EBC2176067A04D9E814CF78A86DC80FA}

```js
s.charSet="character_set"
```

**Exemples** {#section_406DE0A2B58441DB8512F5B3BE5D9CB5}

```js
s.charSet="ISO-8859-1"
```

```js
s.charSet="SJIS"
```

## s.currencyCode {#concept_CE216F1610E2499D8178DB9A8EB97C63}

La variable détermine le taux de conversion à appliquer aux recettes. 

Toutes les valeurs monétaires sont stockées dans la devise de votre choix. Si cette devise est identique à celle qui est spécifiée dans *`currencyCode`*, or *`currencyCode`* is empty, no conversion is applied.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|--- |--- |--- |--- |
| N/D | cc | Conversion &gt; Achats &gt; Recettes Tous les rapports de conversion affichant des recettes ou des valeurs monétaires | "USD" |

Si votre site autorise les visiteurs à effectuer des achats dans plusieurs devises, vous devez utiliser la variable *`currencyCode`* pour vous assurer que les recettes sont stockées dans la devise appropriée. For example, if the base currency for your report suite is USD, and you sell an item for 40 Euros, you should populate the *`currencyCode`* with "EUR" on the HTML page. Dès que la collecte de données reçoit les données, elle utilise le taux de conversion en cours pour convertir le montant de 40 euros dans son équivalent en dollars.

Il est recommandé de renseigner la variable *`currencyCode`* sur la page HTML, au lieu du fichier JavaScript, si vous vendez des articles dans plusieurs devises. Si vous souhaitez utiliser vos propres taux de conversion plutôt que les taux de conversion utilisés par Adobe, définissez la devise *`currencyCode`* de base de votre suite de rapports. Convertissez ensuite toutes les recettes avant de les envoyer dans [!DNL Analytics].

La conversion de devise s’applique à la fois aux recettes et à tout événement monétaire. Il s’agit d’événements utilisés pour additionner des valeurs semblables à des recettes, telles que des taxes et des frais d’expédition. Les recettes et les événements monétaires sont spécifiés dans la chaîne « products ». Pour plus d’informations sur la chaîne « products », reportez-vous à la section [events](../../../implement/js-implementation/c-variables/page-variables.md#concept_FFD115543D54401B98FE683BD7D5B3FE).

**Syntaxe et valeurs possibles** {#section_7CD68F08AB4848EE9B0D19DCC3F1BECE}

```js
s.currencyCode="currency_code"
```

**Exemples** {#section_D55ED45369544C8AAA02B3193752636C}

```js
s.currencyCode="GBP"
```

```js
s.currencyCode="EUR"
```

**Paramètres de configuration** {#section_D05E29F545A04958B1C0A82248BCA1B0}

Adobe [!DNL Customer Care] peut modifier le paramètre de devise par défaut de votre suite de rapports. Lorsque vous modifiez la devise de base d’une suite de rapports, les recettes existantes figurant dans le système ne sont pas converties. Toutes les nouvelles valeurs de recettes sont converties en conséquence.

**Pièges, questions et conseils** {#section_08A80A87B54A4861905953A6FA61FF8F}

* Si vous constatez des recettes étonnamment importantes dans les rapports, assurez-vous que la *`currencyCode`* variable et la devise de base de la suite de rapports sont correctement définies.
* The *`currencyCode`* variable is not persistent, meaning that the variable must be passed in the same image request as any revenue or other currency-related metrics.
* Les événements monétaires doivent uniquement être utilisés pour les devises. Si vous devez comptabiliser des valeurs arbitraires ou dynamiques qui ne sont pas des devises, utilisez le type d’événement [!UICONTROL numeric].
* Lorsque la variable *`currencyCode`* est vide, aucune conversion n’est appliquée.

Pour plus d’informations, voir Codes [de](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/currency.html)devise.

## s.cookieDomain {#concept_6164C39CF8BE4737A7EF1DE5A8376C1B}

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set.

Commonly, `s.cookieDomainPeriods` is used to generate `s.cookieDomain` from `window.location.hostnam`e. Instead of using `s.cookieDomainPeriods`, you can explicitly set `s.cookieDomain` to what you want to use in your implementation. Par exemple, vous pourriez définir des cookies au nom complet de la page en utilisant :

`s.cookieDomain = window.location.hostname;`

## s.cookieDomainPeriods {#concept_F17A59C7D8F54F5897AD40980B6725EB}

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set by determining the number of periods in the domain of the page URL. Elle est également utilisée par certains modules externes pour déterminer le domaine correct afin de définir le cookie du module externe.

La valeur par défaut de *`cookieDomainPeriods`* est "2". This is the value that is used if *`cookieDomainPeriods`* is omitted. Par exemple, l’utilisation du domaine `www.mysite.com`, *`cookieDomainPeriods`* doit être 2. Car `www.mysite.co.jp`il *`cookieDomainPeriods`* doit être "3".

If *`cookieDomainPeriods`* is set to "2" but the domain contains three periods, the JavaScript file attempts to set cookies on the domain suffix.

Par exemple, si vous définissez *`cookieDomainPeriods`* la valeur 2 sur le domaine `www.mysite.co.jp`, les `s_cc` cookies et `s_sq` sont créés sur le domaine `co.jp`. Comme `co.jp` est un domaine incorrect, la plupart des navigateurs rejette ces cookies. Cela entraîne la perte de données de mise en correspondance des clics des visiteurs, et le rapport [!UICONTROL Profil du visiteur] &gt; [!UICONTROL Technologie] &gt; [!UICONTROL Cookies] indique que pratiquement 100 % des visiteurs ont rejeté les cookies propriétaires.

Si la variable *`cookieDomainPeriods`* est définie sur « 3 » et que le domaine contient uniquement deux points, le fichier JavaScript définit les cookie sur le sous-domaine du site. Par exemple, si vous définissez *`cookieDomainPeriods`* la valeur "3" sur le domaine `www2.mysite.com`, les `s_cc` cookies et `s_sq` sont créés sur le domaine `www2.mysite.com`. When a visitor goes to another subdomain of your site (such as `www4.mysite.com`), all cookies set with `www2.mysite.com` cannot be read.

>[!NOTE]
>
>Do not include additional subdomains as part of *`cookieDomainPeriods`*. Par exemple, `store.toys.mysite.com` aurait toujours *`cookieDomainPeriods`* défini sur "2". Cette définition de la variable définit correctement les cookies sur le domaine racine [!DNL mysite.com]. Setting *`cookieDomainPeriods`* to "3" in this example would set cookies on the domain [!DNL toys.mysite.com], which has the same implications as the prior example.

Voir aussi [s.fpCookieDomainPeriods](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_0A25BD152B0744989E7C662A95448274).

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | CDP | Affecte plusieurs rapports, dans la mesure où il contrôle le mode de stockage et de traitement de l’identifiant visiteur. | "2" |

>[!NOTE]
>
>Some cloud computing services are considered Top-Level Domains, which do not allow cookies to be written. (Par exemple, `compute.amazonaws.com`, `*.herokuapp.com`, `*.googlecode.com`, etc.) Si vous mettez ces services en œuvre, vous pourriez être affecté par le paramètre de vie privé d’Analytics qui retire les utilisateurs qui ont bloqué tous les cookies si vous n’avez pas configuré votre propre domaine (par exemple, si vous testez votre mise en œuvre). Dans ce cas, tout accès pour lequel le système a déterminé que les cookies étaient désactivés, non fonctionnels ou inaccessibles est exclu et n’apparaît donc pas dans les rapports.

**Exemples** {#section_4218BE29FA5E49F58975A2094329B268}

Définition manuelle de la variable

```js
s.cookieDomainPeriods = "3";
```

Voici plusieurs exemples pour définir de manière dynamique la variable si le fichier JavaScript héberge les deux types :

```js
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```

```js
s.cookieDomainPeriods = "2"; 
var d=window.location.hostname; 
if(d.indexOf(".co.uk") > 0 || d.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

```js
s.cookieDomainPeriods = "2"; 
if(window.location.indexOf(".co.jp") > 0 || window.location.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

**Pièges, questions et conseils** {#section_F3BE3F039E5C4359B694DBB61369822C}

* If you notice that visitor click map data is absent, or that the [!UICONTROL Traffic] &gt; [!UICONTROL Technology] &gt; [!UICONTROL Cookies] report shows a large percentage of visitors who reject cookies, check that the value of *`cookieDomainPeriods`* is correct.

* If *`cookieDomainPeriods`* is higher than the number of sections in the domain, cookies will be set with the full domain. Cela peut entraîner une perte de données, dans la mesure où des visiteurs basculent entre différents sous-domaines.
* La variable était utilisée dans les implémentations obsolètes avant *`cookieDomainPeriods`* *`trackingServer`* de définir le cookie Identifiant visiteur. Bien qu’elle ne soit présente que dans du code obsolète, l’échec de la définition correcte *`cookieDomainPeriods`* dans ce cas présente un risque de perte de données pour votre implémentation.

## s.fpCookieDomainPeriods {#concept_0A25BD152B0744989E7C662A95448274}

La variable concerne les cookies définis par JavaScript (s_sq, s_cc, modules externes), qui sont intrinsèquement des cookies propriétaires, même si votre mise en œuvre utilise les domaines tiers 2o7.net ou omtrdc.net.

The *`fpCookieDomainPeriods`* variable should never be dynamically set . Si vous utilisez *`cookieDomainPeriods`*, il est recommandé de spécifier une valeur pour *`fpCookieDomainPeriods`* également. *`fpCookieDomainPeriods`* hérite de la *`cookieDomainPeriods`* valeur. Note that *`fpCookieDomainPeriods`* does not affect the domain on which the visitor ID cookie is set, even if your implementation treats this as a first-party cookie.

Le nom " *`fpCookieDomainPeriods`*" fait référence au nombre de points (".") dans le domaine, lorsque celui-ci commence par « www ». For example, `www.mysite.com` contains two periods, while `www.mysite.co.jp` contains three periods. Another way to describe the variable is the number of sections in the main domain of the site (two for `mysite.com` and three for `mysite.co.jp`).

Le fichier [!DNL AppMeasurement] for JavaScript utilise la *`fpCookieDomainPeriods`* variable pour déterminer le domaine avec lequel définir des cookies propriétaires autres que le cookie ID [!UICONTROL de] visiteur (s_vi). Au moins deux cookies sont affectés par cette variable, dont s_sq et s_cc (utilisés respectivement pour la mise en correspondance des clics des visiteurs et pour la vérification de cookies). Les cookies utilisés par des modules externes, tels que [!UICONTROL getValOnce] sont également affectés.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | cookieDomainPeriods |

**Exemple de code pour la définition de variables de domaine de cookies** {#section_5200A92D40384C82998606E800B69E13}

```js
s.fpCookieDomainPeriods="2" 
var d=window.location.hostname 
if(d.indexOf('.co.uk')>-1||d.indexOf('.com.au')>-1) 
  s.fpCookieDomainPeriods="3" 
```

**Syntaxe et valeurs possibles** {#section_87923F4C12E74AF99CC9AFC0FFD77D49}

The *`cookieDomainPeriods`* variable is expected to be a string, as shown below.

```js
s.fpCookieDomainPeriods="3"
```

**Exemples** {#section_EF7355718AD849BF963EE9F6F9F79891}

```js
s.fpCookieDomainPeriods="3"
```

```js
s.fpCookieDomainPeriods="2"
```

**Paramètres de configuration** {#section_DB65D9BC4F3048C8AD08F9A7CD8FCFC0}

Aucune

## s.cookieLifetime {#concept_8347C6648B0E4D4996E2F223C34B9A3D}

La variable est utilisée par les serveurs de collecte de données et JavaScript pour déterminer la durée de vie d’un cookie.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | cl | Trafic &gt; Technologie &gt; Cookies – Tous les rapports liés aux visiteurs | "" |

Si la variable *`cookieLifetime`* est définie, elle remplace toute autre expiration de cookie pour les servers de collecte de données et JavaScript, à une exception près, décrite ci-dessous. The *`cookieLifetime`* variable can have one of three values:

* [!DNL Analytics] Cookies
* Cookies
* Modules externes et paramètres JavaScript

**Syntaxe et valeurs possibles** {#section_09D4D122451B45FAB2C9398600EC66F1}

```js
s.cookieLifetime="value"
```

Les valeurs possibles sont répertoriées comme suit :

* ""
* "NONE"
* "SESSION"
* Nombre entier représentant le nombre de secondes avant l’expiration du cookie.

**Exemples** {#section_91499F70C8B14D3292FCF1B60F04E30A}

```js
s.cookieLifetime="SESSION"
```

```js
s.cookieLifetime="86400" // one day in seconds
```

**Paramètres de configuration** {#section_7BDAD4CFE8414C9BA5717A8C8B1BDD34}

Aucune

**Pièges, questions et conseils** {#section_23E24877F6554E0D9F8C8B7A9C2994B2}

*`cookieLifetime`* affecte le [!DNL Analytics] suivi. If, for example, *`cookieLifetime`* is two days, then monthly, quarterly, and yearly unique visitor reports will be incorrect. Soyez prudent lors de la définition de la variable *`cookieLifetime`*.

## s.doPlugins {#concept_676EAE4FAFCF4B018876390FC874EFDA}

La variable est une référence à la fonction . Elle permet d’appeler la fonction à l’emplacement approprié dans le fichier JavaScript.

The *`s_doPlugins`* function is called each time any of the following occurs:

* La *`t()`* fonction est appelée
* La *`tl()`* fonction est appelée
* Clic sur un lien de sortie ou de téléchargement
* Clic sur un élément de page suivi par la mise en correspondance des clics des visiteurs

La fonction *`doPlugins`* sert à exécuter des routines personnalisées dans le but de rassembler ou de modifier des données. If you are using an object name other than "s," make sure that the *`s_doPlugins`* is renamed appropriately. Par exemple, si le nom de l’objet est s_mc, la *`s_doPlugins`* fonction doit s_mc_doPlugins.

**Syntaxe et valeurs possibles** {#section_5CFB94598521455E80947964A306EA89}

La *`s_doPlugins`* fonction ne doit pas être placée entre guillemets et *`doPlugins`* doit toujours être affectée au nom exact de la *`s_doPlugins`* fonction (si cette fonction est renommée).

```js
s.doPlugins=s_doPlugins;
```

**Exemples** {#section_A5CF0054C56745268A1313CCC7730022}

```js
s.doPlugins=s_doPlugins;
```

```js
s_mc.doPlugins=s_mc_doPlugins;
```

**Paramètres de configuration** {#section_641F0EC55E3349E5A3F8671446797074}

Aucune

**Pièges, questions et conseils** {#section_0C7FB61CF0C946EF8A7D1B686D36E6ED}

* Le partage de contenu avec d’autres clients ou l’extraction de contenu de ces mêmes clients est la seule raison pouvant justifier le changement de nom d’un objet (de s en s_mc, par exemple). En renommant la fonction *`s_doPlugins`* function to [!UICONTROL s_mc_doPlugins] ensures that another client's JavaScript file does not overwrite your *`doPlugins`* function.

* Si vous commencez inopinément à extraire du contenu d’un autre client Adobe et que votre *`s_doPlugins`* fonction est remplacée, il est possible de simplement renommer la *`s_doPlugins`* fonction sans modifier le nom de l’objet. La meilleure solution consiste certes à utiliser un nom d’objet différent de celui des autres fichiers JavaScript de la même page, mais cela n’est pas obligatoire.

## s.registerPreTrackCallback et s.registerPostTrackCallback

Ces fonctions acceptent comme paramètres : rappel (fonction) et les paramètres de cette fonction. Par exemple :

```
s.registerPreTrackCallback(function(requestUrl,a,b,c) { 
    console.log("pre track callback"); 
    console.dir(requestUrl); // Request URL 
    console.dir(a); // param1 
    console.dir(b); // param2 
    console.dir(c); // param3 
}, "param1", "param2", "param3");
```

Le rappel est appelé avec `requestUrl` et les paramètres transmis lorsque le rappel est enregistré. Cela se produit avant ou après l’appel de suivi, selon la méthode utilisée pour enregistrer le rappel.

L’ordre dans lequel ces rappels sont appelés n’est pas garanti. Les rappels enregistrés dans la préfonction sont appelés après la création de l’URL de suivi finale. Les post-rappels sont appelés lors d’un appel de suivi réussi (si l’appel de suivi échoue, ces fonctions ne sont pas appelées). Les rappels enregistrés avec `registerPreTrackCallback` n’ont aucun impact sur l’appel de suivi. De plus, l’appel de ces méthodes de suivi dans un rappel enregistré n’est pas recommandé et peut entraîner une boucle sans fin.

## s.trackDownLoadLinks {#concept_0A7AEAB3172A4BEA8B2E8B1A3A8F596C}

Définissez la variable sur « true » si vous souhaitez effectuer le suivi de liens vers des fichiers téléchargeables de votre site.

Si *`trackDownloadLinks`* est "true", *`linkDownloadFileTypes`* est utilisé pour déterminer quels liens sont des fichiers téléchargeables.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | True |

La variable *`trackDownloadLinks`* ne doit être définie sur « false » que si le site ne comporte aucun lien vers des fichiers téléchargeables ou si vous n’êtes pas intéressé par le suivi des clics effectués sur des fichiers de ce type. If *`trackDownloadLinks`* is 'true,' when a file download link is clicked, data is immediately sent to [!DNL Analytics]. Les données envoyées avec un lien de téléchargement sont notamment l’URL de téléchargement du lien et les données de mise en correspondance des clics des visiteurs relatives à ce lien. Si la variable *`trackDownloadLinks`* is 'false,' then visitor click map data for links to downloadable files on your site is likely to be under reported.

**Syntaxe et valeurs possibles** {#section_828492CC2A144BC68D18C30CF397EEFC}

La variable *`trackDownloadLinks`doit être définie sur « true » ou « false ».*

**Exemples** {#section_BE2FA1873EBD4C5CA95E98B922B10280}

```
js
s.trackDownloadLinks=true 
```

```
js
s.trackDownloadLinks=false
```

**Paramètres de configuration** {#section_9A5F69966BAF433A8DA2BCF655A652D1}

Aucune

**Pièges, questions et conseils** {#section_B3764520D81143968F96CB69AADD457F}

* When *`trackDownloadLinks`* is 'false,' links that people use to download files on your site are likely to be under reported in visitor click map.
* When *`trackDownloadLinks`* is 'true,' data is sent each time a visitor clicks a file download link.

## s.trackExternalLinks {#concept_E1321318696841648A54CF77F6C4A7AF}

Si est défini sur "true" et sont utilisés pour déterminer si un lien sur lequel l’utilisateur a cliqué est un lien de sortie.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | True |

La variable *`trackExternalLinks`* ne doit être définie sur « false » que si votre site ne comporte aucun lien de sortie ou si vous n’êtes pas intéressé par le suivi des clics effectués sur ces liens. On désigne sous le nom de lien de sortie tout lien qui permet à un visiteur de quitter votre site. Si la variable *`trackExternalLinks`* is 'true,' then when you click an exit link, tracking data is immediately sent. Les données envoyées avec un lien de sortie sont notamment l’URL et le nom du lien, ainsi que les données de mise en correspondance des clics des visiteurs relatives à ce lien. Si la variable *`trackExternalLinks`* is 'false,' then visitor click map data for exit links on your site is likely to be under reported.

**Syntaxe et valeurs possibles** {#section_267748949A7544658E1D838AAEF964B2}

La variable *`trackExternalLinks`doit être définie sur « true » ou « false ».*

```
js
s.trackExternalLinks=true|false
```

**Exemples** {#section_EF18DB05884240F5B5062631E68E10A7}

```
js
s.trackExternalLinks=true 
```

```
js
s.trackExternalLinks=false
```

**Paramètres de configuration** {#section_C8748CFE36324FAFB14C23E3E1FB5082}

Aucune

**Pièges, questions et conseils** {#section_FE2C3AF17DA24EA8A944BF1D394FB5BC}

* When *`trackExternalLinks`* is 'false,' links that take people away from your site are likely to be under reported in visitor click map.
* When *`trackExternalLinks`* is 'true,' data is sent each time a visitor clicks on an exit link (before link target loads).

## s.trackInlineStats {#concept_E3A811D9761E4917935F6CD9059C7FCC}

La variable détermine si les données ClickMap sont collectées.

If *`trackInlineStats`* is 'true,' data about the page and link clicked are stored in a cookie called s_sq. If 'false,' s_sq will have a value of "[[B]]," which is considered null.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | ClickMap | False |

**Syntaxe et valeurs possibles** {#section_46B2C1DD0D104A01A9C239929420CD90}

```
js
s.trackInlineStats=true|false
```

La variable *`trackInlineStats`doit être définie sur « true » ou « false ».*

**Exemples** {#section_F146770917A3493AB8007626913CD6AB}

```js
s.trackInlineStats=true
```

```js
s.trackInlineStats=false
```

**Paramètres de configuration** {#section_FB2CDB07CDCE454786D96A66E4D8EDCD}

Aucune

## s.linkDownloadFileTypes {#concept_06CC14C69DFD4887A5E6967A157A9E05}

La variable est une liste d’extensions de fichiers séparées par des virgules.

Si votre site contient des liens pointant vers des fichiers associés à l’une de ces extensions, les URL de ces liens s’afficheront dans le rapport [!UICONTROL Téléchargements de fichiers]

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|--- |--- |--- |--- |
| N/D | N/D | Trafic &gt; Trafic du site &gt; Téléchargements de fichiers | "exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls" |

La variable n’est pertinente que lorsque *`linkDownloadFileTypes`* *`trackDownloadLinks`* la valeur True est affectée.

Seuls les clics avec le bouton gauche effectués sur un lien sont comptabilisés dans le rapport [!UICONTROL Téléchargements de fichiers]. Tous les téléchargements de fichiers qui démarrent automatiquement lors du chargement d’une page, ou qui sont uniquement téléchargés à la suite d’une redirection, ne sont pas comptabilisés dans le rapport [!UICONTROL Téléchargements de fichiers]. Lorsque vous cliquez sur un fichier avec le bouton droit et sélectionnez ensuite l’option « Enregistrer la cible sous... », il n’est pas comptabilisé dans le rapport [!UICONTROL Téléchargements de fichiers].

La variable *`linkDownloadFileTypes`* peut être utilisée pour effectuer le suivi des clics vers des flux RSS. Si vous avez des liens vers des flux RSS avec une extension .xml ou autre, l’ajout de ",xml" à la *`linkDownloadFileTypes`* liste vous permet de voir à quelle fréquence chaque lien RSS est cliqué.

**Syntaxe et valeurs possibles** {#section_E0B3F3817BBF4B11AFAABEF8BB951E5A}

Inclure uniquement les extensions de fichiers (sans espaces).

```js
s.linkDownloadFileTypes="type1[,type2[,type3[...]]]"
```

Toute extension de fichier peut être incluse dans la liste. Veillez à ne pas inclure d’extensions de fichier courantes, telles que htm ou aspx, dans *`linkDownloadFileTypes`*. Cela risquerait, en effet, d’entraîner l’envoi d’une demande d’image supplémentaire pour chaque clic, laquelle serait facturée comme un appel au serveur principal.

**Exemples** {#section_C53F1AF768434CEBA65F3D255BC470AD}

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls"
```

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls,xml"
```

**Paramètres de configuration** {#section_CE24D5852E4D441A958A4EDDB82382A7}

Aucune

**Pièges, questions et conseils** {#section_786CF22D5553429EB6524B13774793BC}

* Seuls les clics avec le bouton gauche effectués sur les fichiers de téléchargement entraînent l’apparition de l’URL dans le rapport [!UICONTROL Téléchargements de fichiers].
* L’insertion d’une extension de fichier courante dans *`linkDownloadFileTypes`* peut entraîner une augmentation sensible du nombre total d’appels au serveur envoyés aux serveurs d’Adobe.
* Les liens vers des redirections côté serveur ou des pages HTML qui lancent automatiquement le téléchargement d’un fichier ne sont pas comptabilisés, sauf si l’extension de fichier figure dans *`linkDownloadFileTypes`*.
* Les liens qui utilisent le langage JavaScript (tels que javascript:openLink( )) ne sont pas comptabilisés dans les téléchargements de fichiers.

## s.linkInternalFilters {#concept_D53C1186762E4AAE82451712B0801CAD}

La variable est utilisée pour déterminer les liens de votre site qui sont des liens de sortie.

Il s’agit d’une liste, séparée par des virgules, de filtres représentant les liens qui font partie du site.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | Chemins &gt; Entrées et sorties &gt; Liens de sortie |  |

>[!NOTE]
>
>Nous avions précédemment suggéré de définir linkInternalFilters sur javascript:. Toutefois, il en résultait que tous les domaines étaient considérés comme externes, y compris le domaine actuel dans lequel réside la balise. Si vous voulez que plusieurs domaines soient considérés comme internes, vous pouvez les ajouter, tel qu’illustré dans les exemples ci-dessous.

The *`linkInternalFilters`* variable is used to determine whether a link is an exit link, which is defined as any link that takes a visitor away from your site. Le lien apparaît dans le rapport des liens de sortie, que la fenêtre cible soit une fenêtre contextuelle ou qu’il s’agisse de la fenêtre existante. Le suivi des liens de sortie est effectué uniquement si *`trackExternalLinks`* est définie sur `"true"`. (Voir [Suivi des liens](https://marketing.adobe.com/resources/help/en_US/dtm/link_tracking.html) dans la documentation relative à Dynamic Tag Management pour plus d’informations sur la façon dont Dynamic Tag Management gère les liens de sortie.) Les filtres dans *`linkInternalFilters`* ne sont pas sensibles à la casse.

The list of filters in  applies to the domain and path of any link by default. *`linkInternalFilters`* If *`linkLeaveQueryString`* is set to `"true"`, then the filters apply to the entire URL (domain, path, and query string). Les filtres sont toujours appliqués au chemin absolu de l’URL, même si un chemin relatif est utilisé comme valeur href.

Sachez que tous les domaines de votre site (ainsi que tout partenaire qui utilise votre fichier JavaScript) sont inclus dans *`linkInternalFilters`*. Si tous les domaines ne sont pas inclus dans la liste, tous les liens qui y sont associés sont considérés comme des liens de sortie, ce qui a pour effet d’augmenter le nombre d’appels au serveur envoyés. If you would like multiple domains or companies to use a single  for JavaScript file, you may consider populating  on the page, overriding the value specified in the JavaScript file. [!DNL AppMeasurement]*`linkInternalFilters`* S’il existe des domaines mineurs qui redirigent immédiatement vers votre domaine principal, ils ne doivent pas nécessairement être inclus dans la liste.

L’exemple suivant illustre l’utilisation de cette variable. In this example, the URL of the page is `https://www.mysite.com/index.html`.

```js
s.trackExternalLinks=true 
s.linkInternalFilters="mysite.com" 
s.linkExternalFilters="" 
s.linkLeaveQueryString=false 
... 
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Exit Link</a> 
<a href="https://www2.site1.com/partners/">Exit Link</a> 
```

**Syntaxe et valeurs possibles** {#section_810966F09912415B96EA9C2EDAE0CEA0}

The *`linkInternalFilters`* variable is a comma-separated list of ASCII characters. Aucun espace n’est autorisé.

```js
s.linkInternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

**Exemples** {#section_491F48556DC247889D54C66FC431B4EC}

```js
s.linkInternalFilters="mysite.com"
```

```js
s.linkInternalFilters="mysite.com,mysite.net,vanity1.com"
```

**Paramètres de configuration** {#section_546AC1FACB664ABFBCF312990097C987}

Aucune

**Pièges, questions et conseils** {#section_E83A6F8B6EE44D51A2800D83F8BB264F}

* Include all domains that the [!DNL AppMeasurement] for JavaScript file may be served under in the filter list.
* Vérifiez régulièrement le rapport [!UICONTROL Chemins] &gt; [!UICONTROL Entrées et sorties] &gt; [!UICONTROL Liens de sortie] pour vous assurer que toutes les entrées qu’il contient sont correctes.

* Consultez régulièrement les contrats conclus avec les partenaires afin de déterminer s’ils contiennent des restrictions en termes de suivi des liens. Par exemple, vous pouvez ne pas être autorisé à effectuer le suivi des liens qui apparaissent dans des publicités de partenaires. Filtrez les liens des partenaires en ajoutant leur domaine à la variable *`linkInternalFilters`*:

```js
s.linkInternalFilters="mysite.com,mysite.net,mypartner.net/adclick"
```

## s.linkLeaveQueryString {#concept_118C280E29394DB5A16DBBF41EB4D742}

Par défaut, les chaînes de requête sont exclues de tous les rapports.

Pour certains liens de sortie et de téléchargement, la partie importante de l’URL peut se trouver dans la chaîne de requête, comme illustré dans l’exemple d’URL ci-dessous.

```js
https://www.mycompany.com/download.asp?filename=myfile.exe
```

Le nom du fichier de téléchargement peut être défini dans la chaîne de requête et, par conséquent, cette dernière est nécessaire pour une meilleure précision du rapport [!UICONTROL Téléchargements de fichiers].

La variable *`linkLeaveQueryString`* détermine si la chaîne de requête doit être incluse dans les rapports [!UICONTROL Liens de sortie] et [!UICONTROL Téléchargements de fichiers].

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|--- |--- |--- |--- |
| N/D | N/D | Téléchargements de fichiers de liens de sortie | false |

>[!NOTE]
>
>Setting `linkLeaveQueryString=true` includes all query string parameters for all exit links and download links.

**Syntaxe** {#section_C40CF036B71A496D92574C6E46DE8302}

```js
s.linkLeaveQueryString=[false/true]
```

**Exemples** {#section_E42CEC8DDE624A4B979F4F6C8094A7F9}

```js
s.linkLeaveQueryString=false
```

**Valeurs possibles** {#section_E13211451B664B909B1BFDD050472F18}

```js
s.linkLeaveQueryString=false
```

```js
s.linkLeaveQueryString=true
```

**Paramètres de configuration** {#section_835FD74D3CA9425A9D091CACF88A6F1F}

Aucune configuration n’est nécessaire pour cette variable.

**Pièges, questions et conseils** {#section_085E79D1A7F74F5D95F82D34FB82AEC4}

* Setting `s.linkLeaveQueryString=true` includes all query string parameters for all exit links and download links.
* The `linkLeaveQueryString` variable does not affect recorded page URLs, visitor click map, or [!UICONTROL Path] reports.

## s.linkTrackVars {#concept_A6B117826C15402EBD0781A94C8065B9}

La variable est une liste de variables séparées par des virgules qui sont envoyées avec des liens personnalisés, de téléchargement et de sortie.

If *`linkTrackVars`* is set to "", all variables that have values are sent with link data. Pour éviter le gonflement des instances ou des pages vues associées à d’autres variables, Adobe conseille de renseigner *`linkTrackVars`* et *`linkTrackEvents`* dans l’événement [!UICONTROL onClick] d’un lien utilisé pour le suivi des liens.

Toutes les variables qui doivent être envoyées avec des données de lien (liens personnalisés, de téléchargement et de sortie) doivent être répertoriées dans *`linkTrackVars`*. Si *`linkTrackEvents`* est utilisé, *`linkTrackVars`* doit contenir "events".

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | Quelconque | "Aucun" |

Lorsque vous renseignez *`linkTrackVars`*, do not use the 's.' prefix for variables. For example, instead of populating  with "s.prop1," you should populate it with "prop1." *`linkTrackVars`* The following example illustrates how  should be used.*`linkTrackVars`*

```js
s.linkTrackVars="eVar1,events" 
s.linkTrackEvents="event1" 
s.events="event1" 
s.eVar1="value A" 
s.eVar2="value B" 
s.t() // eVar1, event1 and event2 are recorded 
<a href="https://google.com">event1 and eVar1 are recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.eVar1='value C';s.events='';s.tl(this,'o')">eVar1 is recorded</a> 
```

Dans la mesure où le lien vers google.com est un lien de sortie (sauf si votre société est Google), « event1 » et « eVar1 » sont envoyés avec les données du lien de sortie, ce qui a pour effet d’augmenter le nombre d’instances associées à « eVar1 » et le nombre de déclenchements de « event1 ». In the link to [!DNL test.php], [!UICONTROL eVar1] is sent with a value of 'value C' because that is the current value of [!UICONTROL eVar1] at the time that *`tl()`* is called.

**Syntaxe et valeurs possibles** {#section_DCC239F5CFE74959856764DAB1862BA7}

The *`linkTrackVars`* variable is a case-sensitive, comma-separated list of variable names, without the object name prefix. Utilisez « eVar1 » plutôt que « s.eVar1 ».

```js
s.linkTrackVars="variable_name[,variable_name[...]]"
```

Il se peut que  variable may contain only variables that are sent to , namely: , , , , eVar1-75, prop1-75, hier1-5, , , , , and .*`linkTrackVars`*[!DNL Analytics]*`events`**`campaign`**`purchaseID`**`products`**`channel`**`server`**`state`**`zip`**`pageType`*

**Exemples** {#section_546BAAC7373A41BF8583B280EAAB607C}

```js
s.linkTrackVars="events,prop1,eVar49"
```

```js
s.linkTrackVars="products"
```

**Paramètres de configuration** {#section_E387604B8A434A7F89A82A886649A89D}

Aucune

**Pièges, questions et conseils** {#section_99E0783A608C4462945F35D21AB4AC2B}

* If *`linkTrackVars`* is blank, all variables that have values are tracked with all server calls.
* Any variable listed in *`linkTrackVars`* that has a value at the time of any download, exit, or custom link, are tracked.
* If  is used,  must contain "events."*`linkTrackEvents`**`linkTrackVars`*

* N’utilisez pas le préfixe « s. » ou « s_objectname. » pour les variables.

## s.linkTrackEvents {#concept_34D029097A674D0A97690C9569590EF5}

The  variable is a comma-separated list of events that are sent with a [!UICONTROL custom], [!UICONTROL exit], or [!UICONTROL download] link.

If an event is not in *`linkTrackEvents`*, it is not sent to [!DNL Analytics], even if it is populated in the [!UICONTROL onClick] event of a link, as shown in the following example:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

Dans le premier lien pointant vers [!DNL help.php], vous pouvez constater que la variable « events » conserve la valeur qui était définie avant que l’utilisateur ne clique. Cela permet à event1 d’être envoyé avec le lien personnalisé. Dans le deuxième exemple, le lien pointant vers [!DNL test.php], event2 n’est pas enregistré, car il ne figure pas dans *`linkTrackEvents`*.

To avoid confusion and potential problems, Adobe recommends populating  and  in the onClick event of a link that is used for link tracking.*`linkTrackVars`**`linkTrackEvents`*

The *`linkTrackEvents`* variable contains the events that should be sent with [!UICONTROL custom], [!UICONTROL download], and [!UICONTROL exit] links. This variable is only considered if  contains "events."*`linkTrackVars`*

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | Conversion | "Aucun" |

**Syntaxe et valeurs possibles** {#section_89BA2425FBDC400A8C8B7FCDE7D67D63}

The *`linkTrackEvents`* variable is a comma-separated list of events (no spaces).

```js
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

Seuls les noms d’événement sont autorisés dans *`linkTrackEvents`*. These events are listed in [Events](../../../implement/js-implementation/c-variables/page-variables.md#concept_FFD115543D54401B98FE683BD7D5B3FE). Si le nom de l’événement est précédé ou suivi d’un espace, il ne peut pas être envoyé avec des demandes d’images de lien.

**Exemples** {#section_AB7F952E522A4DCC92944EBF74C26BDD}

```js
s.linkTrackEvents="purchase,event1"
```

```js
s.linkTrackEvents="scAdd,scCheckout,purchase,event14"
```

**Paramètres de configuration** {#section_D938A47346D94A0C9E98FB327F2EF349}

Aucune

**Pièges, questions et conseils** {#section_DBB68BECC9D44380816113DB2566C38C}

* The JavaScript file only uses  if  contains the "events" variable. *`linkTrackEvents`**`linkTrackVars`* "events" ne doit être inclus dans *`linkTrackVars`* que lorsque *`linkTrackEvents`* est défini.

* Beware if an event is fired on a page, and is listed in *`linkTrackEvents`*. That event is recorded again with any [!UICONTROL exit], [!UICONTROL download], or [!UICONTROL custom] links unless the events variable is reset prior to that event (in the [!UICONTROL onClick] of a link or after the call to the *`t()`* function).

* If *`linkTrackEvents`* contains spaces between event names, the events are not recorded.

## s.linkExternalFilters {#concept_92A59169DCE443EBAE81A373B27BB6DD}

Si votre site contient plusieurs liens vers des sites externes et que vous ne souhaitez pas suivre tous les liens de sortie, vous pouvez utiliser la variable pour créer des rapports sur un sous-ensemble spécifique de liens de sortie.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | Chemins &gt; Entrées et sorties &gt; Liens de sortie | "" |

La variable  variable is an optional variable used in conjunction with  to determine whether a link is an exit link. *`linkExternalFilters`**`linkInternalFilters`* On désigne sous le nom de lien de sortie tout lien qui permet à un visiteur de quitter votre site. Le lien apparaît dans le rapport des liens de sortie, que la fenêtre cible soit une fenêtre contextuelle ou qu’il s’agisse de la fenêtre existante. Le suivi des liens de sortie est effectué uniquement si la variable *`trackExternalLinks`* is set to 'true.' The filters in  and  are case insensitive.*`linkExternalFilters`**`linkInternalFilters`*

>[!NOTE]
>
>If you don't want to use , delete it or set it to "".*`linkExternalFilters`*

The filters list in  and  apply to the domain and path of any link by default. *`linkExternalFilters`**`linkInternalFilters`* If  is set to 'true,' the filters apply to the entire URL (domain, path, and query string). *`linkLeaveQueryString`* Ces filtres sont toujours appliqués au chemin absolu de l’URL, même si un chemin relatif est utilisé comme valeur href.

La plupart des entreprises estiment que la variable *`linkInternalFilters`* leur confère suffisamment de contrôle sur les liens de sortie, rendant de ce fait inutile la variable *`linkExternalFilters`*. Using *`linkExternalFilters`* simply decreases the likelihood that an exit link is considered external. If *`linkExternalFilters`* has a value, then a link is considered only external if it does not match *`linkInternalFilters`* and does match *`linkExternalFilters`*.

L’exemple suivant illustre l’utilisation de cette variable. In this example, the URL of the page is `https://www.mysite.com/index.html`.

```js
s.trackExternalLinks=true 
s.linkInternalFilters="javascript:,mysite.com" 
s.linkExternalFilters="site1.com,site2.com,site3.com/partners" 
s.linkLeaveQueryString=false 
... 
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Not an Exit Link</a> 
<a href="https://www.site1.com">Exit Link</a> 
<a href="https://www2.site3.com/partners/offer.asp">Exit Link</a> 
```

**Syntaxe et valeurs possibles** {#section_E35DAAAE8BDE44CEB8F6763EF1344693}

The *`linkExternalFilters`* variable is a comma-separated list of ASCII characters. Aucun espace n’est autorisé.

```js
s.linkExternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

Toute partie d’une URL peut être incluse dans la variable *`linkExternalFilters`*, separated by commas.

**Exemples** {#section_1D2F13EEC28942868C2F4207ADF2DDE0}

```js
s.linkExternalFilters="partnersite.com,partnertwo.net/path/"
```

```js
s.linkExternalFilters=""
```

**Paramètres de configuration** {#section_2D0CA911855B4B3698145FC18D5021C3}

Aucune

**Pièges, questions et conseils** {#section_8B40E6F539E3473B934A8DB7C5086D73}

* Using *`linkExternalFilters`* can result in fewer links on your site being exit links. N’utilisez pas cette variable au lieu de *`linkInternalFilters`* forcer les liens internes à devenir des liens de sortie.

* Si *`linkExternalFilters`* vous devez appliquer la chaîne de requête d’un lien, assurez-vous *`linkLeaveQueryString`* qu’elle est définie sur "true". See [linkLeaveQueryString](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_118C280E29394DB5A16DBBF41EB4D742) before setting to `"true"`.

* To disable exit link tracking, set *`trackExternalLinks`* to `"false"`.

## s.usePlugins {#concept_81836470A25C41228CE04084565F667D}

If the  function is available and contains useful code, [!UICONTROL s_usePlugins] should be set to 'true.'

Lorsque [!UICONTROL usePlugins] a la valeur "true", la *`s_doPlugins`* fonction est appelée avant chaque demande d’image.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | True |

**Syntaxe et valeurs possibles** {#section_BAD0F150047A4B7FB1214491B939A1FC}

```js
s.usePlugins=true|false
```

La variable [!UICONTROL usePlugins] doit être définie sur « true » ou « false ».

**Exemples** {#section_1423CC3026384B1A9F78B272166B1DF5}

```js
s.usePlugins=true
```

```js
s.usePlugins=false
```

The usePlugins variable should only be false (or not declared) if the  function is not declared in your JavaScript file.*`s_doPlugins`*

**Paramètres de configuration** {#section_DFD41717134147E988B6AFC7DE5BB9E3}

Aucune