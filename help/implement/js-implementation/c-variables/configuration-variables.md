---
description: Variables de configuration définies dans appmeasurement. js.
keywords: Mise en œuvre d’Analytics
seo-description: Variables de configuration définies dans appmeasurement. js pour Adobe Analytics
seo-title: Variables de configuration
solution: Analytics
subtopic: Variables
title: Variables de configuration
topic: Développeur et mise en œuvre
uuid: a 19484 b 6-e 350-4 c 12-b 4 d 6-a 31 c 79 a 42 db 0
translation-type: tm+mt
source-git-commit: 696e7ed6dc6648cf523bc81e6cd40c7a06115484

---


# Variables de configuration

Les variables de configuration contrôlent le mode de collecte et de traitement des données dans les rapports. Variables de configuration les plus courantes généralement définies dans le fichier appmeasurement global appmeasurement. js principal. Ces variables peuvent être définies dans le code et les liens de niveau page Analytics, le cas échéant.

Not all of these variables appear in the code by default when you generate code through the **[!UICONTROL Admin Tool]** &gt; **[!UICONTROL Code Manager]**. Certaines de ces variables de configuration peuvent ne pas s’appliquer aux besoins de mise en œuvre de votre site.

Ces variables de configuration peuvent être utilisées aux fins suivantes :

* Suivi de plusieurs sites/domaines
* Utilisation de n’importe quelle devise pour les achats
* Collecte de données sans tenir compte de la langue
* Suivi des liens (nombre de fichiers téléchargés, liens vers des sites externes)
* Suivi des liens personnalisés à des fins uniques

>[!NOTE]
>
>[!DNL AppMeasurement] exige que toutes les variables de configuration soient définies avant l'appel initial à la fonction de suivi. `t()` If configuration variables are set after the call to `t()`, unexpected results may occur. To ensure proper data collection, all configuration variables must be above the `doPlugins` function.

## s.account {#concept_685A5C832A6C40619ACB5920925785DC}

<!--
s_account.xml
-->

La variable détermine la suite de rapports dans laquelle les données sont stockées et consignées.

If sending to multiple report suites (multi-suite tagging), `s.account` may be a comma-separated list of values. L’ID de la suite de rapports est déterminé par Adobe.

**Paramètres**

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|--- |--- |--- |--- |
| 40 octets | Dans le chemin de l’URL | N/D | N/D |

Chaque ID de suite de rapports doit correspondre à la valeur créée dans [!DNL Admin Console]. La taille de cet ID est limitée à 40 octets ; cependant, la somme de toutes les suites de rapports (toute la liste des valeurs séparées par des virgules) est illimitée.

La suite de rapports est le niveau de segmentation le plus fondamental dans le cadre de la création de rapports. Vous pouvez définir autant de suites de rapports que le permet votre contrat. Chaque suite de rapports fait référence à un ensemble dédié de tableaux remplis dans les serveurs de collecte d’Adobe. Une suite de rapports est identifiée par la variable `s_account` dans votre code JavaScript.

La liste déroulante des sites située dans le coin supérieur gauche des rapports d’[!DNL Analytics] affiche la suite de rapports active. Un identifiant (ID) unique est affecté à chaque suite de rapports. La variable `s_account` contient un ou plusieurs ID auxquels des données sont envoyées. La valeur d’ID de la suite de rapports est invisible pour les utilisateurs d’[!DNL Analytics]. Elle doit être fournie ou approuvée par Adobe avant son utilisation. Un « nom convivial », que vous pouvez modifier dans la section des suites de rapports d’[!DNL Admin Console], est associé à chaque ID de suite de rapports.

The `s_account` variable is normally declared inside the JavaScript file (s_code.js). You can declare the `s_account` variable on the HTML page, which is a common practice when the value of `s_account` may change from page to page. Because the `s_account` variable has a global scope, it should be declared immediately before including Adobe's JavaScript file. If `s_account` does not have a value when the JavaScript file is loaded, no data is sent to [!DNL Analytics].

Adobe's [!DNL DigitalPulse Debugger] displays the value of `s_account` in the path of the URL that appears just below the word "Image," just after /b/ss/. In some cases, the value of `s_account` also appears in the domain, before 112.2o7.net. La valeur indiquée dans le chemin est la seule qui détermine la suite de rapports de destination. Le texte en gras dans l’exemple ci-dessous affiche les suites de rapports auxquelles des données sont envoyées, telles qu’elles apparaissent dans le débogueur. Voir   [Débogueur DigitalPulse](../../../implement/impl-testing/debugger.md#concept_B26FFE005EDD4E0FACB3117AE3E95AA2).

```js
https://mycompany.112.207.net/b/ss/ 
<b>mycompanycom,mycompanysection</b>/1/H.1-pdv-2/s21553246810948?[AQB]
```

**Syntaxe et valeurs possibles** {#section_3BE913DF26D848AEB4CB5B0A6CE7F0CA}

L’identifiant de la suite de rapports est une chaîne composée de caractères ASCII alphanumériques, d’une longueur maximale de 40 octets. Le trait d’union est le seul caractère spécial autorisé. Les espaces, les points, les virgules et les autres signes de ponctuation ne sont pas autorisés. La variable `s_account` peut contenir plusieurs suites de rapports ; elles reçoivent toutes des données de cette page.

```js
var s_account="reportsuitecom[,reportsuite2[,reportsuite3]]"
```

All values of `s_account` must be provided or approved by Adobe.

**Exemples** {#section_16580A9101B64560A58C7745397FB42F}

```js
var s_account="mycompanycom"
```

```js
var s_account="mycompanycom,mycompanysection"
```

**Configuration de la variable dans Analytics** {#section_7DFB2CCF02F045AFB1AD4F376638393B}

Le nom convivial associé à chaque ID de suite de rapports peut être modifié par Adobe [!DNL Customer Care]. Ce nom est visible dans la liste déroulante des sites située dans le coin supérieur gauche d’[!DNL Analytics].

**Pièges, questions et conseils** {#section_BFFDA5C0AF31442494B0E02F0925CF93}

* If `s_account` is empty, not declared, or contains an unexpected value, no data is collected.
* When the `s_account` variable is a comma-separated list (multi-suite tagging), do not put spaces between report suite IDs.
* If [!UICONTROL s.dynamicAccountSelection] is set to *True* the URL is used to determine the destination report suite. Utilisez le [!DNL DigitalPulse Debugger] pour déterminer les suites de rapports de ce type.

* Dans certains cas, [!DNL VISTA] peut être utilisé pour modifier la suite de rapports de destination. Il est conseillé d’utiliser [!DNL VISTA] pour réacheminer ou copier les données sur une autre suite de rapports en cas d’utilisation de cookies propriétaires ou si votre site comporte plus de 20 suites actives.

* Always declare `s_account` inside the JS file or just before it is included.

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

<!-- 
dynamicAccountList.xml
-->

[!DNL AppMeasurement] pour JavaScript peut sélectionner, de manière dynamique, la suite de rapports à laquelle envoyer les données. La variable contient les règles utilisées pour déterminer la suite de rapports de destination.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | "" |

Cette variable est utilisée conjointement avec les variables *`dynamicAccountSelection`* et *`dynamicAccountMatch`* variables. The rules in *`dynamicAccountList`* are applied if *`dynamicAccountSelection`* is set to 'true,' and they apply to the section of the URL specified in *`dynamicAccountMatch`*.

If none of the rules in *`dynamicAccountList`* matches the URL of the page, the report suite identified in `s_account` is used. Les règles répertoriées dans cette variable sont appliquées de gauche à droite. Si l’URL de la page correspond à plusieurs règles, celle qui est située le plus à gauche est utilisée pour déterminer la suite de rapports. Par conséquent, vos règles plus génériques doivent être déplacées vers la droite de la liste.

In the following examples, the page URL is `www.mycompany.com/path1/?prod_id=12345` and `dynamicAccountSelection` is set to *true* and `s_account` is set to `mysuitecom.`

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

* Dynamic account selection is not supported by [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8).
* Si l’URL de la page correspond à plusieurs règles, celle qui est située le plus à gauche est utilisée.
* Si aucune correspondance n’est trouvée, la suite de rapports par défaut est utilisée.
* Si votre page est enregistrée sur le disque dur d’un utilisateur ou traduite au moyen d’un moteur de traduction Web (c’est le cas des pages traduites par Google, par exemple), il y a de fortes chances que la sélection de comptes dynamique ne fonctionne pas. Pour effectuer un suivi plus précis, renseignez la variable `s_account` côté serveur.
* The `dynamicAccountSelection` rules apply only to the section of the URL specified in `dynamicAccountMatch`.

* When using dynamic account selection, be sure to update *`dynamicAccountList`* every time you obtain a new domain.
* Utilisez le [!DNL DigitalPulse Debugger] pour tenter d’identifier la suite de rapports de destination. The `dynamicAccountSelection` variable always overrides the value of `s_account`.

## s.dynamicAccountMatch {#concept_718171E602214CCC9905C749708BBE52}

<!-- 
dynamicAccountMatch.xml
-->

La variable utilise l’objet DOM pour récupérer la section de l’URL à laquelle s’appliquent toutes les règles indiquées dans 

This variable is only valid when *`dynamicAccountSelection`* is set to 'True.' Comme la valeur par défaut est [!DNL window.location.host], cette variable n’est pas requise pour le bon fonctionnement de la [!UICONTROL sélection de compte dynamique]. For additional information, see [dynamicAccountList](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_19715BA0AD4D41748E0C4A4A6B71AB51).

The rules found in `dynamicAccountList` are applied to the value of `dynamicAccountMatch`. If `dynamicAccountMatch` only contains [!DNL window.location.host] (default), the rules in `dynamicAccountList` apply only to the domain of the page.

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

* Dynamic account selection is not supported by [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8).
* Lorsque des pages sont enregistrées sur un disque dur, [!DNL window.location.host] est vide. Ces pages vues sont alors envoyées à la suite de rapports par défaut (dans `s_account`).

* •Lorsqu’une page est traduite au moyen d’un moteur de traduction Web, tel que Google, la [!UICONTROL sélection de compte dynamique] ne fonctionne pas comme prévu. Pour effectuer un suivi plus précis, renseignez la variable [!UICONTROL s_account ] côté serveur.

## s.dynamicVariablePrefix {#concept_38C1F2452DDB47FCA8F458BE1398E276}

<!-- 
dynamicVariablePrefix.xml
-->

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

<!-- 
charset.xml
-->

La propriété charset, normalement définie dans le fichier JavaScript, est utilisée par Analytics pour convertir les données entrantes en UTF -8 pour le stockage et la création de rapports par Analytics.

>[!Note :] La propriété charset est requise lors de l'envoi de données vers une suite de rapports multioctet et ne doit jamais être utilisée avec une suite de rapports standard. L’utilisation de la propriété charSet avec une suite de rapports ISO standard peut provoquer une troncature de la variable ou une conversion inattendue des caractères.

La valeur de la propriété charSet doit correspondre à l’encodage de la page Web utilisé dans la balise META ou l’en-tête http, même si la syntaxe est légèrement différente. Bien que la balise META utilise un alias pour l’encodage, la valeur de charSet doit utiliser le nom recommandé (ou officiel) de l’encodage.

Le tableau suivant répertorie certains des encodages les plus fréquents avec leur nom recommandé et leurs alias.

| Nom recommandé | Alias |
|--- |--- |
| ISO-8859-1 | ISO_8859-1, CP819, latin1 |
| ISO-8859-2 | ISO_8859-2, latin2 |
| ISO-8859-5 | ISO_8859-5, cyrillic |
| Big5 | Big-5 |
| Shift_JIS | SJIS |

Comme il existe de nombreux encodages et alias, contactez votre conseiller en implémentation ou le service à la clientèle Adobe pour vérifier la valeur de charset si elle n'apparaît pas dans le tableau ci-dessus.

If a site has different web encodings on different pages, or a single JavaScript file is used for multiple sites, the charSet property can be set to a default value in the JavaScript file and then reset on specific pages as needed to override the default; for example, `s.charSet="UTF-8"` or `s.charSet="SJIS"`.

Toute valeur non vide du paramètre charSet provoque la conversion des données en UTF-8 pour le stockage. Tous les caractères de la plage 128 à 255 sont convertis dans la séquence UTF-8 sur deux octets correcte puis stockés. Ces caractères ne s’afficheront pas correctement dans une suite de rapports standard. La propriété charSet ne doit donc jamais être utilisée avec une suite de rapports standard.

De même, une valeur vide du paramètre charSet contourne le processus de conversion de données et tous les caractères de la plage 128 à 255 sont alors stockés sur un seul octet. Ces caractères ne s’affichent pas correctement dans une suite de rapports multioctet, puisque les codes mono-octets de ces caractères ne sont pas des valeurs UTF-8 correctes. Le paramètre charSet ne doit donc jamais être utilisé avec une suite de rapports standard. De plus, la valeur exacte d’encodage de la page Web doit être utilisée.

If the *`charSet`* variable contains an incorrect value, the data in all other variables are translated incorrectly. If JavaScript variables on your pages (e.g. *`pageName`*, [!UICONTROL prop1], or *`channel`*) contain only ASCII characters, *`charSet`* does not need to be defined. However, if the variables on your pages contain non-ASCII characters, the *`charSet`* variable must be populated.

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

<!-- 
currencycode.xml
-->

La variable détermine le taux de conversion à appliquer aux recettes. 

Toutes les valeurs monétaires sont stockées dans la devise de votre choix. Si cette devise est identique à celle qui est spécifiée dans *`currencyCode`* ou *`currencyCode`* est vide, aucune conversion n'est appliquée.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|--- |--- |--- |--- |
| N/D | cc | Conversion &gt; Achats &gt; Recettes Tous les rapports de conversion affichant des recettes ou des valeurs monétaires | "USD" |

Si votre site autorise les visiteurs à effectuer des achats dans plusieurs devises, vous devez utiliser la variable *`currencyCode`* pour vous assurer que les recettes sont stockées dans la devise appropriée. For example, if the base currency for your report suite is USD, and you sell an item for 40 Euros, you should populate the *`currencyCode`* with "EUR" on the HTML page. Dès que la collecte de données reçoit les données, elle utilise le taux de conversion en cours pour convertir le montant de 40 euros dans son équivalent en dollars.

Il est recommandé de renseigner la variable *`currencyCode`* sur la page HTML, au lieu du fichier JavaScript, si vous vendez des articles dans plusieurs devises. If you want to use your own conversion rates rather than the conversion rates used by Adobe, set the *`currencyCode`* to equal the base currency of your report suite. Convertissez ensuite toutes les recettes avant de les envoyer dans [!DNL Analytics].

La conversion de devise s’applique à la fois aux recettes et à tout événement monétaire. Il s’agit d’événements utilisés pour additionner des valeurs semblables à des recettes, telles que des taxes et des frais d’expédition. Les recettes et les événements monétaires sont spécifiés dans la chaîne « products ». Pour plus d’informations sur la chaîne « products », reportez-vous à la section [events](../../../implement/js-implementation/c-variables/page-variables.md#concept_FFD115543D54401B98FE683BD7D5B3FE). Pour en savoir plus sur le traitement des devises, accédez à la page [Prise en charge de plusieurs devises](https://marketing.adobe.com/resources/help/en_US/whitepapers/currency/).

**Syntaxe et valeurs possibles** {#section_7CD68F08AB4848EE9B0D19DCC3F1BECE}

```js
s.currencyCode="currency_code"
```

Seuls les codes de devise répertoriés dans la section [Prise en charge de plusieurs devises](https://marketing.adobe.com/resources/help/en_US/whitepapers/currency/) sont autorisés :

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

* If you notice surprisingly large amounts of revenue in reports, ensure that the *`currencyCode`* variable and base currency of the report suite are set correctly.
* *`currencyCode`* La variable n'est pas persistante, ce qui signifie que la variable doit être transmise dans la même demande d'image que les recettes ou autres mesures liées à la devise.
* Les événements monétaires doivent uniquement être utilisés pour les devises. Si vous devez comptabiliser des valeurs arbitraires ou dynamiques qui ne sont pas des devises, utilisez le type d’événement [!UICONTROL numeric].
* Lorsque la variable *`currencyCode`* est vide, aucune conversion n’est appliquée.

## s.cookieDomain {#concept_6164C39CF8BE4737A7EF1DE5A8376C1B}

<!-- 
cookiedomain.xml
-->

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set.

Commonly, `s.cookieDomainPeriods` is used to generate `s.cookieDomain` from `window.location.hostnam`e. Instead of using `s.cookieDomainPeriods`, you can explicitly set `s.cookieDomain` to what you want to use in your implementation. Par exemple, vous pourriez définir des cookies au nom complet de la page en utilisant :

`s.cookieDomain = window.location.hostname;`

## s.cookieDomainPeriods {#concept_F17A59C7D8F54F5897AD40980B6725EB}

<!-- 
cookiedomainperiods.xml
-->

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set by determining the number of periods in the domain of the page URL. Elle est également utilisée par certains modules externes pour déterminer le domaine correct afin de définir le cookie du module externe.

The default value for *`cookieDomainPeriods`* is "2". This is the value that is used if *`cookieDomainPeriods`* is omitted. For example, using the domain `www.mysite.com`, *`cookieDomainPeriods`* should be "2". For `www.mysite.co.jp`, *`cookieDomainPeriods`* should be "3".

If *`cookieDomainPeriods`* is set to "2" but the domain contains three periods, the JavaScript file attempts to set cookies on the domain suffix.

For example, if setting *`cookieDomainPeriods`* to "2" on the domain `www.mysite.co.jp`, the `s_cc` and `s_sq` cookies are created on the domain `co.jp`. Comme `co.jp` est un domaine incorrect, la plupart des navigateurs rejette ces cookies. Cela entraîne la perte de données de mise en correspondance des clics des visiteurs, et le rapport [!UICONTROL Profil du visiteur] &gt; [!UICONTROL Technologie] &gt; [!UICONTROL Cookies] indique que pratiquement 100 % des visiteurs ont rejeté les cookies propriétaires.

Si la variable *`cookieDomainPeriods`* est définie sur « 3 » et que le domaine contient uniquement deux points, le fichier JavaScript définit les cookie sur le sous-domaine du site. For example, if setting *`cookieDomainPeriods`* to "3" on the domain `www2.mysite.com`, the `s_cc` and `s_sq` cookies are created on the domain `www2.mysite.com`. When a visitor goes to another subdomain of your site (such as `www4.mysite.com`), all cookies set with `www2.mysite.com` cannot be read.

>[!NOTE]
>
>Do not include additional subdomains as part of *`cookieDomainPeriods`*. For example, `store.toys.mysite.com` would still have *`cookieDomainPeriods`* set to "2". Cette définition de la variable définit correctement les cookies sur le domaine racine [!DNL mysite.com]. Setting *`cookieDomainPeriods`* to "3" in this example would set cookies on the domain [!DNL toys.mysite.com], which has the same implications as the prior example.

See also [s.fpCookieDomainPeriods](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_0A25BD152B0744989E7C662A95448274).

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | CDP | Affecte plusieurs rapports, dans la mesure où il contrôle le mode de stockage et de traitement de l’identifiant visiteur. | "2" |

>[!NOTE]
>
>Certains services de cloud computing sont considérés comme des domaines de niveau supérieur qui n'autorisent pas l'écriture de cookies. (For example, `compute.amazonaws.com`, `*.herokuapp.com`, `*.googlecode.com`, and so on.) Si vous mettez ces services en œuvre, vous pourriez être affecté par le paramètre de vie privé d’Analytics qui retire les utilisateurs qui ont bloqué tous les cookies si vous n’avez pas configuré votre propre domaine (par exemple, si vous testez votre mise en œuvre). Dans ce cas, tout accès pour lequel le système a déterminé que les cookies étaient désactivés, non fonctionnels ou inaccessibles est exclu et n’apparaît donc pas dans les rapports.

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
* La variable *`cookieDomainPeriods`* était utilisée dans les implémentations obsolètes avant de définir *`trackingServer`* le cookie Identifiant visiteur. Though only present in outdated code, failure to correctly define *`cookieDomainPeriods`* in this circumstance puts your implementation at risk of data loss.

## s.fpCookieDomainPeriods {#concept_0A25BD152B0744989E7C662A95448274}

<!-- 
fpCookieDomainPeriods.xml
-->

La variable concerne les cookies définis par JavaScript (s_sq, s_cc, modules externes), qui sont intrinsèquement des cookies propriétaires, même si votre mise en œuvre utilise les domaines tiers 2o7.net ou omtrdc.net.

The *`fpCookieDomainPeriods`* variable should never be dynamically set . If you use *`cookieDomainPeriods`*, it is good practice to specify a value for *`fpCookieDomainPeriods`* as well. *`fpCookieDomainPeriods`* hérite de la *`cookieDomainPeriods`* valeur. Note that *`fpCookieDomainPeriods`* does not affect the domain on which the visitor ID cookie is set, even if your implementation treats this as a first-party cookie.

The name " *`fpCookieDomainPeriods`*" refers to the number of periods (".") dans le domaine, lorsque celui-ci commence par « www ». For example, `www.mysite.com` contains two periods, while `www.mysite.co.jp` contains three periods. Another way to describe the variable is the number of sections in the main domain of the site (two for `mysite.com` and three for `mysite.co.jp`).

[!DNL AppMeasurement] Le fichier JavaScript utilise la *`fpCookieDomainPeriods`* variable pour déterminer le domaine avec lequel définir des cookies propriétaires autres que le cookie [!UICONTROL identifiant visiteur] (s_ vi). Au moins deux cookies sont affectés par cette variable, dont s_sq et s_cc (utilisés respectivement pour la mise en correspondance des clics des visiteurs et pour la vérification de cookies). Les cookies utilisés par des modules externes, tels que [!UICONTROL getValOnce] sont également affectés.

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

<!-- 
cookielifetime.xml
-->

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

*`cookieLifetime`* affecte [!DNL Analytics] le suivi. If, for example, *`cookieLifetime`* is two days, then monthly, quarterly, and yearly unique visitor reports will be incorrect. Soyez prudent lors de la définition de la variable *`cookieLifetime`*.

## s.doPlugins {#concept_676EAE4FAFCF4B018876390FC874EFDA}

<!-- 
doPlugins.xml
-->

La variable est une référence à la fonction . Elle permet d’appeler la fonction à l’emplacement approprié dans le fichier JavaScript.

The *`s_doPlugins`* function is called each time any of the following occurs:

* *`t()`* La fonction est appelée
* *`tl()`* La fonction est appelée
* Clic sur un lien de sortie ou de téléchargement
* Clic sur un élément de page suivi par la mise en correspondance des clics des visiteurs

La fonction *`doPlugins`* sert à exécuter des routines personnalisées dans le but de rassembler ou de modifier des données. If you are using an object name other than "s," make sure that the *`s_doPlugins`* is renamed appropriately. For example, if your object name is s_mc, the *`s_doPlugins`* function should be called s_mc_doPlugins.

**Syntaxe et valeurs possibles** {#section_5CFB94598521455E80947964A306EA89}

*`s_doPlugins`* La fonction ne doit pas être entre guillemets et *`doPlugins`* doit toujours être affectée au nom exact de *`s_doPlugins`* la fonction (si cette fonction est renommée).

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

* Le partage de contenu avec d’autres clients ou l’extraction de contenu de ces mêmes clients est la seule raison pouvant justifier le changement de nom d’un objet (de s en s_mc, par exemple). En renommant la fonction *`s_doPlugins`* à [!UICONTROL s_ mc_ doplugins] garantit que le fichier JavaScript d'un autre client ne remplace pas votre *`doPlugins`* fonction.

* If you unexpectedly start pulling in content from another Adobe customer, and your *`s_doPlugins`* function is being overwritten, it is possible to simply rename the *`s_doPlugins`* function without changing the object name. La meilleure solution consiste certes à utiliser un nom d’objet différent de celui des autres fichiers JavaScript de la même page, mais cela n’est pas obligatoire.

## s. registerpretrackcallback et s. registerposttrackcallback

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

<!-- 
trackDownloadLinks.xml
-->

Définissez la variable sur « true » si vous souhaitez effectuer le suivi de liens vers des fichiers téléchargeables de votre site.

If *`trackDownloadLinks`* is 'true,' *`linkDownloadFileTypes`* is used to determine which links are downloadable files.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | True |

La variable *`trackDownloadLinks`* ne doit être définie sur « false » que si le site ne comporte aucun lien vers des fichiers téléchargeables ou si vous n’êtes pas intéressé par le suivi des clics effectués sur des fichiers de ce type. If *`trackDownloadLinks`* is 'true,' when a file download link is clicked, data is immediately sent to [!DNL Analytics]. Les données envoyées avec un lien de téléchargement sont notamment l’URL de téléchargement du lien et les données de mise en correspondance des clics des visiteurs relatives à ce lien. Si la variable *`trackDownloadLinks`* est définie sur « false », il est probable que les données de mise en correspondance des clics des visiteurs pour les liens pointant vers des fichiers téléchargeables de votre site soient sous-estimées.

**Syntaxe et valeurs possibles** {#section_828492CC2A144BC68D18C30CF397EEFC}

La variable *`trackDownloadLinks`doit être définie sur « true » ou « false ».*

**Exemples** {#section_BE2FA1873EBD4C5CA95E98B922B10280}

```js
s.trackDownloadLinks=true 
```

```js
s.trackDownloadLinks=false
```

**Paramètres de configuration** {#section_9A5F69966BAF433A8DA2BCF655A652D1}

Aucune

**Pièges, questions et conseils** {#section_B3764520D81143968F96CB69AADD457F}

* When *`trackDownloadLinks`* is 'false,' links that people use to download files on your site are likely to be under reported in visitor click map.
* When *`trackDownloadLinks`* is 'true,' data is sent each time a visitor clicks a file download link.

## s.trackExternalLinks {#concept_E1321318696841648A54CF77F6C4A7AF}

<!-- 
trackExternalLinks.xml
-->

Si la valeur est true, et est utilisée pour déterminer si un lien sur lequel l'utilisateur a cliqué est un lien de sortie.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | True |

La variable *`trackExternalLinks`* ne doit être définie sur « false » que si votre site ne comporte aucun lien de sortie ou si vous n’êtes pas intéressé par le suivi des clics effectués sur ces liens. On désigne sous le nom de lien de sortie tout lien qui permet à un visiteur de quitter votre site. Si la variable *`trackExternalLinks`* est définie sur « true », lorsque vous cliquez sur un lien de sortie, les données de suivi sont immédiatement envoyées. Les données envoyées avec un lien de sortie sont notamment l’URL et le nom du lien, ainsi que les données de mise en correspondance des clics des visiteurs relatives à ce lien. Si la variable *`trackExternalLinks`* est définie sur « false », il est probable que les données de mise en correspondance des clics des visiteurs pour les liens de sortie de votre site soient sous-estimées.

**Syntaxe et valeurs possibles** {#section_267748949A7544658E1D838AAEF964B2}

La variable *`trackExternalLinks`doit être définie sur « true » ou « false ».*

```js
s.trackExternalLinks=true|false
```

**Exemples** {#section_EF18DB05884240F5B5062631E68E10A7}

```js
s.trackExternalLinks=true 
```

```js
s.trackExternalLinks=false
```

**Paramètres de configuration** {#section_C8748CFE36324FAFB14C23E3E1FB5082}

Aucune

**Pièges, questions et conseils** {#section_FE2C3AF17DA24EA8A944BF1D394FB5BC}

* When *`trackExternalLinks`* is 'false,' links that take people away from your site are likely to be under reported in visitor click map.
* When *`trackExternalLinks`* is 'true,' data is sent each time a visitor clicks on an exit link (before link target loads).

## s.trackInlineStats {#concept_E3A811D9761E4917935F6CD9059C7FCC}

<!-- 
trackInlineStats.xml
-->

La variable détermine si les données ClickMap sont collectées.

If *`trackInlineStats`* is 'true,' data about the page and link clicked are stored in a cookie called s_sq. If 'false,' s_sq will have a value of "[[B]]," which is considered null.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | ClickMap | False |

**Syntaxe et valeurs possibles** {#section_46B2C1DD0D104A01A9C239929420CD90}

```js
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

<!-- 
linkDownloadFileTypes.xml
-->

La variable est une liste d’extensions de fichiers séparées par des virgules.

Si votre site contient des liens pointant vers des fichiers associés à l’une de ces extensions, les URL de ces liens s’afficheront dans le rapport [!UICONTROL Téléchargements de fichiers]

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|--- |--- |--- |--- |
| N/D | N/D | Trafic &gt; Trafic du site &gt; Téléchargements de fichiers | "exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls" |

La variable *`linkDownloadFileTypes`* n'est utile que lorsqu' *`trackDownloadLinks`* elle est définie sur True.

Seuls les clics avec le bouton gauche effectués sur un lien sont comptabilisés dans le rapport [!UICONTROL Téléchargements de fichiers]. Tous les téléchargements de fichiers qui démarrent automatiquement lors du chargement d’une page, ou qui sont uniquement téléchargés à la suite d’une redirection, ne sont pas comptabilisés dans le rapport [!UICONTROL Téléchargements de fichiers]. Lorsque vous cliquez sur un fichier avec le bouton droit et sélectionnez ensuite l’option « Enregistrer la cible sous... », il n’est pas comptabilisé dans le rapport [!UICONTROL Téléchargements de fichiers].

La variable *`linkDownloadFileTypes`* peut être utilisée pour effectuer le suivi des clics vers des flux RSS. If you have links to RSS feeds with a .xml or other extension, appending ",xml" to the *`linkDownloadFileTypes`* list allows you to see how often each RSS link is clicked.

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

<!-- 
linkInternalFilters.xml
-->

La variable est utilisée pour déterminer les liens de votre site qui sont des liens de sortie.

Il s’agit d’une liste, séparée par des virgules, de filtres représentant les liens qui font partie du site.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | Chemins &gt; Entrées et sorties &gt; Liens de sortie |  |

>[!NOTE]
>
>Nous avons précédemment suggéré de définir linkinternalfilters sur javascript :. Toutefois, il en résultait que tous les domaines étaient considérés comme externes, y compris le domaine actuel dans lequel réside la balise. Si vous voulez que plusieurs domaines soient considérés comme internes, vous pouvez les ajouter, tel qu’illustré dans les exemples ci-dessous.

The *`linkInternalFilters`* variable is used to determine whether a link is an exit link, which is defined as any link that takes a visitor away from your site. Le lien apparaît dans le rapport des liens de sortie, que la fenêtre cible soit une fenêtre contextuelle ou qu’il s’agisse de la fenêtre existante. Le suivi des liens de sortie est effectué uniquement si *`trackExternalLinks`* est définie sur `"true"`. (Voir [Suivi des liens](https://marketing.adobe.com/resources/help/en_US/dtm/link_tracking.html) dans la documentation relative à Dynamic Tag Management pour plus d’informations sur la façon dont Dynamic Tag Management gère les liens de sortie.) The filters in *`linkInternalFilters`* are not case-sensitive.

The list of filters in *`linkInternalFilters`* applies to the domain and path of any link by default. If *`linkLeaveQueryString`* is set to `"true"`, then the filters apply to the entire URL (domain, path, and query string). Les filtres sont toujours appliqués au chemin absolu de l’URL, même si un chemin relatif est utilisé comme valeur href.

Sachez que tous les domaines de votre site (ainsi que tout partenaire qui utilise votre fichier JavaScript) sont inclus dans *`linkInternalFilters`*. Si tous les domaines ne sont pas inclus dans la liste, tous les liens qui y sont associés sont considérés comme des liens de sortie, ce qui a pour effet d’augmenter le nombre d’appels au serveur envoyés. If you would like multiple domains or companies to use a single [!DNL AppMeasurement] for JavaScript file, you may consider populating *`linkInternalFilters`* on the page, overriding the value specified in the JavaScript file. S’il existe des domaines mineurs qui redirigent immédiatement vers votre domaine principal, ils ne doivent pas nécessairement être inclus dans la liste.

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

*`linkInternalFilters`* La variable est une liste de caractères ASCII séparés par des virgules. Aucun espace n’est autorisé.

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

<!-- 
linkLeaveQueryString.xml
-->

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

<!-- 
linkTrackVars.xml
-->

La variable est une liste de variables séparées par des virgules qui sont envoyées avec des liens personnalisés, de téléchargement et de sortie.

If *`linkTrackVars`* is set to "", all variables that have values are sent with link data. To avoid inflation of instances or page views associated with other variables, Adobe recommends populating *`linkTrackVars`* and *`linkTrackEvents`* in the [!UICONTROL onClick] event of a link that is used for link tracking.

Toutes les variables qui doivent être envoyées avec des données de lien (liens personnalisés, de téléchargement et de sortie) doivent être répertoriées dans *`linkTrackVars`*. If *`linkTrackEvents`* is used, *`linkTrackVars`* should contain "events."

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | Quelconque | "Aucun" |

Lorsque vous renseignez *`linkTrackVars`*, n'utilisez pas le préfixe s.'pour les variables. For example, instead of populating *`linkTrackVars`* with "s.prop1," you should populate it with "prop1." The following example illustrates how *`linkTrackVars`* should be used.

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

Il se peut que *`linkTrackVars`* ne peut contenir que des variables envoyées à [!DNL Analytics], à savoir : *`events`**`campaign`**`purchaseID`*, *`products`*[!UICONTROL Evar 1-75], [!UICONTROL prop 1-75], [!UICONTROL hier 1-5]*`channel`**`server`**`state`**`zip`*, and *`pageType`*.

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
* If *`linkTrackEvents`* is used, *`linkTrackVars`* must contain "events."

* N’utilisez pas le préfixe « s. » ou « s_objectname. » pour les variables.

## s.linkTrackEvents {#concept_34D029097A674D0A97690C9569590EF5}

<!-- 
linkTrackEvents.xml
-->

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

To avoid confusion and potential problems, Adobe recommends populating *`linkTrackVars`* and *`linkTrackEvents`* in the [!UICONTROL onClick] event of a link that is used for link tracking.

The *`linkTrackEvents`* variable contains the events that should be sent with [!UICONTROL custom], [!UICONTROL download], and [!UICONTROL exit] links. This variable is only considered if *`linkTrackVars`* contains "events."

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

* The JavaScript file only uses *`linkTrackEvents`* if *`linkTrackVars`* contains the "events" variable. "events" should be included in *`linkTrackVars`* only when *`linkTrackEvents`* is defined.

* Beware if an event is fired on a page, and is listed in *`linkTrackEvents`*. That event is recorded again with any [!UICONTROL exit], [!UICONTROL download], or [!UICONTROL custom] links unless the events variable is reset prior to that event (in the [!UICONTROL onClick] of a link or after the call to the *`t()`* function).

* If *`linkTrackEvents`* contains spaces between event names, the events are not recorded.

## s.linkExternalFilters {#concept_92A59169DCE443EBAE81A373B27BB6DD}

<!-- 
linkExternalFilters.xml
-->

Si votre site contient plusieurs liens vers des sites externes et que vous ne souhaitez pas suivre tous les liens de sortie, vous pouvez utiliser la variable pour créer des rapports sur un sous-ensemble spécifique de liens de sortie.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | Chemins &gt; Entrées et sorties &gt; Liens de sortie | "" |

La variable *`linkExternalFilters`* est une variable facultative utilisée conjointement pour *`linkInternalFilters`* déterminer si un lien est un lien de sortie. On désigne sous le nom de lien de sortie tout lien qui permet à un visiteur de quitter votre site. Le lien apparaît dans le rapport des liens de sortie, que la fenêtre cible soit une fenêtre contextuelle ou qu’il s’agisse de la fenêtre existante. Le suivi des liens de sortie est effectué uniquement si la variable *`trackExternalLinks`* est définie sur « true ». The filters in *`linkExternalFilters`* and *`linkInternalFilters`* are case insensitive.

>[!NOTE]
>
>If you don't want to use *`linkExternalFilters`*, delete it or set it to "".

The filters list in *`linkExternalFilters`* and *`linkInternalFilters`* apply to the domain and path of any link by default. If *`linkLeaveQueryString`* is set to 'true,' the filters apply to the entire URL (domain, path, and query string). Ces filtres sont toujours appliqués au chemin absolu de l’URL, même si un chemin relatif est utilisé comme valeur href.

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

*`linkExternalFilters`* La variable est une liste de caractères ASCII séparés par des virgules. Aucun espace n’est autorisé.

```js
s.linkExternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

Toute partie d’une URL peut être incluse dans la variable *`linkExternalFilters`*, séparées par des virgules.

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

* Using *`linkExternalFilters`* can result in fewer links on your site being exit links. Do not use this variable in place of *`linkInternalFilters`* to force internal links to become exit links.

* If *`linkExternalFilters`* should be applied to the query string of a link, make sure *`linkLeaveQueryString`* is set to 'true.' See [linkLeaveQueryString](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_118C280E29394DB5A16DBBF41EB4D742) before setting to `"true"`.

* To disable exit link tracking, set *`trackExternalLinks`* to `"false"`.

## s.usePlugins {#concept_81836470A25C41228CE04084565F667D}

<!-- 
s_usePlugins.xml
-->

If the  function is available and contains useful code, [!UICONTROL s_usePlugins] should be set to 'true.'

When [!UICONTROL usePlugins] is 'true,' the *`s_doPlugins`* function is called prior to each image request.

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

The [!UICONTROL usePlugins] variable should only be false (or not declared) if the *`s_doPlugins`* function is not declared in your JavaScript file.

**Paramètres de configuration** {#section_DFD41717134147E988B6AFC7DE5BB9E3}

Aucune