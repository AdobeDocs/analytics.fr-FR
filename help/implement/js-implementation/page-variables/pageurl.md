---
description: Les variables de page renseignent directement un rapport (pageName, props de liste, variables de liste, etc.).
keywords: Analytics Implementation
subtopic: Variables
title: Variables de page
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# pageURL

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

> [!NOTE] Bien qu’Adobe autorise des valeurs *`pageURL`* égales à 64 Ko, certains navigateurs imposent une limite de taille à l’URL de demandes d’image. Pour éviter que d’autres données ne soient tronquées, les URL de page de plus de 255 octets sont fractionnées, les 255 premiers octets apparaissant dans le paramètre `g=`, les autres apparaissant plus tard dans la chaîne de requête, dans le paramètre de requête `-g=`.

**Syntaxe et valeurs possibles** {#section_22AF3BF7C2F743549967B0C760A095C0}

La variable *`pageURL`* doit être une URL valide avec un protocole valide. En fonction des paramètres définis dans Analytics, il est possible que la chaîne de requête soit altérée. De plus, le domaine fait l’objet d’un affichage forcé en minuscules avant d’être renseigné dans les rapports.

```js
s.pageURL="proto://domain/path?query_string"
```

Seuls les caractères compatibles avec l’URL sont acceptés comme URL de la page.

> [!NOTE] Il est vivement conseillé de contacter votre conseiller ou l’assistance clientèle Adobe avant d’utiliser la variable *`pageURL`* à des fins personnalisées.

**Exemples** {#section_45158FDA3F8F4574BDEB5CBC9F7E6C97}

```js
s.pageURL="https://mysite.com/home.jsp?id=1224" 
```

```js
s.pageURL="https://www.mysite.com/"
```

**Paramètres de configuration** {#section_A8F77DAD88164528ACC5C16C066B47DF}

Aucun

