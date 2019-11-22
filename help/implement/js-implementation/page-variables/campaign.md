---
description: Les variables de page renseignent directement un rapport (pageName, props de liste, variables de liste, etc.).
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variables de page
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---



# campaign

La variable identifie les campagnes marketing utilisées pour amener les visiteurs sur votre site. La valeur de  provient généralement d’un paramètre de chaîne de requête.
https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/page-variables/browserheight.html

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

Les deux méthodes principales permettant de renseigner la variable *`campaign`* sont les suivantes :

* Le module externe [!UICONTROL getQueryParam], utilisé dans le fichier JavaScript, récupère un paramètre de chaîne de requête de l’URL. Pour plus d’informations sur le module externe [!UICONTROL getQueryParam], reportez-vous à la section [Modules externes de mise en œuvre](/help/implement/js-implementation/plugins/impl-plugins.md).

* Attribuez une valeur à la variable *`campaign`* dans le code HTML de la page web.

Quelle que soit la méthode utilisée pour renseigner la variable *`campaign`*, le trafic du bouton Retour peut gonfler le nombre réel de clics publicitaires à partir d’un élément de campagne.

Par exemple, un visiteur parvient sur votre site en cliquant sur un mot-clé de recherche payante. Lorsqu’il arrive sur la page d’entrée, l’URL contient un paramètre de chaîne de requête qui identifie le code de suivi du mot-clé. Il clique ensuite sur un lien pointant vers une autre page, puis il clique immédiatement sur le bouton Précédent pour revenir sur la page d’entrée. Lors de sa deuxième visite sur la page d’entrée, l’URL contenant le paramètre de chaîne de requête identifie à nouveau le code de suivi. Un deuxième clic publicitaire est alors enregistré, ce qui a pour effet de gonfler artificiellement le nombre des clics.

Pour éviter l’accroissement anarchique des clics publicitaires, Adobe conseille d’utiliser le module externe [!UICONTROL getValOnce] de telle sorte que chaque clic publicitaire soit comptabilisé une seule fois par session. Pour plus d’informations sur le module externe [!UICONTROL getValOnce], reportez-vous à la section [Modules externes de mise en œuvre](/help/implement/js-implementation/plugins/impl-plugins.md).

**Syntaxe et valeurs possibles** {#section_91A141841A6D4711A1EE08A6145A301D}

```js
s.campaign="112233"
```

La variable *`campaign`* présente les mêmes limites que toutes les autres variables. Adobe conseille de limiter la valeur aux caractères ASCII standard.

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

* Pour éviter l’accroissement anarchique des clics publicitaires, utilisez le module externe [!UICONTROL getValOnce], de telle sorte que chaque clic publicitaire soit comptabilisé une seule fois par session. Pour plus d’informations sur le module externe [!UICONTROL getValOnce], reportez-vous à la section [Modules externes de mise en œuvre](/help/implement/js-implementation/plugins/impl-plugins.md).

* Pour plus d’informations sur le suivi des campagnes marketing et les achats de mots-clés, reportez-vous à la section [Campagnes](https://marketing.adobe.com/resources/help/en_US/reference/campaign.html).
* Utilisez le [!DNL DigitalPulse Debugger] pour connaître la valeur réelle des campagnes (v0 dans le débogueur). Si v0 n’apparaît pas dans le débogueur, aucune donnée de campagne n’est enregistrée pour cette page.
