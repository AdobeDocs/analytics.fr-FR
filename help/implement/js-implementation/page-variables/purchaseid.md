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


# purchaseID

La variable permet d’éviter qu’une commande ne soit comptée plusieurs fois dans les rapports.


<!-- 

purchaseID.xml

 -->

Lorsque l’événement d’[!UICONTROL achat] est utilisé sur votre site, vous devez employer la variable *`purchaseID`*.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| 20 octets | purchaseID | Conversion &gt; Achats &gt; Revenus issus des conversions | "" |

Lorsqu’un visiteur achète un article sur votre site, la variable *`purchaseID`* est renseignée sur la page de remerciement, à l’endroit où est déclenché l’événement d’[!UICONTROL achat]. Si la variable *`purchaseID`* est renseignée, les produits figurant sur la page de remerciement sont comptabilisés une seule fois par *`purchaseID`*. Il s’agit là d’un point essentiel, car de nombreux visiteurs de votre site enregistrent la page de remerciement ou de confirmation à des fins personnelles. La variable *`purchaseID`* évite que les achats ne soient comptabilisés lors de chaque consultation de la page.

Outre le fait d’empêcher que les données d’achat ne soient comptabilisées deux fois, la variable *`purchaseID`*, lorsqu’elle est utilisée, permet de ne pas comptabiliser deux fois toutes les données de conversion dans les rapports.

**Syntaxe et valeurs possibles** {#section_E352CE2370D54BA69A368E1F63A9C32D}

```js
s.purchaseID="unique_id"
```

La variable *`purchaseID`* peut contenir, au maximum, 20 caractères ASCII standard.

**Exemples** {#section_60A5C1EAF42F4611898CD6A4F4CF5A28}

```js
s.purchaseID="11223344" 
s.purchaseID="a8g784hjq1mnp3"
```

**Paramètres de configuration** {#section_1808631C96674380BF9C4A6D9A2C568E}

Aucun

**Pièges, questions et conseils** {#section_F5D010F234ED43F19AD1FCD2CD64E060}

La variable *`purchaseID`* permet à toutes les variables de conversion de n’être comptabilisées qu’une seule fois dans les rapports.
