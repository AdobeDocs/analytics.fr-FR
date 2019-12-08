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


# pageType

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

The *`pageType`* variable captures the errant URL when a 404 Error page is displayed, which allows you to quickly find broken links and paths that are no longer valid on the custom site. Configurez la variable *`pageType`* sur la page d’erreur exactement comme illustré ci-dessous.

N’utilisez pas la variable de nom de page sur les pages de type Erreur 404. La variable *`pageType`* concerne exclusivement la page Erreur 404.

Dans la plupart des cas, cette page est une page statique qui est codée en dur. La référence au fichier .JS doit alors être définie sur un chemin/répertoire relatif ou global approprié.

**Syntaxe et valeurs possibles** {#section_C1C59968226446559B05F6EE7374D525}

La seule valeur autorisée de *`pageType`* est « errorPage », comme illustré ci-dessous.

```js
s.pageType="errorPage"
```

**Exemples** {#section_6CE22FCB835B4A19B633B7F67E73A115}

```js
s.pageType="errorPage"
```

**Paramètres de configuration** {#section_3B304A6D3A6C48F2BE90B4DA92A39DDB}

Aucun

**Pièges, questions et conseils** {#section_943681AB01FE47BEAC72E93CB60C53C8}

Pour capturer d’autres erreurs côté serveur (des erreurs 500, par exemple), utilisez une prop afin de capturer le message d’erreur, puis indiquez « `500 Error: <URL>` » (où `<URL>` est l’URL demandée) dans la variable *`pageName`*. En suivant cette méthodologie, vous pouvez utiliser des rapports [!UICONTROL Cheminement] afin d’afficher les chemins empruntés par les utilisateurs pour générer des erreurs 500. La prop explique le message d’erreur généré par le serveur.

