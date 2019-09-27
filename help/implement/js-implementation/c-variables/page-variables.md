---
description: Les variables de page renseignent directement un rapport (pageName, props de liste, variables de liste, etc.).
keywords: Mise en œuvre d’Analytics
seo-description: Les variables de page renseignent directement un rapport (pageName, props de liste, variables de liste, etc.).
seo-title: Variables de page
solution: Analytics
subtopic: Variables
title: Variables de page
topic: Développeur et mise en œuvre
uuid: 2578eddd-74db-4a8a-96f2-d0289ec1826b
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Variables de page

Les variables de page renseignent directement un rapport (pageName, props de liste, variables de liste, etc.).

## browserHeight {#concept_DB87062001824369A56AA1E7969EC02A}

La variable affiche la hauteur de la fenêtre du navigateur.

<!-- 
browserheight.xml
-->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>Cette variable ne doit être lue que et jamais définie.

Vous pouvez lire ces valeurs et les copier dans props/eVars, mais vous ne pouvez, en aucun cas, les modifier. Cette variable est apparue avec la version H.11 du fichier JavaScript.

**Paramètres**

<table id="table_94598A2204CF42FF9DD14D353D5C0468"> 
 <thead> 
  <tr> 
   <th class="entry"> Paramètre de requête </th> 
   <th class="entry"> Valeur </th> 
   <th class="entry"> Exemple </th> 
   <th class="entry"> Rapports concernés </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>bh </p> </td> 
   <td> <p>Entier positif </p> </td> 
   <td> <p>865 </p> </td> 
   <td> <p>Trafic &gt; Technologie &gt; Hauteur du navigateur </p> </td> 
  </tr> 
 </tbody> 
</table>

## browserWidth {#concept_BA0C4C2D655D41A4AEF059E21E4A55A2}

La variable affiche la largeur de la fenêtre du navigateur.

<!-- 

browserwidth.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>Cette variable ne doit être lue que et jamais définie.

Vous pouvez lire ces valeurs et les copier dans props/eVars, mais vous ne pouvez, en aucun cas, les modifier. Cette variable est apparue avec la version H.11 du fichier JavaScript.

**Paramètres**

<table id="table_B70F279A8CD240328520E5BD889806BD"> 
 <tbody> 
  <tr> 
   <td> <p> <b>Paramètre de requête</b> </p> </td> 
   <td> <p> <b>Valeur</b> </p> </td> 
   <td> <p> <b>Exemple</b> </p> </td> 
   <td> <p> <b>Rapports concernés</b> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>bw </p> </td> 
   <td> <p>Entier positif </p> </td> 
   <td> <p>1179 </p> </td> 
   <td> <p>Trafic &gt; Technologie &gt; Largeur du navigateur </p> </td> 
  </tr> 
 </tbody> 
</table>

## campaign {#concept_C7BF7B8A69D048A6AB482052A98A91F8}

La variable identifie les campagnes marketing utilisées pour amener les visiteurs sur votre site. The value of  is usually taken from a query string parameter.

<!-- 

campaign.xml

 -->

**Paramètres**

<table id="table_A35175678B6C4D3D86287199AFBE6803"> 
 <thead> 
  <tr> 
   <th class="entry"> Taille maximale </th> 
   <th class="entry"> Paramètre du débogueur </th> 
   <th class="entry"> Rapports renseignés </th> 
   <th class="entry"> Valeur par défaut </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>255 octets </p> </td> 
   <td> <p>v0 </p> </td> 
   <td> <p>Conversion &gt; Campagnes &gt; Code de suivi </p> </td> 
   <td> <p>"" </p> </td> 
  </tr> 
 </tbody> 
</table>

Chaque élément d’une campagne marketing doit être associé à un code de suivi unique. Par exemple, le code de suivi 112233 peut être associé à un mot-clé de moteur de recherche payante. Lorsqu’un internaute clique sur le mot-clé ayant le code de suivi 112233 et est redirigé vers le site Web correspondant, la variable *`campaign`* enregistre le code de suivi.

There are two main ways to populate the *`campaign`* variable:

* Le module externe [!UICONTROL getQueryParam], utilisé dans le fichier JavaScript, récupère un paramètre de chaîne de requête de l’URL. Pour plus d’informations sur le module externe [!UICONTROL getQueryParam], reportez-vous à la section [Modules externes de mise en œuvre](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

* Assign a value to the  variable in the HTML on the Web page.*`campaign`*

With either method of populating the  variable, the Back button traffic may inflate the actual number of click-throughs from a campaign element.*`campaign`*

Par exemple, un visiteur parvient sur votre site en cliquant sur un mot-clé de recherche payante. Lorsqu’il arrive sur la page d’entrée, l’URL contient un paramètre de chaîne de requête qui identifie le code de suivi du mot-clé. Il clique ensuite sur un lien pointant vers une autre page, puis il clique immédiatement sur le bouton Précédent pour revenir sur la page d’entrée. Lors de sa deuxième visite sur la page d’entrée, l’URL contenant le paramètre de chaîne de requête identifie à nouveau le code de suivi. Un deuxième clic publicitaire est alors enregistré, ce qui a pour effet de gonfler artificiellement le nombre des clics.

Pour éviter l’accroissement anarchique des clics publicitaires, Adobe conseille d’utiliser le module externe [!UICONTROL getValOnce] de telle sorte que chaque clic publicitaire soit comptabilisé une seule fois par session. Pour plus d’informations sur le module externe [!UICONTROL getValOnce], reportez-vous à la section [Modules externes de mise en œuvre](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

**Syntaxe et valeurs possibles** {#section_91A141841A6D4711A1EE08A6145A301D}

```js
s.campaign="112233"
```

The *`campaign`* variable has the same limitations as all other variables. Adobe conseille de limiter la valeur aux caractères ASCII standard.

**Respect de la casse** {#section_112A9A0F886148B6BEF9A7C94BE0A36F}

Les eVars ne sont pas sensibles à la casse, mais elles respectent la mise en majuscules de la première occurrence. Ainsi, si la première instance de la variable eVar1 est définie sur « Connecté », mais que toutes les instances suivantes sont transmises sous la forme « connecté », les rapports affichent toujours « Connecté » comme valeur de l’eVar.

**Exemples** {#section_705A25D05F6848E29C78320247AECB5F}

```js
s.campaign="112233"
```

```js
s.campaign=s.getQueryParam('cid');
```

**Paramètres de configuration** {#section_4083F281968443169EAF8C0E8529D7BC}

Chaque valeur de campagne reste active pour un utilisateur, et reçoit du crédit pour les événements de succès et les activités de cet utilisateur jusqu’à son expiration. Vous pouvez modifier l’expiration de la variable campaign dans Admin Console.

**Pièges, questions et conseils** {#section_94B5C4BF9DE84BA3A16F9E9E9D197F0C}

* Pour éviter l’accroissement anarchique des clics publicitaires, utilisez le module externe [!UICONTROL getValOnce], de telle sorte que chaque clic publicitaire soit comptabilisé une seule fois par session. Pour plus d’informations sur le module externe [!UICONTROL getValOnce], reportez-vous à la section [Modules externes de mise en œuvre](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

* Pour plus d’informations sur le suivi des campagnes marketing et les achats de mots-clés, reportez-vous à la section [Campagnes](https://marketing.adobe.com/resources/help/en_US/reference/campaign.html).
* Utilisez le [!DNL DigitalPulse Debugger] pour connaître la valeur réelle des campagnes (v0 dans le débogueur). Si v0 n’apparaît pas dans le débogueur, aucune donnée de campagne n’est enregistrée pour cette page.

## marketing {#concept_C7770B8C15724A99B10F8F468AF82D0D}

La variable est généralement utilisée pour identifier une section de votre site. 

<!-- 

channel.xml

 -->

Par exemple, un site commercial peut présenter des sections telles que « Electronique », « Jouets » ou « Vêtements ». Un site de médias peut présenter des sections comme « Infos », « Sports » ou encore « Affaires ».

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| 100 octets | CH | Contenu du site &gt; Sections du site | "" |

Adobe recommande de renseigner la variable channel sur chaque page. Vous pouvez également activer une corrélation entre les variables *`channel`* et [!UICONTROL page name].

When sections have one or more levels of subsections, you can show those sections in the *`channel`* variable or use separate variables to identify levels.

**Syntaxe et valeurs possibles** {#section_ED90592730B64242A737F4090F1DCEE4}

```js
s.channel="value"
```

The *`channel`* variable has no extra limitations on its values.

**Exemples** {#section_2527B2BB1CFD46CB952178ABF7A9028A}

```js
s.channel="Electronics"
```

```js
s.channel="Media"
```

**Pièges, questions et conseils** {#section_61941D5E4E644B59A267A4F44FD5DE8C}

If your site contains multiple levels, you can use the *`hierarchy`* or another variable to designate those levels. The *`channel`* value does not persist, but the success events fired on the same page are attributed to the *`channel`* value.

## colorDepth {#concept_756516E181F449B996DA9CC5A53FFA3D}

La variable sert à afficher le nombre de bits utilisés pour l’affichage de la couleur sur chaque pixel de l’écran.

<!-- 

colordepth.xml

 -->

Par exemple, la valeur 32 représente 32 bits de couleur à l’écran. Cette variable est complétée après le code de page et avant l’exécution de *`doPlugins`*.

>[!NOTE]
>
>Cette variable ne doit être lue que et jamais définie.

Vous pouvez lire ces valeurs et les copier dans `props/eVars`, mais vous ne pouvez, en aucun cas, les modifier. Cette variable est apparue avec la version H.11 du fichier JavaScript.

| Paramètre de requête | Valeur | Exemple | Rapports concernés |
|---|---|---|---|
| c | 8, 16 et 32 | 32 | Trafic &gt; Technologie &gt; Profondeur de couleur d’écran |

## connectionType {#concept_2F98ECB8BB3D490F834F274EFF02860E}

Dans Internet Explorer, la variable indique si le navigateur est configuré sur une connexion LAN (réseau local) ou modem.

<!-- 

conntype.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>This variable should only be read and never set.

Vous pouvez lire ces valeurs et les copier dans `props/eVars`, mais vous ne pouvez, en aucun cas, les modifier. Cette variable est apparue avec la version H.11 du fichier JavaScript.

| Paramètre de requête | Valeur | Exemple | Rapports concernés |
|---|---|---|---|
| ct | lan ou modem | lan | Trafic &gt; Technologie &gt; Type de connexion |

## cookiesEnabled {#concept_DF5B37E38D0D4F6DB910F419F92467ED}

La variable indique si un cookie de session propriétaire a pu être défini par JavaScript.

<!-- 

cookiesenabled.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>This variable should only be read and never set.

Vous pouvez lire ces valeurs et les copier dans `props/eVars`, mais vous ne pouvez, en aucun cas, les modifier. Cette variable est apparue avec la version H.11 du fichier JavaScript.

| Paramètre de requête | Valeur | Exemple |
|---|---|---|
| k | Y ou N | Y |

## dc {#concept_ECE6C83376704B3C84A920EFDD338A31}

(Obsolète) La variable vous permet de sélectionner le centre de données auquel vos données sont envoyées.

<!-- 

dc.xml

 -->

>[!NOTE]
>
>La variable dc est obsolète. Vous devez définir *`trackingServer`pour toutes les implémentations sur la valeur générée par le Gestionnaire de code dans le fichier s_code.js.*

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | 112 |

Le centre de données est identifié dans la variable *`dc`* afin de correspondre à [!UICONTROL ActionSource].

## eVarN {#concept_74FFDDB44B5344E18ABC6F2F99DF4649}

Les variables [!UICONTROL eVar] sont utilisées pour créer des rapports personnalisés.

<!-- 

eVarN.xml

 -->

Lorsqu’une variable eVar est définie sur une valeur pour un visiteur, la valeur est mémorisée jusqu’à son expiration. Tout événement de succès auquel est associé un visiteur alors que la valeur eVar est active est comptabilisé dans cette dernière.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| 255 octets | V1-v75 ( or v100 or v250)[](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28) | Conversion personnalisée | "" |

**Expiration**{#section_6DB5882B960D4660AE248B91B76883C4}

Les [!UICONTROL eVars] arrivent à expiration après une période que vous avez spécifiée. Une fois arrivées à expiration, elles ne reçoivent plus de crédit pour les événements de succès. Vous pouvez également configurer les eVars pour qu’elles arrivent à expiration lors d’un événement de succès. Ainsi, dans le cas d’une promotion interne qui arrive à expiration à la fin de la visite, celle-ci ne reçoit du crédit que pour les achats ou inscriptions qui ont lieu au cours de la visite pendant laquelle ils ont été activés.

Il existe deux méthodes pour faire expirer une eVar :

* Vous pouvez la configurer de manière à ce qu’elle arrive à expiration après une période ou un événement spécifique.
* Vous pouvez forcer l’expiration d’une eVar, ce qui se révèle utile pour redéfinir son objectif.

Si une eVar est utilisée en mai pour refléter les promotions internes et expire après 21 jours, et qu’en juin elle est utilisée pour capturer les mots-clés de recherche interne, le 1er juin, vous devez forcer l’expiration de la variable ou la réinitialiser. De cette manière, les valeurs de promotion interne ne figureront pas dans les rapports du mois de juin.

**Respect de la casse** {#section_6E9145B7FCC2438E95BB35AAE3857412}

Les eVars ne sont pas sensibles à la casse, mais elles respectent la mise en majuscules de la première occurrence. Ainsi, si la première instance de la variable eVar1 est définie sur « Connecté », mais que toutes les instances suivantes sont transmises sous la forme « connecté », les rapports affichent toujours « Connecté » comme valeur de l’eVar.

**Compteurs**{#section_D8403F0C175E4BC9BE4F2E794B1F4D33}

Bien que les eVars soient généralement utilisées pour contenir des valeurs de chaîne, elles peuvent également être configurées pour faire office de compteurs. Elles s’avèrent particulièrement utiles sous cette forme lorsque vous essayez de comptabiliser le nombre d’actions qu’un utilisateur effectue avant un événement. Vous pouvez, par exemple, utiliser une eVar pour capturer le nombre de recherches internes avant un achat. Chaque fois qu’un visiteur effectue une recherche, l’eVar doit contenir une valeur « +1 ». Si un utilisateur effectue quatre recherches avant un achat, une instance est affichée pour chaque compte total : 1.00, 2.00, 3.00 et 4.00. Cependant, seule la valeur 4.00 reçoit du crédit pour l’événement d’achat (mesures Commandes et Recettes). Seuls les nombres positifs sont autorisés comme valeurs d’un compteur eVar.

**Sous-relations** {#section_2BEABBBC735241F4BA42E74D19B5AEE0}

La possibilité de ventiler un rapport [!UICONTROL eVar personnalisée] en fonction d’un autre constitue une exigence courante pour ce type de rapport. Par exemple, si une eVar contient le genre, et qu’une autre contient le salaire, vous pouvez poser la question suivante : parmi les visiteurs de sexe féminin, quel est le montant des recettes généré par les femmes dont le revenu annuel est supérieur à 50 000 euros. Toute eVar en sous-relation permet ce type de ventilation dans les rapports. Par exemple, si les sous-relations complètes sont activées dans l’eVar de genre, tous les autres rapports eVar personnalisés peuvent être ventilés par genre, et inversement. Pour qu’il soit possible d’afficher la sous-relation entre deux rapports, les sous-relations complètes doivent simplement êtres activées sur l’un d’eux. Par défaut, les rapports [!UICONTROL Campagnes], [!UICONTROL Produits] et [!UICONTROL Catégorie] disposent de sous-relations complètes (toute eVar peut être ventilée par campagnes ou par produits).

**Syntaxe et valeurs possibles** {#section_BD46438B14F3488FB9AC42994C317B06}

While eVars may be renamed, they should always be referred to in the JavaScript file by eVarX, where X is a number between 1 and 75 ( [or 100, or 250](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28)).

```js
s.eVarX="value"
```

Les eVars présentent les mêmes limites que toutes les autres variables, sauf lorsqu’elles sont utilisées comme compteur. Si l’eVar est un « compteur », il est prévu qu’elle reçoive des valeurs numériques telles que « 1 » ou « 2,5 ». S’il y a plus de deux décimales, le compteur eVar arrondit la valeur à deux décimales. Un compteur eVar ne peut pas contenir de nombres négatifs.

**Exemples** {#section_B37F4B0D56734DA3AB02BB218825BA4E}

```js
s.eVar1="logged in"
```

```js
s.eVar23="internal spring promo 4"
```

**Paramètres de configuration** {#section_BD1FE63001C84D3DB69F3DEE243960B6}

eVars can be configured in [!UICONTROL Analytics &gt; Admin &gt; Report Suites &gt; Edit Settings &gt; Conversion &gt; Conversion Variables]. Toutes peuvent être configurées avec un [!UICONTROL Nom], un [!UICONTROL Type], une [!UICONTROL Affectation], un paramètre [!UICONTROL Expire après ]ou [!UICONTROL Réintialiser]. Chaque paramètre de configuration est décrit séparément

<table id="table_5C524B71520849FA8A9A6B79A3EE77C9"> 
 <thead> 
  <tr> 
   <th class="entry"> Paramètre </th> 
   <th class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Nom </td> 
   <td> Permet de renommer un rapport eVar dans <span class="keyword">Analytics </span>. <p>L’eVar doit toujours être référencée sous la forme s.eVarX dans le code JavaScript, quel que soit le nom attribué au rapport dans <span class="keyword">Analytics </span>. </p> </td> 
  </tr> 
  <tr> 
   <td> Type </td> 
   <td> Permet d’indiquer si l’eVar est une chaîne de texte ou un compteur. </td> 
  </tr> 
  <tr> 
   <td> Affectation </td> 
   <td> Permet de configurer la valeur de l’eVar qui reçoit du crédit pour les événements de succès. <p>Si le paramètre Affectation est défini sur « Le dernier », B reçoit du crédit </p> <p>Si le paramètre Affectation est défini sur « Valeur d’origine (première) », A reçoit du crédit. </p> <p>Si le paramètre Affectation est défini sur « Linéaire », A et B reçoivent tous deux du crédit pour la moitié de la valeur d’achat. </p> </td> 
  </tr> 
  <tr> 
   <td> Expire après </td> 
   <td> Permet de déterminer si une eVar arrive à expiration lors d’un événement spécifique, tel qu’un achat, ou après une période personnalisée ou prédéfinie. </td> 
  </tr> 
  <tr> 
   <td> Réinitialiser </td> 
   <td> Lorsque vous cochez la case <span class="wintitle">Réinitialiser</span> pour une eVar et cliquez sur <span class="wintitle">Enregistrer</span> en bas de la page, toutes les valeurs de l’eVar en question expirent immédiatement. Ensuite, seules les nouvelles valeurs de l’eVar reçoivent du crédit pour les événements de succès. </td> 
  </tr> 
 </tbody> 
</table>

**Pièges, questions et conseils** {#section_DA6912C802E445F986C6DE4234C6C737}

* Contrairement aux variables [!UICONTROL prop], les variables eVar ne sont pas autorisées comme listes de valeurs délimitées. Si vous renseignez une liste de valeurs dans une eVar (« un,deux,trois », par exemple), cette chaîne apparaît à l’identique dans les rapports.
* Les compteurs eVar ne peuvent pas contenir de nombres négatifs.

## Événements {#concept_FFD115543D54401B98FE683BD7D5B3FE}

La variable sert à enregistrer des événements de succès courants de panier, ainsi que des événements de succès personnalisés.

<!-- 

events.xml

 -->

<table id="table_9EB9D08C80544CD68C4B1A2012440472"> 
 <thead> 
  <tr> 
   <th class="entry"> Taille maximale </th> 
   <th class="entry"> Paramètre du débogueur </th> 
   <th class="entry"> Rapports renseignés </th> 
   <th class="entry"> Valeur par défaut </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Sans limite </td> 
   <td> events </td> 
   <td> <p>Événements du panier </p> <p>Événements personnalisés </p> </td> 
   <td> N/D </td> 
  </tr> 
 </tbody> 
</table>

Un [!UICONTROL événement] doit être considéré comme un « jalon » d’un site. Les événements de succès sont le plus souvent renseignés sur la page de confirmation finale d’un processus tel qu’une inscription ou l’abonnement à un bulletin d’information. Les événements personnalisés sont définis en renseignant les variables events avec les valeurs littérales définies dans la section Valeurs possibles ci-dessous.

Par défaut, les événements de succès sont configurés en tant qu’événements « *compteur* ». Les événements de compteur comptabilisent le nombre de fois où un événement de succès est défini (x+1). Les événements peuvent également être configurés en tant qu’événements « *numériques* » qui vous permettent de spécifier la valeur d’incrément (cela peut notamment s’avérer nécessaire lors du décompte de valeurs dynamiques ou arbitraires, telles que le nombre de résultats renvoyés par une recherche interne).

Un type d’événement final, « *devise* », vous permet de définir le montant à ajouter (semblable à des événements numériques). Cependant, il s’affiche sous la forme d’une devise dans les rapports et est sujet à des conversions monétaires sur la base de la valeur s. *`currencyCode`* et du paramètre de devise par défaut de votre suite de rapports. For additional information on using numeric and currency events, see [Products](../../../implement/js-implementation/c-variables/page-variables.md#concept_A4007F6307E4419DAA65E1668A8FEBA2).

**Configuration de la variable** {#section_9195286C34C54B02B2598E2B856492C3}

La variable [!UICONTROL s.events] est activée par défaut pour toutes les implémentations. Les sept événements de conversion préconfigurés sont automatiquement activés pour toutes les nouvelles suites de rapports. New custom events (event1- [event100 or event1000](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28)) can be enabled by any admin-level user using the Admin Console.

**Valeurs possibles** {#section_18395A3BEFEB4E9F8D7B2ED0001FBE4E}

Voici la liste des valeurs possibles pour la variable « events » :

| Evénement | Description | Rapports renseignés |
|---|---|---|
| prodView | Consultations produits | Produits |
| scOpen | Ouvrir / Initialiser un nouveau panier | Paniers |
| scAdd | Ajouter un/des article(s) au panier  | Ajouts au panier |
| scRemove | Retirer un/des article(s) du panier | Retraits du panier |
| scView | Afficher le panier | Consultations du panier |
| scCheckout | Début du processus de passage en caisse | Achats |
| purchase | Finalisation d’un achat (d’une commande) | Commandes |
| événement1 - événement1000 (événement100 pour un produit ponctuel) | Evénements personnalisés | Événements personnalisés |

**Syntaxe et exemples** {#section_45A159DF00114066B8551DDEB15E084C}

Des événements de compteur sont définis en plaçant les événements souhaités dans la variable [!UICONTROL s.events], dans une liste de valeurs séparées par des virgules (si plusieurs événements doivent être transmis).

```js
s.events="scAdd"
```

```js
s.events="scAdd,event1,event7"
```

```js
s.events="event5"
```

```js
s.events="purchase,event10"
```

Si vous utilisez du code H23 ou une version antérieure, des valeurs entières supérieures à un peuvent être affectés aux événements de compteur. 

```js
s.events="event1=10"
```

```js
s.events="scRemove=3,event6,event2=4"
```

L’implémentation d’événements de compteur lorsque des valeurs entières sont affectées traite l’événement comme s’il est déclenché à plusieurs reprises dans la demande d’image. Les événements de compteur ne prennent pas en charge les décimales. Il est recommandé d’utiliser à la place des événements numériques en cas de besoin.
Les événements numériques et monétaires doivent être définis dans la variable [!UICONTROL s.events], mais ils reçoivent leur valeur numérique (24,99, par exemple) dans la variable [!UICONTROL s.products]. Vous avez ainsi la possibilité d’associer des valeurs numériques et monétaires spécifiques à des entrées de produit individuelles.

**Sérialisation d’événements** {#section_A89488EF4471405AAFC4D6DD05E77621}

Par défaut, un événement est comptabilisé chaque fois qu’il est défini sur votre site.

Reportez-vous à la section [Sérialisation d’événements](../../../implement/js-implementation/event-serialization.md#concept_092B638D7FEE423D91F8A57EA8E09705) pour plus d’informations.

**Syntaxe** {#section_8559D42D3F344AF3BB3C0125F78C4989}

```js
s.events="event1:3167fhjkah"
```

**Exemples** {#section_7B5B5728A59648ADB3E2548CDAD2C9D4}

```js
s.events="scAdd:003717174"
```

```js
s.events="scAdd:user228197,event1:577247280,event7:P7fhF8571"
```

## hierN {#concept_C4475D1584D544ACB4C0A573EB60FA08}

La variable de [!UICONTROL hiérarchie] détermine l’emplacement d’une page dans la hiérarchie de votre site.

<!-- 

hierN.xml

 -->

Cette variable est particulièrement utile pour les sites dont la structure comprend plus de trois niveaux. Par exemple, la section Sports d’un site de médias peut comporter 4 niveaux : Sports, Sports locaux, Base-ball et Red Sox. Si un visiteur accède à la page Base-ball, les niveaux Sports, Sports locaux et Base-ball reflètent tous cette visite.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| 255 octets | H1-H5 | Hiérarchie | "" |

Cinq variables de [!UICONTROL hiérarchie] sont disponibles. Elles doivent être activées par le service à la clientèle Adobe. Au moment de l’activation de la hiérarchie, vous devez choisir un séparateur pour la variable, ainsi que le nombre maximal de niveaux pour la hiérarchie. Par exemple, si le délimiteur est une virgule, la hiérarchie Sports peut se présenter comme suit.

```js
s.hier1="Sports,Local Sports,Baseball"
```

Veillez à ce qu’aucun de vos noms de section ne comporte de séparateur. Par exemple, si l’une de vos sections s’intitule « Coach Griffin, Jim », vous devez opter pour un séparateur autre que la virgule. Chaque section de la hiérarchie est limitée à 255 octets, la limite de variable totale étant de 255 octets. Une fois le séparateur choisi (au moment de la création de la hiérarchie), il est difficile de le modifier.

Contactez le service à la clientèle Adobe pour modifier le séparateur d’une hiérarchie existante. Les séparateurs peuvent également se composer de plusieurs caractères, tels que || ou /|\, dont les probabilités d’affichage dans une section sont moins élevées.

**Syntaxe et valeurs possibles** {#section_0739948A68A2420DAB1CBEA3115A5A66}

N’insérez pas d’espace entre deux séparateurs. Dans l’exemple de syntaxe ci-dessous, N est un nombre compris entre 1 et 5.

```js
s.hierN="Level 1[<delimiter>Level 2[<delimiter>Level 3[...]]]"
```

N’utilisez le séparateur que pour délimiter les niveaux de la hiérarchie. Le séparateur peut être un ou plusieurs caractères de votre choix.

**Exemples** {#section_38E0929F88DD45B6ACDF473DF155971D}

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub"
```

```js
s.hier4="Sports/Local Sports/Baseball"
```

**Paramètres de configuration** {#section_E823FB3CAD744D2480EBCE2DF9B134CC}

Aucune

**Pièges, questions et conseils** {#section_104E5BD320764BDEA5FA8D13A70C78E3}

* Une fois la hiérarchie configurée, le séparateur ne peut plus être modifié. S’il s’avère nécessaire de modifier le séparateur de votre hiérarchie, contactez le service à la clientèle Adobe.
* Une fois la hiérarchie configurée, le nombre de niveaux ne peut plus être modifié.

>[!NOTE]
>
>Les modifications apportées aux hiérarchies peuvent entraîner des frais de service.

## homepage {#concept_0A3E416F1A064BA396B5FCEABFB7B0B4}

La variable , dans Internet Explorer, indique si la page active est définie comme page d’accueil de l’utilisateur.

<!-- 

homepage.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>Cette variable ne doit être lue que et jamais définie.

Vous pouvez lire ces valeurs et les copier dans props/eVars, mais vous ne pouvez, en aucun cas, les modifier. Cette variable est apparue avec la version H.11 du fichier JavaScript.

| Paramètre de requête | Valeur | Exemple | Rapports concernés |
|---|---|---|---|
| hp | Y ou N | Y | Trafic &gt; Technologie &gt; Page d’accueil |

## javaEnabled {#concept_F24A3536F1F0453DA214B16BAA5A6F67}

La variable indique si Java est activé sur le navigateur.

<!-- 

javaEnabled.xml

 -->

Cette variable est complétée après le code de page et avant l’exécution de doPlugins.

>[!NOTE]
>
>Cette variable ne doit être lue que et jamais définie.

Vous pouvez lire ces valeurs et les copier dans props/eVars, mais vous ne pouvez, en aucun cas, les modifier. Cette variable est apparue avec la version H.11 du fichier JavaScript.

| Paramètre de requête | Valeur | Exemple | Rapports concernés |
|---|---|---|---|
| v | Y ou N | Y | Trafic &gt; Technologie &gt; Java |

## javascriptVersion {#concept_19E2C9F87BB24E69B911C0F5873CAA90}

La variable indique la version de JavaScript prise en charge par le navigateur.

<!-- 

javascriptVersion.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>Cette variable ne doit être lue que et jamais définie.

Vous pouvez lire ces valeurs et les copier dans props/eVars, mais vous ne pouvez, en aucun cas, les modifier. Cette variable est apparue avec la version H.11 du fichier JavaScript.

| Paramètre de requête | Valeur | Exemple | Rapports concernés |
|---|---|---|---|
| j | 1.0, 1.1, 1.2, … 1.7 | 1.7 | Trafic &gt; Technologie &gt; Version de JavaScript |

Les versions H.10 et ultérieures du fichier JavaScript effectuent une détection précise jusqu’à la version 1.7 (soit la version la plus élevée au moment de la publication de H.10). Dans le cas des versions antérieures du fichier JavaScript, la détection n’est assurée que jusqu’à la version 1.3.

## linkName {#concept_1B2A3F56C9AD4C23A8A4331730EC2B8F}

The  variable is an optional variable used in [!UICONTROL Link Tracking] that determines the name of a custom, download, or exit link.

<!-- 

linkName.xml

 -->

The *`linkName`* variable is not normally needed because the third parameter in the *`tl()`* function replaces it.

<table id="table_4B0D1C9AADA542A59B626E077D5FC568"> 
 <thead> 
  <tr> 
   <th class="entry"> Taille maximale </th> 
   <th class="entry"> Paramètre du débogueur </th> 
   <th class="entry"> Rapports renseignés </th> 
   <th class="entry"> Valeur par défaut </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 100 octets </td> 
   <td> pev2 </td> 
   <td> <p>Téléchargements de fichiers </p> <p>Liens personnalisés </p> <p>Liens de sortie  </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

Les [!UICONTROL liens personnalisés] désignent des liens qui envoient des données de suivi. La variable *`linkName`* variable (or the third parameter in the *`tl()`* function) is used to identify the value that appears in the [!UICONTROL Custom], [!UICONTROL Download], or [!UICONTROL Exit Links] report. If *`linkName`* is not populated, the URL of the link appears in the report.

**Syntaxe et valeurs possibles** {#section_C8D89834C98B4C7A858C947293C4148E}

```js
s.linkName="Link Name"
```

There are no limitations on *`linkName`* outside of the standard variable limitations.

**Exemples** {#section_5F68766210184E82A23D2A6ECD80BA0B}

```js
s.linkName="Nav Bar Home Link"
```

```js
s.linkName="Partner Link to A.com"
```

**Paramètres de configuration** {#section_F15FF429FC274F708D50DF79D4668EA3}

Aucune

**Pièges, questions et conseils** {#section_170A78452A7340B5B229713AC1FB71FA}

* The *`linkName`* variable is replaced by the third parameter in the *`tl()`* function.

* If the *`linkName`* variable and the third parameter in the *`tl()`* function are blank, the full URL of the link (with the exception of the query string) appears in the report (even if the link is relative).

## linkType {#concept_7695692AF5D843E3B370F6D345E32964}

La variable est une variable facultative utilisée dans le cadre du suivi des liens. Elle détermine le rapport dans lequel un nom de lien ou une URL doit apparaître (liens personnalisés, de téléchargement ou de sortie).

<!-- 

linkType.xml

 -->

The *`linkType`* variable is not normally needed because the second parameter in the *`tl()`* function replaces it.

<table id="table_3D1A2FC1CECD4709BE2F9E32AC2DC730"> 
 <thead> 
  <tr> 
   <th class="entry"> Taille maximale </th> 
   <th class="entry"> Paramètre du débogueur </th> 
   <th class="entry"> Rapports renseignés </th> 
   <th class="entry"> Valeur par défaut </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Un seul caractère </td> 
   <td> pe=[lnk_o|lnk_d|lnk_e] </td> 
   <td> <p>Téléchargements de fichiers </p> <p>Liens personnalisés </p> <p>Liens de sortie  </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

Les liens personnalisés envoient des données à Analytics. The *`linkType`* variable (or the second parameter in the *`tl()`* function) is used to identify the report in which the link name or URL appears ( [!UICONTROL Custom], [!UICONTROL Download], or [!UICONTROL Exit Links] report).

Pour les liens de sortie et de téléchargement, la *`linkType`* variable est automatiquement renseignée selon que le lien sur lequel l’utilisateur a cliqué est un lien de sortie ou de téléchargement. A custom link may be configured to send data to any of the three reports with this variable or with the second parameter in the *`tl()`* function. By setting  to 'o,' 'e,' or 'd,' the  or link URL is sent to the Custom Links, Exit Links, or File Downloads report respectively.*`linkType`**`linkName`*

**Syntaxe et valeurs possibles** {#section_18DB3A8083FB4F75B970055ED336DA4E}

The *`linkType`* variable syntax depends on whether you use XML or a query string.

Si vous utilisez du code XML, la variable ne peut contenir qu’un seul caractère, à savoir « o », « e » ou « d ».

```js
s.tl(this,’o’,’Link Name’);
```

If you are using the query-string `pe`, you need to use `lnk_d`, `lnk_e`, or `lnk_o`.

**Exemples** {#section_242B5DFFD1C9462A9A8EB1556B2E3160}

```js
<a href="index.html" onClick=" 
 var s=s_gi('rsid'); **see note below on the rsid** 
 s.tl(this,'o','Link Name'); 
 ">My Page</a> 
```

**Paramètres de configuration** {#section_59738AD1B5E94294B8D36F4E772DEDB3}

Aucune

**Pièges, questions et conseils** {#section_F0D01DDE3FDA486C987162DA50A79C45}

* Si *`linkType`* n’est pas spécifié, les liens personnalisés ("o") sont supposés.

## Propriétés de liste {#concept_83ED74232225431F83A796E22FFC75B4}

Les props de liste sont une liste délimitée de valeurs transmises dans une variable, puis signalées comme lignes individuelles. Elles sont généralement implémentées sur des pages contenant des valeurs pouvant être sélectionnées par l’utilisateur, telles que des éléments répertoriés avec des cases à cocher ou des cases d’option. Les props de liste s’avèrent utiles lorsque vous souhaitez définir plusieurs valeurs dans une variable sans envoyer plusieurs demandes d’image.

<!-- 

list_props.xml

 -->

**Considérations**

* Les propriétés de liste ne sont activées que sur les variables de trafic ( [props](../../../implement/js-implementation/c-variables/page-variables.md#concept_0F10FA2DE69B4029A31EA5E9313AA254)).
* Le cheminement et les corrélations ne peuvent pas être activés pour les props de liste.
* Analytics fournit les visites et visiteurs uniques à presque tous les rapports, notamment tous les rapports sur les props de liste. 
* Les classifications sont prises en charge pour les propriétés de liste.
* Toute variable de trafic personnalisée peut devenir une propriété de liste. (Exceptions : [pageName](../../../implement/js-implementation/c-variables/page-variables.md#concept_5827B499DAC34B5D8445F9D9140CC328), [channel](../../../implement/js-implementation/c-variables/page-variables.md#concept_C7770B8C15724A99B10F8F468AF82D0D)et [server](../../../implement/js-implementation/c-variables/page-variables.md#concept_BF77952603BA454BAFC9A0A81D06A7D2).)

* Lors de la définition de valeurs dupliquées dans une même demande d’image, les instances ne sont pas dédupliquées.

Vous pouvez changer une variable prop dans une liste sur la page Outils d’administration &gt; Suite de rapports &gt; Variables de trafic en activant la prise en charge des listes et en sélectionnant un délimiteur. Les délimiteurs les plus courants sont les suivants : deux-points, points-virgules, virgules et barres verticales. D’un point de vue technique, il peut s’agir de l’un des 127 premiers caractères ASCII.

**Exemples de mise en œuvre** {#section_A3DD7293A8BB4807B42BFB1F73BE11AC}

Lorsque vous demandez l’activation de propriétés de liste, indiquez le délimiteur à utiliser. Après avoir activé la variable *`s.prop`* de votre choix, vous pouvez définir plusieurs valeurs, comme illustré dans les exemples suivants :

Une propriété de liste délimitée par une barre verticale, transmettant deux valeurs :

```js
s.prop1="Banner ad impression|Sidebar impression"
```

Une propriété de liste délimitée par une virgule, transmettant plusieurs valeurs :

```js
s.prop2="cerulean,vermilion,saffron"
```

Les propriétés de liste peuvent également être envoyées avec une seule valeur :

```js
s.prop3="Single value"
```

Vous pouvez changer de délimiteur à tout moment. L’implémentation doit toutefois correspondre au nouveau délimiteur. Si vous n’utilisez pas le délimiteur correct, la valeur de propriété de liste sera considérée comme un élément concaténé unique dans les rapports.

Comme une prop de liste reste une variable de trafic, elle est donc soumise aux mêmes limites que cette dernière. Les props de liste sont limitées à 100 octets de données et sont sensibles à la casse.

## Variable de liste {#concept_AC42F2D69B674C02A484137CE5B4E687}

Connue également sous le nom de variable de liste. A l’instar de la fonction Propriétés de liste, les variables de liste autorisent plusieurs valeurs dans la même demande d’image. Elles se comportent également de la même manière que les eVars, lesquelles persistent au-delà de la demande d’image sur laquelle elles ont été définies. Vous pouvez utiliser ces variables pour afficher les causes et les effets parmi plusieurs éléments sur une seule page, tels que des listes de produits, de cadeaux, d’affinements de recherche ou encore d’annonces graphiques.

<!-- 

listN.xml

 -->

**Considérations**

* Elles mémorisent leurs valeurs spécifiques en référençant le cookie VisitorID dans le navigateur du visiteur.
* 250 valeurs au maximum sont stockées à la fois par visiteur. Si cette limite de 250 valeurs par visiteur est dépassée, seules les 250 dernières valeurs sont utilisées. L’expiration de ces valeurs dépend de l’expiration configurée pour la variable.
* Chaque valeur délimitée peut contenir, au maximum, 255 caractères (ou moins en cas d’utilisation de caractères codés sur plusieurs octets). Il s’agit de la longueur maximale de chaque élément.
* Le nombre de caractères de cette variable n’est pas limité. La seule exception concerne les anciens navigateurs Internet Explorer qui imposent une limite de 2 083 caractères à toutes les demandes d’URL.
* Au total, trois variables de liste sont disponibles par suite de rapports.
* Le code H23 ou ultérieur est nécessaire pour utiliser des variables de liste.
* Les variables de liste peuvent être classifiées.
* Si des valeurs en double sont définies dans une même demande d’image, les variables de liste dédupliquent toutes les instances de celles-ci. 
* Les variables de liste les plus granulaires peuvent être segmentées au niveau des accès (ou des pages vues). Si une variable de liste contient trois valeurs dans une même demande d’image, les règles de segmentation qui correspondent à une valeur incluent les trois valeurs dans les rapports. A l’inverse, si une règle d’exclusion définie correspond à une seule valeur, les trois valeurs sont exclues.

**Configuration** {#section_8CADFF581D2447518BA3F7F79B2D80A9}

La configuration est accessible dans Admin Console ; vous pouvez la mettre à jour sans faire appel au service à la clientèle :

1. Go to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**
1. Sélectionnez la suite de rapports.
1. Click  **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL List Variables]** .

* **Nom** : chaque valeur délimitée peut contenir, au maximum, 255 caractères (ou moins en cas d’utilisation de caractères codés sur plusieurs octets). Il s’agit de la longueur maximale de chaque élément.
* **Délimiteur de valeurs** : caractère utilisé pour séparer les valeurs dans la variable de liste. Il s’agit généralement de caractères tels que des virgules, deux-points, barres verticales, etc.

   >[!NOTE]
   >
   >Les caractères complexes ne sont pas pris en charge en tant que délimiteurs dans les List Vars. Le délimiteur doit être un caractère à un seul octet.

* **Expiration** : à l’instar d’une expiration d’eVar, cette valeur détermine la période qui peut s’écouler entre la variable de liste et l’événement de conversion à relier.

   * **Au niveau d’une page vue ou d’une visite** : les événements de succès au-delà de la page vue ou de la visite ne sont reliés à aucune des valeurs dans la variable de liste.
   * **Sur la base d’une période, telle qu’un jour, une semaine, un mois, etc.** : les événements de succès au-delà de la période spécifiée ne sont reliés à aucune des valeurs dans la variable de liste. Un nombre personnalisé de jours peut être également défini.
   * **Evénements de conversion spécifiques** : tout autre événement de succès qui se déclenche après l’événement désigné n’est relié à aucune des valeurs dans la variable de liste.
   * **Jamais** : une période indéfinie peut s’écouler entre la variable de liste et l’événement de succès.

* **Affectation ** : ce paramètre détermine comment les événements de succès répartissent le crédit entre les valeurs :

   * **Complète** : toutes les valeurs de la variable définies avant l’expiration de celle-ci obtiennent un crédit complet pour les événements de succès.
   * **Linéaire** : toutes les valeurs de la variable définies avant l’expiration de celle-ci obtiennent un crédit divisé pour les événements de conversion.
   * Les valeurs de la variable ne sont jamais remplacées. Elles sont ajoutées aux valeurs qui obtiennent le crédit pour les événements de succès. 

* **Valeurs max.** : désigne le nombre de valeurs actives autorisées pour cette variable de liste. Par exemple, si ce paramètre est défini sur 3, seules les 3 dernières valeurs capturées sont enregistrées et toute valeur capturée précédemment est ignorée. Notez que si plusieurs valeurs pour la même variable de liste sont envoyées sur le même accès, alors que vous avez limité l’utilisation des valeurs maximales, chaque valeur aura le même horodatage et vous n’aurez aucune garantie quant à la valeur enregistrée.

   250 valeurs au maximum sont stockées à la fois par visiteur. Si cette limite de 250 valeurs par visiteur est dépassée, seules les 250 dernières valeurs sont utilisées. L’expiration de ces valeurs dépend de l’expiration configurée pour la variable.

   Le paramètre Valeurs max. se révèle particulièrement utile pour limiter l’attribution à un nombre spécifique de valeurs. Par exemple, si une variable de liste est définie sur « A,B,C » sur la première page d’une liste, puis sur « X,Y,Z » sur la page suivante, l’attribution est distribuée à ces six valeurs sur la base de l’allocation. Si vous souhaitez limiter l’attribution aux seules valeurs « X,Y,Z », vous pouvez définir ce paramètre sur 3.

To set up or edit List Vars, go to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL List Variables]** .

**Exemples de mise en œuvre** {#section_564AFE6A2F524BFEB372EC0F7FEBA656}

La virgule est utilisée comme délimiteur de valeurs dans les exemples suivants :

**Définition d’une seule valeur dans une variable de liste :**

```js
s.list1="Cat";
```

**Transmission de plusieurs valeurs :**

```js
s.list2="Tabby,Persian,Siamese"; 
s.list1="Product 1,Product 2,Product 3";
```

**Affectation de recettes à une variable de liste :**

```js
//Define this code on the landing page: 
s.list3="Top Banner Ad,Side Bar Ad,Internal Campaign 1"; 
 
//Have these variables fire on the purchase confirmation page: 
s.products=";Kitten;1;50" 
s.events="purchase";
```

Ce résultat présente trois éléments avec, pour chacun d’eux, des recettes de 50 USD. (Bannière publicitaire supérieure ; Annonce de barre latérale ; Campagne interne 1.) Notez que le total de ce rapport déduplique les recettes, de telle sorte qu’il fera également état de 50 USD.

**Affectation de recettes à une variable de liste qui a été définie plusieurs fois lors d’une visite :**

**Affectation** : complète

**Expiration** : visite

<table id="table_09E1879B44624A858555449E2DC74E69"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Page </th> 
   <th colname="col2" class="entry"> s.list1 </th> 
   <th colname="col3" class="entry"> s.events/s.products </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Page 1 </td> 
   <td colname="col2"> <code> s.list1=”value1,value2,value3”; </code> </td> 
   <td colname="col3"> (non défini) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Page 2 </td> 
   <td colname="col2"> <code> s.list1=”value4,value5,value6”; </code> </td> 
   <td colname="col3"> <p> <code> s.events=”purchase”; </code> </p> <p> <code> s.products=”;product;1;200” </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Résultat :** toutes les valeurs définies dans la variable de liste 1 à tout moment pendant la visite (value1,value2,value3,value4,value5,value6) reçoivent un crédit complet pour l’achat. 

## maxDelay {#concept_B355038C3B094BB68C0DC6C80F9FE5B0}

La variable s.maxDelay est principalement utilisée dans les intégrations Genesis DFA pour déterminer le délai d’inactivité lors du contact de l’hôte DFA. Si Adobe ne reçoit pas de réponse des serveurs de DFA dans le délai spécifié qui est défini dans la variable  , la connexion est établie, et les données sont traitées normalement. Implémentez cette variable si le temps de réponse de DFA sur chaque page vous préoccupe. Il est conseillé de tester cette valeur pour déterminer le délai d’inactivité optimal. 

<!-- 

maxDelay.xml

 -->

**Exemple d’implémentation**

```
s.maxDelay="750";
```

**Propriétés**

* Cette variable est une mesure d’événement facultative qui est renseignée via le code JavaScript implémenté sur votre site.
* Si l’hôte DFA ne répond pas dans le délai imparti, l’événement désigné pour le délai dépassé s’exécute (attribué via l’assistant d’intégration Genesis). 
* Cette variable ne peut contenir qu’une valeur numérique.
* La durée spécifiée est mesurée en millisecondes.
* L’augmentation du délai d’attente permet de collecter des données DFA supplémentaires, mais augmente aussi le risque de perte des données d’accès Analytics.

   Losing Analytics hit data would occur when the user navigates away from the page during the *`s.maxDelay`* period.

* La diminution du délai d’attente limite le risque de perte des données d’accès Analytics, mais peut diminuer le nombre de données DFA envoyées avec les données d’accès.

   La perte des données d’intégration DFA surviendrait lorsque la *`s.maxDelay`* période ne permet pas à l’hôte DFA de répondre.

>[!NOTE]
>
>Adobe does not have control over DFA's response time. Si vous rencontrez des problèmes même après avoir augmenté le délai de la variable, contactez l’administrateur de compte DFA de votre société.

## mediaLength {#concept_F52B1670122C4461824223E525307060}

La variable définit la longueur totale du média en cours de lecture.

<!-- 

mediaLength.xml

 -->

<table id="table_B1AE8A9DF9D545C2965CDB2DB6C2969B"> 
 <thead> 
  <tr> 
   <th class="entry"> Taille maximale </th> 
   <th class="entry"> Paramètre du débogueur </th> 
   <th class="entry"> Rapports renseignés </th> 
   <th class="entry"> Valeur par défaut </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Pas de taille maximale pour la requête pev3 complète ; la taille est limitée à la longueur maximale de l’URL du navigateur. </td> 
   <td> pev3 </td> 
   <td> Durée de consultation de la vidéo ; <p>Segments de vidéo affichés </p> </td> 
   <td> Aucun </td> 
  </tr> 
 </tbody> 
</table>

**Syntaxe et valeurs possibles** {#section_FEC1B01FDD234ACEB63C0558BEEB5CBC}

** Méthode autoTrack : **

Si vous utilisez [!UICONTROL s.Media.autoTrack], la variable [!UICONTROL mediaLength] ne doit pas être implémentée explicitement. Elle est déterminée automatiquement par le code AppMeasurement pour JavaScript.

**Méthode de suivi manuel :**

Syntaxe :

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

Valeurs possibles :

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**Exemples** {#section_048B2D31BB584647A5D335AE94E5A599}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3= [Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**Pièges, questions et conseils** {#section_1CEDC78FEF4940E9BC02A2AF1EE2FB01}

* Vous ne devez appeler les méthodes de suivi de média que si le suivi du lecteur s’avère impossible à l’aide de [!UICONTROL s.Media.autoTrack] = true.
* Si le suivi n’est pas effectué à l’aide de la méthode [!UICONTROL autoTrack], veillez à définir la durée en secondes.

## mediaName {#concept_A4CB1782DE244C23BA6CBB5E806DDE6A}

Cette variable indique le nom de la vidéo ou de l’élément multimédia.

<!-- 

mediaName.xml

 -->

Elle est uniquement disponible par le biais de l’[!UICONTROL API pour l’insertion des données] et de la [!UICONTROL source de données à traitement complet].

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| 64 Ko | pev3 | Vidéos ; Flux vidéo suivant ; Flux vidéo précédent ; Segments de la vidéo affichée ; Durée de consultation de la vidéo | Aucun |

**Syntaxe et valeurs possibles** {#section_F97A2253BBD24FEBBC225F233A319F5D}

**Méthode autoTrack :**

Si vous utilisez [!UICONTROL s.Media.autoTrack], la variable *`mediaName`ne doit pas être implémentée explicitement.* Elle est déterminée automatiquement par le code AppMeasurement pour JavaScript.

**Méthode de suivi manuel :**

Syntaxe :

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName) 
```

```js
s.Media.play(mediaName,mediaOffset)
```

```js
s.Media.stop(mediaName,mediaOffset)
```

```js
s.Media.close(mediaName)
```

Valeurs possibles :

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
s.Media.close("de_bofr_1045Making_400k")
```

**Exemples** {#section_4B9584265B1A47289818141B2A88021D}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
s.Media.close("de_bofr_1045Making_400k")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 Values: 
  pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 
  11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32  
  
```

**Pièges, questions et conseils** {#section_941A445BB52E4063B0F6920E61BB90DE}

* Vous ne devez appeler les méthodes de suivi de média que si le suivi du lecteur s’avère impossible à l’aide de [!UICONTROL s.Media.autoTrack] = true.
* Cette variable est stockée sous forme de variable TEXTE mySQL contrairement à VARCHAR(100).

## mediaPlayer {#concept_1932756C093B4B2FBA0484E5A58EF927}

Cette variable indique le lecteur utilisé pour exécuter une vidéo ou un élément multimédia.

<!-- 

mediaPlayer.xml

 -->

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| 100 octets | pev3 | Lecteurs vidéo | Aucun |

**Syntaxe et valeurs possibles** {#section_EAA55A3A45B5405F903E3BE6ACAB143F}

**Méthode autoTrack :**

```js
s.Media.playerName = "My Custom Player Name"  //configure player name in global JavaScript or ActionSource
```

**Méthode de suivi manuel :**

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

Valeurs possibles :

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**Exemples** {#section_64967E1333D542CCB6CF62F0A1E0EF88}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers] 
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**Pièges, questions et conseils** {#section_0020E031338F4A4880B9AC5B9A85BEF5}

Vous ne devez appeler les méthodes de suivi de média que si le suivi du lecteur s’avère impossible à l’aide de s.Media.autoTrack = true.

## mediaSession {#concept_19E6C850C3244CB6973140709BDCB0B9}

Cette variable indique les segments lus d’une vidéo ou d’une ressource multimédia.

<!-- 

mediaSession.xml

 -->

<table id="table_8681473270FE44DFBBCCC0FBA6737104"> 
 <thead> 
  <tr> 
   <th class="entry"> Taille maximale </th> 
   <th class="entry"> Paramètre du débogueur </th> 
   <th class="entry"> Rapports renseignés </th> 
   <th class="entry"> Valeur par défaut </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 255 octets </td> 
   <td> pev3 </td> 
   <td> Durée de consultation de la vidéo <p>Segments de vidéo affichés </p> </td> 
   <td> Aucun </td> 
  </tr> 
 </tbody> 
</table>

**Syntaxe et valeurs possibles** {#section_9A63266633C4427CB4A6549E4D887B85}

**Méthode autoTrack :**

Si vous utilisez [!UICONTROL s.Media.autoTrack], la *`mediaName`ne doit pas être implémentée explicitement.* Elle est déterminée automatiquement par le code AppMeasurement pour JavaScript.

**Méthode de suivi manuel :**

Syntaxe :

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName) 
```

```js
s.Media.play(mediaName,mediaOffset)
```

```js
s.Media.stop(mediaName,mediaOffset)
```

Valeurs possibles :

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

**Exemples** {#section_3446EC37E017407FA3F43C9BDAEA0B85}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32 
```

**Pièges, questions et conseils** {#section_1BCEB037AB724B6EBE87420BD3604B88}

Vous ne devez appeler les méthodes de suivi de média que si le suivi du lecteur s’avère impossible à l’aide de [!UICONTROL s.Media.autoTrack] = true.

## Media.trackEvents {#concept_B1C5FF6C437949EBA5D52040AC6BB6D9}

La variable identifie les événements qui doivent être envoyés avec un accès au média.

<!-- 

media_trackEvents.xml

 -->

Elle s’applique uniquement à JavaScript et [!UICONTROL ActionSource].

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | s.Media.trackEvents="None" |

**Syntaxe et valeurs possibles** {#section_66A978EF56914BEAAE73359A268A1B4A}

Noms d’événements tels que « event1 » ou « purchase ».

**Exemples** {#section_140A55D80EA24011954F9383CF312237}

```js
s.Media.trackEvents=”event1,purchase”
```

**Pièges, questions et conseils** {#section_030B11C64EE84D46A85CA550DB732D28}

Veillez à renseigner « events » dans la variable [!UICONTROL trackVars], le cas échéant.

## Media.trackVars {#concept_4350CA9A892148AE93C8133AB3B4BEA4}

La variable identifie les variables qui doivent être envoyées avec un accès au média.

<!-- 

media_trackVars.xml

 -->

Elle s’applique uniquement à JavaScript et [!UICONTROL ActionSource].

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | s.Media.trackVars="None" |

**Syntaxe et valeurs possibles** {#section_7374684A7EB34AE685E8C40A66CFD289}

Noms de variables tels que [!UICONTROL propN], *`eVarN`*, *`events`*, *`channel`*, etc.

**Exemples** {#section_48653222ABA14AB0A3C4471659971FAA}

```js
s.Media.trackVars=”prop2,events,eVar3”
```

**Pièges, questions et conseils** {#section_615AE1B696124B00B78F651B03813EAB}

* Même si eVar3 est spécifiée dans [!UICONTROL trackVars], elle est envoyée avec un accès au média.

## mobile {#concept_0CEE045F57B444138C0EAA015FC7EA70}

La variable spécifie l’ordre dans lequel les cookies et les identifiants d’abonnés sont utilisés pour identifier les visiteurs.

<!-- 

mobile.xml

 -->

See [Mobile network protocols](../../../implement/js-implementation/c-additional-libraries/network-protocols.md#concept_2425537FC9CB45DD868B5FA2298B6CAC).

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | /5/ ou /1/ dans le chemin de l’URL de l’image | N/D | Aucun |

**Syntaxe et valeurs possibles** {#section_7F1C58090C454882BA9D3D66C9263A76}

```js
s.mobile="any_string" //subscriber id used first, produces /5/ in path of image url 
s.mobile=""  // if set to an empty string or not set at all, cookies used first, produces /1/ in path of image url 
```

**Pièges, questions et conseils** {#section_06CD5CB4EF1E4B9FBE3B9D1F18AAFA30}

Utilisez l’identification des visiteurs croisés pour atténuer les pics possibles du trafic des visiteurs lors de l’utilisation de la *`s.mobile`* variable avec l’implémentation des cookies JavaScript.

## pageName {#concept_5827B499DAC34B5D8445F9D9140CC328}

La variable contient le nom de chaque page de votre site.

<!-- 

pageName.xml

 -->

<table id="table_0D09BAEC2FFD43F7905ED3649B3F8E05"> 
 <thead> 
  <tr> 
   <th class="entry"> Taille maximale </th> 
   <th class="entry"> Paramètre du débogueur </th> 
   <th class="entry"> Rapports renseignés </th> 
   <th class="entry"> Valeur par défaut </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 100 octets </td> 
   <td> pageName </td> 
   <td> <p>Pages </p> <p>Chemins </p> </td> 
   <td> URL de la page </td> 
  </tr> 
 </tbody> 
</table>

Pour renseigner la variable *`pageName`*, il convient d’utiliser une valeur reconnue par les utilisateurs de l’entreprise. Dans la plupart des cas, la *`pageName`* valeur n’est pas l’URL ou le chemin d’accès au fichier. Common *`pageName`* values include names such as "Home Page," "Checkout," "Purchase Thank you," or "Registration."

Veillez à ne pas autoriser l’affichage de caractères de nouvelle ligne, de tirets cadratins ou tirets courts, ou encore de tout caractère HTML dans le nom de la page et dans d’autres variables. Certains navigateurs envoient des caractères de nouvelle ligne, ce qui provoque le fractionnement des données d’Analytics entre deux noms de page apparemment identiques. De nombreux programmes de traitement de texte et clients de messagerie convertissent automatiquement un trait d’union en tiret cadratin ou tiret court lors de la saisie. Dans la mesure où ces deux tirets sont des caractères interdits dans les variables Analytics (car il s’agit de caractères ASCII dont le code est supérieur à 127), Analytics n’enregistre pas le nom de page où ils apparaissent et affiche, à la place, l’URL de la page.

If *`pageName`* is left blank, the URL is used to represent the page name. Leaving *`pageName`* blank is often problematic because the URL may not always be the same for a page `www.mysite.com` and `mysite.com` are the same page with different URLs).

**Syntaxe et valeurs possibles** {#section_7A61EE70F1A84D26B414404998C84BA8}

The *`pageName`* variable should contain a useful identifier for business users of Analytics.

```js
s.pageName="page_name"
```

There are no limitations on *`pageName`* outside of the standard variable limitations.

**Exemples** {#section_8BB4F86F84E246A08B72DEC47FFC0765}

```js
s.pageName="Search Results" 
```

```js
s.pageName="Standard Offer List"
```

**Paramètres de configuration** {#section_58CBC68C805344A999EB47455FEBA8D5}

Les administrateurs ont la possibilité de modifier le nom de page visible dans Analytics à l’aide de l’outil d’attribution de [!UICONTROL noms aux pages], ce qui peut représenter un danger potentiel et avoir une incidence négative sur vos rapports. Contactez le service à la clientèle Adobe avant d’utiliser l’outil d’attribution de [!UICONTROL noms aux pages].

**Pièges, questions et conseils** {#section_BB41DC9682C34385B9CAA80D5257C113}

Assurez-vous que le *`pageName`* ne contient pas de caractères interdits.

## pageType {#concept_F67870238EF74491B5D3909A33CDB985}

La variable n’est utilisée que pour désigner une page « Erreur 404 - Page introuvable ».

<!-- 

pageType.xml

 -->

<table id="table_0492B136E9D14070A6CA49ED534BCA4C"> 
 <thead> 
  <tr> 
   <th class="entry"> Taille maximale </th> 
   <th class="entry"> Paramètre du débogueur </th> 
   <th class="entry"> Rapports renseignés </th> 
   <th class="entry"> Valeur par défaut </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 20 octets </td> 
   <td> pageType </td> 
   <td> Chemins &gt; Pages &gt; Pages <p>introuvables </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

La variable *`pageType`* capture l’URL erronée lors de l’affichage d’une page Erreur 404, ce qui vous permet d’identifier rapidement les chemins et liens rompus qui ne sont plus valides sur le site personnalisé. Configurez la *`pageType`* variable sur la page d’erreur exactement comme illustré ci-dessous.

N’utilisez pas la variable de nom de page sur les pages de type Erreur 404. La variable *`pageType`* concerne exclusivement la page Erreur 404.

Dans la plupart des cas, cette page est une page statique qui est codée en dur. La référence au fichier .JS doit alors être définie sur un chemin/répertoire relatif ou global approprié.

**Syntaxe et valeurs possibles** {#section_C1C59968226446559B05F6EE7374D525}

La seule valeur autorisée de *`pageType`* est "errorPage", comme illustré ci-dessous.

```js
s.pageType="errorPage"
```

**Exemples** {#section_6CE22FCB835B4A19B633B7F67E73A115}

```js
s.pageType="errorPage"
```

**Paramètres de configuration** {#section_3B304A6D3A6C48F2BE90B4DA92A39DDB}

Aucune

**Pièges, questions et conseils** {#section_943681AB01FE47BEAC72E93CB60C53C8}

To capture other server-side errors (such as 500 errors), use a prop to capture the error message and put "`500 Error: <URL>`" where `<URL>` is the URL requested, in the *`pageName`* variable. En suivant cette méthodologie, vous pouvez utiliser des rapports [!UICONTROL Cheminement] afin d’afficher les chemins empruntés par les utilisateurs pour générer des erreurs 500. La prop explique le message d’erreur généré par le serveur.

## pageURL {#concept_A15F710CD0174297A2286BF3E7452113}

La variable remplace l’URL réelle de la page.

<!-- 

pageURL.xml

 -->

Dans de rares cas, l’URL de la page diffère de celle que vous souhaiteriez voir consignée dans les rapports Analytics.

<table id="table_D4DC6B476FFD4BEEB36A5C6B2D026255"> 
 <thead> 
  <tr> 
   <th class="entry"> Taille maximale </th> 
   <th class="entry"> Paramètre du débogueur </th> 
   <th class="entry"> Rapports renseignés </th> 
   <th class="entry"> Valeur par défaut </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Aucune limite* </td> 
   <td> <p>G </p> </td> 
   <td> Trafic &gt; Segmentation &gt; Chemins des pages les plus populaires </td> 
   <td> URL de la page </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Although Adobe allows *`pageURL`* values up to 64k, some browsers impose a size limit on the URL of image requests. To prevent truncation of other data, page URLs longer than 255 bytes are split, with the first 255 bytes appearing in the `g=` parameter, with the remaining bytes appearing later in the query sting in the `-g=` query parameter.

**Syntaxe et valeurs possibles** {#section_22AF3BF7C2F743549967B0C760A095C0}

The *`pageURL`* variable must be a valid URL, with a valid protocol. En fonction des paramètres définis dans Analytics, il est possible que la chaîne de requête soit altérée. De plus, le domaine fait l’objet d’un affichage forcé en minuscules avant d’être renseigné dans les rapports.

```js
s.pageURL="proto://domain/path?query_string"
```

Seuls les caractères compatibles avec l’URL sont acceptés comme URL de la page.

>[!NOTE]
>
>Il est vivement conseillé de contacter votre conseiller Adobe ou le service à la clientèle avant d’utiliser la *`pageURL`* variable à des fins personnalisées.

**Exemples** {#section_45158FDA3F8F4574BDEB5CBC9F7E6C97}

```js
s.pageURL="https://mysite.com/home.jsp?id=1224" 
```

```js
s.pageURL="https://www.mysite.com/"
```

**Paramètres de configuration** {#section_A8F77DAD88164528ACC5C16C066B47DF}

Aucune

## plugins {#concept_B570F04FEDA34EB7A9826687FE633953}

Dans les navigateurs Netscape et à architecture Mozilla, la variable répertorie les modules externes (plug-ins) installés.

<!-- 

plugins.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>Cette variable ne doit être lue que et jamais définie.

Vous pouvez lire ces valeurs et les copier dans props/eVars, mais vous ne pouvez, en aucun cas, les modifier. Cette variable est apparue avec la version H.11 du fichier JavaScript.

| Paramètre de requête | Valeur | Exemple | Rapports concernés |
|---|---|---|---|
| p | Modules externes reconnus | IE Tab Plug-in;QuickTime Plug-in 7.1.6;Mozilla Default Plug-in;iTunes Application Detector;Adobe Acrobat;ActiveTouch General Plugin Container;Shockwave Flash;Microsoft Office 2003;Java(TM) Platform SE 6 U1;Windows Media Player Plug-in Dynamic Link Library;Microsoft® DRM; | Trafic &gt; Technologie &gt; Modules complémentaires |

## products {#concept_A4007F6307E4419DAA65E1668A8FEBA2}

La variable sert à effectuer le suivi des produits et des catégories de produits (ainsi que de la quantité achetée et du prix d’achat). Les produits sont généralement définis en association avec un événement de panier ou un événement 

<!-- 

products.xml

 -->

>[!IMPORTANT]
>
>In January of 2016, we updated the logic that sets the *`prodView`* event automatically, which happens when there is a *`product`* but no *`event`*. Cette mise à jour peut augmenter le nombre des événements *`prodView`.* *`prodViews`* augmentera uniquement dans les cas suivants :
>
>1. The events variable contains nothing but an unrecognized event, such as *`shoppingCart`* or *`cart`*, which are not valid events.
   >
   >
1. La variable *`products`n’est pas vide.*
>
>
Effet secondaire possible : il se peut que les eVars de marchandisage déclenchées par les événements *`prodView`* soient associées à une variable *`product`* vide, mais seulement si la variable *`product list`contient un produit non valide (tel un point-virgule sans produit répertorié).*

The *`products`* variable tracks how users interact with products on your site. Par exemple, une variable « products » peut surveiller le nombre de fois où un produit est affiché, ajouté au panier, passé en caisse et acheté. Elle peut également surveiller l’efficacité relative des catégories de marchandisage de votre site. Les scénarios ci-dessous sont courants pour l’utilisation de la variable « products ».

La variable *`products`* doit toujours être définie conjointement avec un événement de succès.

<table id="table_D5A11AFDDD364D0993D387906343DDF3"> 
 <thead> 
  <tr> 
   <th class="entry"> Taille maximale </th> 
   <th class="entry"> Paramètre du débogueur </th> 
   <th class="entry"> Rapports renseignés </th> 
   <th class="entry"> Valeur par défaut </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>La chaîne " <span class="wintitle"> products </span>" a une taille maximale de 64 Ko. </p> </td> 
   <td> products </td> 
   <td> Produits <p>Catégories (facultatif) </p> <p>Recettes (facultatif) </p> <p>Unités (facultatif) </p> <p>Evénements personnalisés (facultatif) </p> <p>eVars (facultatif) </p> </td> 
   <td> " " </td> 
  </tr> 
 </tbody> 
</table>

**Syntaxe** {#section_ABA3682985E540E6AA67A510176CCFFC}

```js
"Category;Product;Quantity;Price;eventN=X[|eventN2=X2];eVarN=merch_category[|eVarN2=merch_category2]"
```

| Champ | Définition |
|---|---|
| Catégorie | Comporte la catégorie de produit associée. Dans la version 15, les produits peuvent être associés à plusieurs catégories, ce qui corrige une limite présente dans la version 14. Si vous n’enregistriez pas auparavant une catégorie de produit, nous vous encourageons à commencer à remplir ce champ pour les suites de rapports présentes dans la version 15. |
| Produit | (Obligatoire) Identifiant utilisé pour le suivi d’un produit. Cet identifiant est utilisé pour compléter le rapport [!UICONTROL Produits]. Veillez à utiliser le même identifiant pendant tout le processus de passage en caisse. |
| Quantité | Nombre d’unités achetées. Ce champ doit être défini avec un événement d’[!UICONTROL achat] pour être enregistré. |
| Prix | Fait référence au coût associé de la quantité totale achetée (unités x prix unitaire), et non au prix unitaire. Ce champ doit être défini avec un événement d’[!UICONTROL achat] pour être enregistré. |
| Événements | Evénements monétaires associés à un produit spécifique. Voir [Evénements monétaires spécifiques à un produit](../../../implement/js-implementation/c-variables/page-variables.md#section_F814DF053C0D463A97DA039E6323720C) et [Evénements monétaires à l’échelle de la commande](../../../implement/js-implementation/c-variables/page-variables.md#section_D06F76A8A1F8498EB1BD6D8C8B9D5BE0). |
| eVars | Valeurs d’eVars de marchandisage associées à un produit spécifique. Voir [Variables de marchandisage](/help/components/c-variables/c-merch-variables/var-merchandising.md). |

Les valeurs incluses dans la variable *`products`* sont basées sur le type d’événement que vous enregistrez. Le délimiteur de catégorie/produit (;) est obligatoire comme espace réservé lors de l’omission de catégories. D’autres délimiteurs ne sont obligatoires que s’ils sont nécessaires pour distinguer le paramètre que vous incluez, comme indiqué dans les exemples de cette page.

**Définition de la variable « products » avec des événements de défaut d’achat** {#section_D5E689D4AAE941EC851CA9B98328A4DE}

The *`products`* variable must be set in conjunction with a success event.

**Définition de la variable « products » avec un événement d’achat** {#section_618AAC96E7B541A7AABAA028E5F4E5C3}

The *`purchase`* event should be set on the final confirmation ("Thank You!") du processus de commande. Le nom, la catégorie, la quantité et le prix du produit sont tous capturés dans la variable *`products`* variable. Although the *`purchaseID`* variable is not required, it is strongly recommended in order to prevent duplicate orders.

**Evénements de devise spécifique à un produit** {#section_F814DF053C0D463A97DA039E6323720C}

Si un événement de devise reçoit une valeur dans la *`products`* variable au lieu de la variable events, il s’applique uniquement à cette valeur. Cette fonction est utile pour effectuer le suivi de remises spécifiques à des produits, de l’expédition d’un produit et des valeurs similaires. Par exemple, si vous avez configuré l’événement 1 pour le suivi de l’expédition d’un produit, un produit avec des frais d’expédition de « 4,50 » (4.50) peut apparaître comme suit :

```js
s.events="event1" 
s.products="Footwear;Running Shoes;1;99.99;event1=4.50"
```

Dans cet exemple, la valeur de 4,50 (4.50) est associée directement au produit « Chaussures de courses » (Running Shoes). Si vous ajoutez event1 dans le rapport des produits, vous verrez « 4.50 » répertorié sur l’élément de ligne « Running Shoes ». Similaire au prix, cette valeur doit refléter le total correspondant à la quantité répertoriée. Si vous avez 2 éléments avec des frais d’expédition de 4,50 chacun, event1 doit être égal à « 9,00 » (9.00).

**Evénements de devise à l’échelle de la commande** {#section_D06F76A8A1F8498EB1BD6D8C8B9D5BE0}

Si un événement de devise reçoit une valeur dans la liste des événements au lieu de la *`products`* variable, il s’applique à tous les produits de la *`products`* variable. Cela s’avère utile pour effectuer un suivi des remises à l’échelle de la commande, sur l’expédition et sur des valeurs similaires, sans modifier le prix des produits ou en effectuant un suivi sur celui-ci séparément dans la liste de produits.

Par exemple, si vous avez configuré event10 pour contenir les remises à l’échelle de la commande, un achat avec une remise de 10 % peut ressembler à ce qui suit :

```js
s.events="purchase,event10=9.95" 
s.products="Footwear;Running Shoes;1;69.95,Running Essentials;Running Socks;10;29.50" 
s.purchaseID="1234567890"
```

Dans les rapports sur les événements monétaires, le total correspond au total des événements dédupliqués (dans cet exemple, le montant total des remises durant la période du rapport) et non à la somme des valeurs d’événement pour chaque produit. Par exemple, vous verriez « 9,95 » (9.95) répertorié à la fois pour les chaussettes et les chaussures de course et le total serait également de « 9,95 » (9.95).

>[!NOTE]
>
>si une valeur pour le même événement numérique/monétaire est spécifiée dans la *`products`* variable et dans la *`events`* variable, la valeur de la *`events`* variable est utilisée.

**Pièges, questions et conseils** {#section_D38FD0B79C0347B9AB4CF1632183DA2E}

* The *`products`* variable should always be set in conjunction with a [!UICONTROL success] event (events). Si aucun événement de [!UICONTROL succès] n’est spécifié, l’événement par défaut est [!UICONTROL prodView].

* Débarrassez le nom des produits et des catégories de toute virgule ou point-virgule avant de renseigner la variable « products ».
* Eliminez tout caractère HTML (symboles de marque déposée, de marque de commerce, etc.).
* Eliminez le symbole de devise (€) du prix.

**Exemples** {#section_FCC6EF43D3534ECB9A95CDB05820F564}

<table id="table_6F1334E73CE048A5AC0CC28B561C1B2D"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <code> s.products=”Category;ABC123” </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products=”Category2;ABC123,;ABC456” </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products=”Category3;ABC123;1;10” </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products=”Category;ABC123;1;10,;ABC456;2;19.98” </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1” </code> <p> <code> s.products="Category;ABC123;;;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99,;ABC123;2;19.98;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1,event2” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1,event2” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1,event2” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping|evar2=3 Stars" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1,event2” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping, ;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1,event2,event3” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1,event2,event3=9.95” </code> <p> <code> s.products="Category;ABC123;,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## propN {#concept_0F10FA2DE69B4029A31EA5E9313AA254}

Les variables de propriété ([!UICONTROL prop]) sont utilisées pour créer des rapports personnalisés dans le [!UICONTROL module Trafic].

<!-- 

propN.xml

 -->

Vous pouvez utiliser la variable props comme compteur (pour comptabiliser le nombre d’envois d’une page vue), pour les rapports de cheminement ou dans des rapports de corrélation.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| 100 octets | c1 - c75 | Trafic personnalisé | "" |

**Syntaxe et valeurs possibles** {#section_4D3013AF2979426B9589CA2BB9D254CD}

```js
s.propN="value"
```

Les variables de [!UICONTROL propriété] ne sont concernées par aucune limite, à l’exception des limites standard.

**Exemples** {#section_FFBB916DA9F44B668D5FAB7C511F6182}

```js
s.prop2="editorial" 
```

```js
s.prop15="toy category"
```

**Paramètres de configuration** {#section_25FDEB6ECA8242A2A44EE540C083078A}

Contactez le service à la clientèle Adobe au sujet de l’affichage des mesures [!UICONTROL Visite], [!UICONTROL Visiteur] et [!UICONTROL Chemin] pour les variables [!UICONTROL prop].

## purchaseID {#concept_21937434E63F413CB469007623B933AE}

La variable permet d’éviter qu’une commande ne soit comptée plusieurs fois dans les rapports.

<!-- 

purchaseID.xml

 -->

Whenever the [!UICONTROL purchase] event is used on your site, you should use the *`purchaseID`* variable.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| 20 octets | purchaseID | Conversion &gt; Achats &gt; Revenus issus des conversions  | "" |

Lorsqu’un visiteur achète un article sur votre site, la variable *`purchaseID`* est renseignée sur la page de remerciement, à l’endroit où est déclenché l’événement d’[!UICONTROL achat]. If the *`purchaseID`* is populated, the products on the "Thank You" page are counted only once per *`purchaseID`*. Il s’agit là d’un point essentiel, car de nombreux visiteurs de votre site enregistrent la page de remerciement ou de confirmation à des fins personnelles. La variable *`purchaseID`* évite que les achats ne soient comptabilisés lors de chaque consultation de la page.

Outre le fait que les données d’achat ne soient pas comptabilisées deux fois, la *`purchaseID`* variable permet de ne pas comptabiliser deux fois toutes les données de conversion dans les rapports.

**Syntaxe et valeurs possibles** {#section_E352CE2370D54BA69A368E1F63A9C32D}

```js
s.purchaseID="unique_id"
```

The *`purchaseID`* must be 20 characters or fewer, and be standard ASCII.

**Exemples** {#section_60A5C1EAF42F4611898CD6A4F4CF5A28}

```js
s.purchaseID="11223344" 
s.purchaseID="a8g784hjq1mnp3"
```

**Paramètres de configuration** {#section_1808631C96674380BF9C4A6D9A2C568E}

Aucune

**Pièges, questions et conseils** {#section_F5D010F234ED43F19AD1FCD2CD64E060}

The *`purchaseID`* variable allows all conversion variables on the page to be counted only once in reports.

## referrer {#concept_3D8E6A5D30DC4D92982EFA34D4C7F81B}

La variable peut être utilisée pour restaurer les informations de référent perdues.

<!-- 

referrer.xml

 -->

Les redirections JavaScript et côté serveur sont souvent utilisées pour acheminer les visiteurs vers les emplacements appropriés. Cependant, lorsqu’un navigateur est redirigé, l’URL de référence originale est perdue. 

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| 255 octets | R | Trafic &gt; Conversion des méthodes de recherche &gt; Méthodes de recherche | document.referrer |

La plupart des entreprises utilise des redirections sur leurs sites Web. Un visiteur peut ainsi être redirigé à partir des résultats de recherche payante d’un moteur de recherche. Lorsqu’un navigateur est redirigé, il n’est pas rare que le référent soit perdu. La variable peut être utilisée pour restaurer la *`referrer`* *`referrer`* valeur d’origine sur la première page après une redirection. The *`referrer`* may be populated server-side, or via JavaScript from the query string.

Pour qu’Analytics enregistre un référent, celui-ci doit être « bien formé » ; en d’autres termes, il doit être conforme au format URL standard, avec un protocole et un emplacement approprié.

**Syntaxe et valeurs possibles** {#section_A0365D76789C4F4A959E81FE5A9D491D}

```js
s.referrer="URL"
```

La variable *`referrer`*. Assurez-vous que la chaîne respecte le codage URL (pas d’espaces autorisés).

**Exemples** {#section_86FB1577670C4AA18BF3718F0832FCD4}

```js
s.referrer="https://www.google.com/search?q=search+string" 
s.referrer=<%=referrerVar%> // populated server-side  
if(s.getQueryParam('ref') 
s.referrer=s.getQueryParam('ref') 
```

**Paramètres de configuration** {#section_7AAEF28A7CBC446984F32C0659EFBF8D}

Aucune

**Pièges, questions et conseils** {#section_B42BF7FBA1094FF9805707FEA810CFE1}

The *`referrer`* must look like a standard URL and include a protocol.

## resolution {#concept_8CBDDBE710744A3AA09E6B1E1519BF30}

La variable indique la résolution du moniteur du visiteur de la page Web.

<!-- 

resolution.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>This variable should only be read and never set.

Vous pouvez lire ces valeurs et les copier dans props/eVars, mais vous ne pouvez, en aucun cas, les modifier. Cette variable est apparue avec la version H.11 du fichier JavaScript.

| Paramètre de requête | Valeur | Exemple | Rapports concernés |
|---|---|---|---|
| s | LxH | 1680 x 1050 | Trafic &gt; Technologie &gt; Résolution de l’écran |

## s_objectID {#concept_48B50DE6B7E546EBB4D187033F1CAF2B}

The  variable is a global variable that should be set in the [!UICONTROL onClick] event of a link.

<!-- 

s_objectID.xml

 -->

By creating a unique object ID for a link or link location on a page, you can either improve visitor activity tracking or use [!UICONTROL Activity Map] to report on a link type or location, rather than the link URL.

>[!NOTE]
>
>A trailing semicolon (;) is required when using s_objectID with [Activity Map](https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/activitymap-link-tracking-use-case.html).

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| 100 octets | OID | [!UICONTROL Carte]d’activités, [!UICONTROL ClickMap] | URL absolue d’un lien sur lequel l’utilisateur a cliqué |

Trois raisons justifient généralement l’utilisation de la variable *`s_objectID`*:

* Pour agréger l’activité des visiteurs qui change fréquemment au cours d’une journée.
* To separate link activity that [!UICONTROL Activity Map] combines.
* To improve the accuracy of [!UICONTROL Activity Map] data reporting.

**Cumul de clics sur des liens très dynamiques** {#section_BA730A0393B149DDBCAA272C3C23A1C5}

Si votre site est très dynamique et que les liens de certaines pages changent tout au long de la journée, *`s_objectID`* ils peuvent servir à identifier l’emplacement d’un lien sur la page. Si *`s_objectID`* est défini sur "top left 1" ou "top left 2", ce qui représente le premier lien dans le coin supérieur gauche de la page, par exemple, tous les liens qui apparaissent à cet emplacement (ou qui ont *`s_objectID`* la même valeur) sont signalés avec la carte des clics des visiteurs. If you don't use *`s_objectID`*, you see the number of times that a specific link was clicked, but you lose insight into how all the other links in that location were used by visitors to your site.

**Séparation de clics combinés** {#section_1AE91FB8A2D3423CBE064ACF02FEEA47}

If the  variable on your site is used to show the section or template a visitor is viewing, rather than the specific page the visitor is viewing, you may want to use  to separate links that appear on multiple versions of that page template. *`pageName`**`s_objectID`* Supposons, par exemple, que votre site comporte une page de modèle pour l’ensemble des produits qui y sont proposés. Dans ce cas, il est probable qu’il existe, sur toutes les pages, un lien pointant vers votre page d’accueil et vers une zone de recherche. Si vous souhaitez visualiser le mode d’utilisation des liens en fonction de chaque produit (plutôt que sur la base du modèle), vous pouvez renseigner, dans la variable *`s_objectID`* une valeur spécifique telle que « prod 123789 home page » ou « prod 123789 search ». Once completed, [!UICONTROL Activity Map] reports on those links at an individual product basis.

**Improve Activity Map Accuracy**{#section_08B3406821294DCCABEEB99C90CF5C52}

Dans certains cas, les navigateurs autres que Firefox, Internet Explorer, Netscape, Opera et Safari ne figurent pas dans les rapports. Bien qu’il s’agisse d’un pourcentage minime, il fait une différence pour les clics et d’autres mesures. Use *`s_objectID`* within links to uniquely identify the addresses the browser reporting issue. Voici un exemple de mise à jour de vos liens afin d’utiliser *`s_objectID`*:

```js
<a href="/art.jsp?id=559" onClick="s_objectID='top left 1';">Article 559</a> 
<a href="/home.jsp" onClick="s_objectID='prod 123789 home page';">Home</a> 
```

**Syntaxe et valeurs possibles** {#section_85841DF9F06A4680953D9B2A884A1A5A}

La variable s_objectID peut contenir tout identifiant de texte.

```js
s_objectID="unique_id" 
```

La variable *`s_objectID`* n’est concernée par aucune limite, à l’exception des limites standard.

**Exemples** {#section_33F119D532CA4ACAA3426253C42030BB}

```js
s_objectID="top left 2" 
```

```js
s_objectID="prod 123789 search"
```

**Paramètres de configuration** {#section_95396657D55B41ECB66B83D0534EA827}

Aucune

## server {#concept_BF77952603BA454BAFC9A0A81D06A7D2}

La variable est utilisée pour afficher soit le domaine d’une page web (pour indiquer les domaines sur lesquels arrivent les utilisateurs), soit le serveur d’où provient la page (pour une référence rapide de l’équilibrage de charge).

<!-- 

server.xml

 -->

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| 100 octets | server | Serveurs | "" |

Si votre site possède plusieurs domaines qui diffusent le même contenu, vous pouvez utiliser la variable *`server`* pour déterminer ceux qui sont utilisés par les visiteurs. Le code JavaScript ci-dessous renseigne le domaine de la page dans la variable « server ».

```js
s.server=window.location.hostname
```

Si vous utilisez la variable « server » comme référence rapide pour l’équilibrage de charge, vous pouvez indiquer un nom ou un numéro de serveur dans cette variable. Reportez-vous à l’exemple suivant :

```js
s.server="server 14"
```

Bien que le rapport [!UICONTROL Serveurs les plus populaires] puisse être utilisé comme référence rapide de l’équilibrage de charge, il ne constitue pas une mesure précise de la charge serveur. Ainsi, le trafic généré par le bouton Précédent n’augmente pas la charge serveur, mais il est affiché dans les rapports. Le rapport n’indique pas les serveurs qui diffusent des images ou des téléchargements de grande taille.

**Syntaxe et valeurs possibles** {#section_48E4B9BFEBFF4409A246D86EC0C0FB13}

```js
s.server="server_name"
```

There are no limitations on the *`server`* variable outside of the standard variable limitations.

**Exemples** {#section_78B9EE3C27FB491384869E3D0BD503D6}

```js
s.server="server 18" 
s.server=window.location.hostname 
```

**Paramètres de configuration** {#section_969DB379D5BD469FBEE8D505D3000E49}

Aucune

**Pièges, questions et conseils** {#section_42A28F9B01574F38891D9D54B411D8FE}

The *`server`* variable can be used to show which domains are most popular or which servers are serving the most pages.

## state {#concept_82295D22888947BF8B1C76182C635C6C}

Les variables et sont des variables de conversion.

<!-- 

state.xml

 -->

Ces variables sont semblables à des eVars, en ce sens qu’elles capturent des événements. Toutefois, contrairement aux eVars, elles ne sont pas persistantes. Les variables *`zip`* and *`state`* variables are like eVars that expire immediately.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| 50 octets | state | Conversion &gt; Profil du visiteur &gt; État du visiteur | "" |

Because the *`state`* and *`zip`* variables expire immediately, the only events associated with them are events that are fired on the same page on which they are populated. For example, if you are using *`state`* to compare conversion rates by state, you should populate the *`state`* variable on every page of the checkout process. S’agissant des sites de conversion, Adobe conseille d’utiliser l’adresse de facturation comme source du code postal. Vous pouvez toutefois choisir d’utiliser plutôt l’adresse de livraison (à condition qu’il y ait une seule adresse de livraison pour la commande). Un site de médias peut opter pour l’utilisation de *`zip`* and *`state`* for registration or ad click-through tracking.

**Syntaxe et valeurs possibles** {#section_EDD1F5F9EDBC457898E61695F08C1744}

```js
s.state="state"
```

The *`state`* variable does not impose any special value or format restrictions. There are no limitations on *`state`* outside of the standard variable limitations.

**Exemples** {#section_D181B163F79A41D199CA4C70765E583F}

```js
s.state="california" 
```

```js
s.state="prince edward island"
```

**Paramètres de configuration** {#section_DB0D6DC3F4764AC59C11B10D27D2806C}

Aucune

**Pièges, questions et conseils** {#section_02F1620D0BB14AA6A838966FDB9A234F}

* Populate *`state`* on every page that a relevant event is fired (such as each page of the checkout process).
* The *`zip`* and *`state`* variables act like eVars that expire on the Page View.

## timestamp {#concept_D997A2FF4D134C80A614C0BC7A4D7507}

Cette variable permet de personnaliser l’horodatage d’un accès tout comme les bibliothèques AppMeasurement pour d’autres plateformes.

<!-- 

timestamp.xml

 -->

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| 4 octets | Date/Heure | Ne sont pas renseignés directement. | Définie par les serveurs de collecte de données. |

**Syntaxe** {#section_1DF752B1202C4412A301AC7CC10874DF}

```js
s.timestamp="UNIX or ISO-8601 format timestamp"
```

The *`timestamp`* variable must be in the format explained in the next section.

>[!IMPORTANT]
>
>Your report suite must be timestamp-enabled by Customer Care before you can use the *`timestamp`* variable. After timestamp support is enabled, all hits sent to this report suite from JavaScript must have a timestamp manually set (using *`s.timestamp`*) or the hits will not be recorded.
>
>De plus, si vous activez la prise en charge de l’horodatage sur une suite de rapports afin de prendre en charge le suivi hors ligne, tous les accès envoyés à cette suite à partir de JavaScript doivent également être horodatés manuellement (à l’aide de *`s.timestamp`*). Vous ne pouvez pas envoyer à la même suite de rapports des accès horodatés et non horodatés.
>
>Vous pouvez également utiliser le paramètre [Horodatages facultatifs](../../../implement/js-implementation/timestamps-overview.md#concept_1A7DF6F7BDA34467B51A6F61E08BB73F) pour mélanger les données horodatées et non horodatées dans une même suite de rapports globale, envoyer les données horodatées depuis une application mobile à une suite de rapports globale, puis mettre à niveau les applications afin d’employer les horodatages sans avoir à créer une suite de rapports.

**Formats des horodatages** {#section_C12CBCECCD7047D38EF63A5800761CE9}

Les horodatages doivent être au format UNIX (secondes depuis le 1er janvier 1970) ou ISO-8601, avec les restrictions suivantes pour le format ISO-8601 pris en charge :

* La date et l’heure doivent être précisées, séparées par « T ».
* La date doit être une date civile complète (année, mois et jour). . Les dates de semaine et les dates ordinales ne sont pas prises en charge.
* The date can be in standard or extended format ( `YYYY-MM-DD` or `YYYYMMDD`), but they must include the hour and minute. Les secondes sont facultatives ( `HH:MM`, `HH:MM:SS`, `HHMM`ou `HHMMSS`). Les minutes et secondes fractionnaires peuvent être précisées, mais la partie fractionnaire est ignorée.

* An optional time zone can be specified in standard or extended format ( `±HH`, `±HH:MM`, `±HH`, `±HHMM`, or Z)

Les horodatages UNIX sont toujours pris en charge (secondes depuis le 1er janvier 1970).

**Exemples** {#section_FA19C53D70DE4CF2AF259A5B968B84C3}

```js
s.timestamp=Math.round((new Date()).getTime()/1000);
```

```js
s.timestamp="2012-04-20T12:49:31-0700";
```

La liste suivante contient des exemples d’horodatages au format ISO-8601 valide :

```
2013-01-01T12:30:05+06:00 
2013-01-01T12:30:05Z 
2013-01-01T12:30:05 
2013-01-01T12:30
```

**Paramètres de configuration** {#section_5275D206F2CB4009B3681E8C4457124A}

Avant d’utiliser cette variable, le service à la clientèle doit permettre à une suite de rapports d’accepter les horodatages personnalisés. Une fois que les horodatages sont activés, tous les accès envoyés à la suite de rapports doivent contenir un horodatage pour ne pas être ignorés. 

**Pièges, questions et conseils** {#section_EFDE8F67D13C4775A461E0B00D30AFD7}

* Les horodatages servent principalement à effectuer le suivi des données hors connexion sur les plateformes mobiles. En règle générale, les horodatages personnalisés sont désactivés, à moins que vous ne collectiez des données d’application Web et hors connexion dans une même suite de rapports.
* Les données sont horodatées lorsque les données hors ligne sont activées dans le SDK mobile (paramètre par défaut) ou chaque fois qu’une suite de rapports est configurée pour accepter les données horodatées. Les données collectées hors ligne sur les périphériques mobiles peuvent être envoyées des heures ou des semaines après la date où elles sont survenues. Ces accès peuvent être placés en file d’attente dans la plateforme Analytics pendant plus longtemps (minutes ou heures) que les accès sans horodatage :

   * Pour les données horodatées envoyées à un moment très proche de l’heure actuelle, le délai probable est de 10 à 15 minutes.
   * Pour les données horodatées envoyées depuis hier, le délai probable est d’environ 2 heures.
   * Pour les données horodatées envoyées avant hier, comptez 1 heure de délai pour chaque jour, jusqu’à il y a 15 jours, où le délai arrête de s’incrémenter.

* Les données de la session avec horodatage sont conservées pendant 92 jours au maximum.

## trackingServer {#concept_45EE91B1A99B4A37AFAEF1C0A8A6B02F}

La variable est utilisée dans le cadre de l’implémentation des cookies propriétaires, afin d’indiquer le domaine au niveau duquel sont écrits le cookie et la demande d’image.

<!-- 

trackingServer.xml

 -->

Elle est utilisée pour les pages non sécurisées. Si la variable *`trackingServer`* est définie, aucun élément n’est envoyé à 2o7.net. If *`trackingServer`* is not defined (and dc is not defined), data goes to 112.2o7.net.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | "" |

Vous trouverez une liste des centres de données Adobe [ici](https://helpx.adobe.com/analytics/kb/determining-data-center.html).

## trackingServerSecure {#concept_28132A2606E34A2F87BEC9E7ACADC7DD}

La variable est utilisée dans le cadre de l’implémentation des cookies propriétaires, afin d’indiquer le domaine au niveau duquel sont écrits le cookie et la demande d’image.

<!-- 

trackingServerSecure.xml

 -->

Elle est utilisée pour les pages sécurisées. Si cet élément   *`trackingServerSecure`* n’est pas définie, les données SSL sont envoyées à *`trackingServer`*.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | "" |

## stockage {#concept_FBFA55E137E644A2BD97B41E92F6AFEF}

Les [!UICONTROL sources de données d’intégration] utilise une variable [!UICONTROL transactionID] pour lier les données hors ligne à une transaction en ligne (comme un prospect ou un achat généré en ligne).

<!-- 

transactionID.xml

 -->

Each unique *`transactionID`* sent to Adobe is recorded in preparation for a [!UICONTROL Data Sources] upload of offline information about that transaction. Voir [Sources de données](https://marketing.adobe.com/resources/help/en_US/sc/datasources/).

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| 100 octets | xact | n/d | "" |

**Activer le stockage** des identifiants de transaction {#section_3EA2C9DC9D4C4F0FBE4AB67981BCB52E}

Before *`transactionID`* values are recorded, [!UICONTROL Transaction ID Storage] must be enabled for the report suite selected in the Report Suite Manager. Ce paramètre se trouve sous :

```
Analytics > Admin > Report Suites > Edit Settings > General > General Account Settings.
```

Pour déterminer si le *`transactionID Storage`* est activé pour une suite de rapports, sélectionnez

```
Analytics > Admin > Data Sources > Manage
```

**Syntaxe et valeurs possibles** {#section_0C18329203DC45E989DBAE70C0FB4801}

```js
s.transactionID="unique_id"
```

The *`transactionID`* should contain only alphanumeric characters. Si plusieurs [!UICONTROL transactionID] doivent être enregistrés pour un seul accès, vous pouvez séparer les différentes valeurs par une virgule.

**Exemples** {#section_A4C1F0E54CB54AD7B86A22147E9B5FEF}

```js
s.transactionID="11123456"
```

```js
s.transactionID="lead_12345xyz"
```

```js
s.transactionID=s.purchaseID
```

**Pièges, questions et conseils** {#section_4299BAD5D0154DBC88A9EF0E2C252BB4}

* Si *`transactionID`* l’enregistrement n’est pas activé, *`transactionID`* les valeurs sont ignorées et ne peuvent pas être utilisées avec les sources [!UICONTROL de données d’]intégration. Make sure to set a conversion variable or event (an eVar or the events variable) on the page where *`transactionID`* is set. Dans le cas contraire, aucune donnée ne sera enregistrée pour *`transactionID`*.

* If you are recording transactionIDs for multiple systems, such as purchases and leads, make sure the value in  is always unique. *`transactionID`* Pour ce faire, il vous suffit d’ajouter un préfixe à l’identifiant ; par exemple prospect_1234 et achat_1234. [!UICONTROL Les sources] de données d’intégration ne fonctionnent pas comme prévu (les données de la source [!UICONTROL de] données sont liées à des données incorrectes) si une valeur unique *`transactionID`* est vue deux fois.

* Par défaut, *`transactionID`* les valeurs sont mémorisées pendant 90 jours. Si votre processus d’interaction hors ligne dépasse 90 jours, demandez à un agent du service clientèle d’étendre cette limite.

>[!NOTE]
>
>The *`transactionID`* variable can contain any character other than a comma. Elle doit se trouver au même emplacement que celui où est spécifiée la limite de caractères (100 octets). En cas d’utilisation de caractères multi-octets, cette prise en charge doit être activée afin d’éviter les problèmes liés aux caractères inattendus dans la variable *`transactionID`*.

## visitorID {#concept_CD273CC915CC4ABD8F52E4209FF9557E}

Les visiteurs peuvent être identifiés par la variable ou par Adresse IP/Agent utilisateur.

<!-- 

visitorID.xml

 -->

The *`visitorID`* can be up to 100 alpha-numeric characters and must not contain a hyphen.

Si vous avez spécifiquement défini un identifiant personnalisé, celui-ci sera toujours utilisé avant d’autres méthodes d’identification.

Voici l’ordre à utiliser : s.visitorID &gt; s_vi &gt; s_fid &gt; IP/UA.

| ** Taille maximale** | ** Paramètre du débogueur** | ** Rapports renseignés** | ** Valeur par défaut** |
|---|---|---|---|
| 100 octets | vid | n/d | "" |

**Syntaxe et valeurs possibles** {#section_5F768C7AE6824557997E92B295C09280}

```js
s.visitorID="visitor_id"
```

>[!NOTE]
>
>The *`visitorID`* variable should not contain a hyphen.

**Exemples** {#section_F7F07FEFAC3644A5A084D166ACE1315E}

```js
s.visitorID="abc123"
```

**Paramètres de configuration** {#section_582B376FE55C4BCA8F978E0F62B5DB54}

Aucune

## visitorNamespace {#concept_8369DDB3830C4BF2905F1CFC8C8B0D92}

La variable identifie le domaine avec lequel les cookies sont définis.

<!-- 

visitorNamespace.xml

 -->

If *`visitorNamespace`* is used in your JavaScript file, do not delete or alter it. If *`visitorNamespace`* changes, all visitors reported in Analytics may become new visitors. L’historique des visiteurs est déconnecté du trafic actuel et futur. Ne modifiez pas cette variable sans l’accord d’un représentant Adobe.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | ns | N/D | "" |

Analytics utilise un cookie pour identifier de façon unique les visiteurs de votre site. If *`visitorNamespace`* is not used, the cookie is associated 2o7.net. If *`visitorNamespace`* is used, the cookie is associated with a sub-domain of 2o7.net. Les cookies de tous les visiteurs de votre site doivent être associés au même domaine ou sous-domaine.

L’utilisation de la variable *`visitorNamespace`*&#x200B;évite la surcharge potentielle de la limite des cookies du navigateur. Internet Explorer impose une limite de 20 cookies par domaine. En utilisant la variable *`visitorNamespace`* les cookies Analytics des autres sociétés n’entreront pas en conflit avec ceux de vos visiteurs.

**Syntaxe et valeurs possibles** {#section_EE247FE371784CA4B6058182181F3EA1}

The value of *`visitorNamespace`* must be provided by Adobe and is a string of ASCII characters that don't contain commas, periods, spaces, or special characters.

```js
s.visitorNamespace="company_specific_value"
```

**Identification des visiteurs dans les suites de rapports** {#section_7AC5A97FC8C045DD8850245A62BB09F4}

If you do not specify a `visitorNamespace`, each report suite in your company receives its own visitor ID cookie written as `s_vi_[random string]`. Si vous spécifiez la variable `visitorNamespace`, le même cookie `s_vi` sera utilisé pour toutes les suites de rapports qui envoient des données à la variable `trackingServer` spécifiée. Si vous avez mis en œuvre un balisage multisuite, veillez à spécifier l’espace de noms du visiteur afin que le même cookie soit utilisé par chaque suite de rapports.

**Exemples** {#section_89A95852AB9446E794AD3283B8800B09}

```js
s.visitorNamespace="company_name"
```

```js
s.visitorNamespace="Adobe"
```

**Paramètres de configuration** {#section_1128A2531ECC43DFA6749ECC21F050A2}

Aucune

## zip {#concept_C1DF93083553410DA36EAB61FBFDF69A}

The  and  variables are conversion variables.

<!-- 

zip.xml

 -->

Ces variables sont semblables à des eVars, en ce sens qu’elles capturent des événements. Toutefois, contrairement aux eVars, elles ne sont pas persistantes. Les variables *`zip`* and *`state`* variables are like eVars that expire immediately.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| 50 octets | zip | Conversion &gt; Profil du visiteur &gt; Codes postaux | "" |

Dans la mesure où les variables *`state`* and *`zip`* variables expire immediately, the only events associated with them are events fired on the same page that are populated. For example, if you are using *`zip`* to compare conversion rates by Zip Code, you should populate *`zip`* on every page of the checkout process. Adobe conseille d’utiliser l’adresse de facturation comme source du code postal. Vous pouvez toutefois choisir d’utiliser plutôt l’adresse de livraison (à condition qu’il y ait une seule adresse de livraison pour la commande). Un site de médias peut opter pour l’utilisation de *`zip`* and *`state`* for registration or ad click-through tracking.

**Syntaxe et valeurs possibles** {#section_5EDCFCAC8FC241D1B4CC777996858CD7}

```js
s.zip="zip_code"
```

The *`zip`* variable does not impose any value or format restrictions. There are no limitations on *`zip`* outside of the standard variable limitations.

**Exemples** {#section_F25C0D0CC3C04B81892A662CD605C593}

```js
s.zip="92806"
```

```js
s.zip="92806-4115"
```

**Paramètres de configuration** {#section_7987084EECC34DD38B643B94F82385CA}

Aucune

**Pièges, questions et conseils** {#section_E86774D5CE8B40EFA36353CDEE3A84D0}

* Renseignez la variable [!UICONTROL zip] sur chaque page sur laquelle un événement pertinent est déclenché (chaque page du processus de passage en caisse, par exemple).
* The *`zip`* and *`state`* variables act like eVars that expire on the Page View.

