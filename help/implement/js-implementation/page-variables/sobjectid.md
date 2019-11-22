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


# s_objectID

La variable  est une variable globale qui doit être définie dans l’événement [!UICONTROL onClick] d’un lien.


<!-- 

s_objectID.xml

 -->

En créant un identifiant d’objet unique pour un lien ou emplacement de lien sur une page, vous pouvez améliorer le suivi des activités des visiteurs ou utiliser [!UICONTROL Activity Map] pour créer des rapports sur un emplacement ou un type de lien plutôt que sur l’URL du lien.

> [!NOTE] Un point-virgule de fin (;) est requis lors de l’utilisation de s_objectID avec [Activity Map](https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/activitymap-link-tracking-use-case.html).

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| 100 octets | OID | [!UICONTROL Activity Map], [!UICONTROL ClickMap] | URL absolue d’un lien sur lequel l’utilisateur a cliqué |

Trois raisons justifient généralement l’utilisation de la variable *`s_objectID`* :

* Pour agréger l’activité des visiteurs qui change fréquemment au cours d’une journée.
* Pour séparer l’activité des liens combinée par [!UICONTROL Activity Map].
* Pour améliorer l’exactitude des rapports de données [!UICONTROL Activity Map].

**Cumul de clics sur des liens très dynamiques** {#section_BA730A0393B149DDBCAA272C3C23A1C5}

Si votre site est très dynamique et que les liens de certaines pages changent tout au long de la journée, *`s_objectID`* peut servir à identifier l’emplacement d’un lien sur la page. Si *`s_objectID`* est défini sur « top left 1 » ou « top left 2 », ce qui représente le premier lien dans le coin supérieur gauche de la page, par exemple, tous les liens qui apparaissent à cet emplacement (ou qui ont *`s_objectID`* défini sur la même valeur) sont signalés avec la mise en correspondance des clics des visiteurs. Si vous n’utilisez pas la variable *`s_objectID`*, le nombre de clics effectués sur un lien spécifique est indiqué. En revanche, vous n’avez aucune indication quant à la manière dont tous les autres liens situés à cet emplacement ont été utilisés par les visiteurs de votre site.

**Séparation de clics combinés** {#section_1AE91FB8A2D3423CBE064ACF02FEEA47}

Si la variable *`pageName`* de votre site est utilisée pour afficher la section ou le modèle qu’un visiteur consulte, plutôt que la page spécifique qu’il affiche, vous pouvez utiliser *`s_objectID`* pour séparer les liens qui apparaissent sur plusieurs versions de ce modèle de page. Supposons, par exemple, que votre site comporte une page de modèle pour l’ensemble des produits qui y sont proposés. Dans ce cas, il est probable qu’il existe, sur toutes les pages, un lien pointant vers votre page d’accueil et vers une zone de recherche. Si vous souhaitez visualiser le mode d’utilisation des liens en fonction de chaque produit (plutôt que sur la base du modèle), vous pouvez renseigner, dans la variable *`s_objectID`* une valeur spécifique telle que « prod 123789 home page » ou « prod 123789 search ». Ensuite, [!UICONTROL Activity Map] génère des rapports sur ces liens en fonction de chaque produit.

**Améliorer la précision[!UICONTROL d’Activity Map]** {#section_08B3406821294DCCABEEB99C90CF5C52}

Dans certains cas, les navigateurs autres que Firefox, Internet Explorer, Netscape, Opera et Safari ne figurent pas dans les rapports. Bien qu’il s’agisse d’un pourcentage minime, il fait une différence pour les clics et d’autres mesures. L’utilisation de *`s_objectID`* dans les liens pour les identifier de manière unique corrige le problème de suivi du navigateur. Voici un exemple de mise à jour de vos liens afin d’utiliser *`s_objectID`*:

```js
<a href="/art.jsp?id=559" onClick="s_objectID='top left 1';">Article 559</a> 
<a href="/home.jsp" onClick="s_objectID='prod 123789 home page';">Home</a> 
```

**Syntaxe et valeurs possibles** {#section_85841DF9F06A4680953D9B2A884A1A5A}

La variable s_objectID peut contenir tout identifiant de texte.

```js
s_objectID="unique_id" 
```

*`s_objectID`* n’est concerné par aucune limite, à l’exception des limites standard.

**Exemples** {#section_33F119D532CA4ACAA3426253C42030BB}

```js
s_objectID="top left 2" 
```

```js
s_objectID="prod 123789 search"
```

**Paramètres de configuration** {#section_95396657D55B41ECB66B83D0534EA827}

Aucun
