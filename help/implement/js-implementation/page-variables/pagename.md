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


# pageName

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

Pour renseigner la variable *`pageName`*, il convient d’utiliser une valeur reconnue par les utilisateurs de l’entreprise. Dans la plupart des cas, la valeur *`pageName`* n’est pas l’URL ou le chemin d’accès au fichier. Les valeurs *`pageName`* courantes sont généralement des noms tels que « Page d’accueil », « Passage en caisse », « Merci de votre achat » ou « Enregistrement ».

Veillez à ne pas autoriser l’affichage de caractères de nouvelle ligne, de tirets cadratins ou tirets courts, ou encore de tout caractère HTML dans le nom de la page et dans d’autres variables. Certains navigateurs envoient des caractères de nouvelle ligne, ce qui provoque le fractionnement des données d’Analytics entre deux noms de page apparemment identiques. De nombreux programmes de traitement de texte et clients de messagerie convertissent automatiquement un trait d’union en tiret cadratin ou tiret court lors de la saisie. Dans la mesure où ces deux tirets sont des caractères interdits dans les variables Analytics (car il s’agit de caractères ASCII dont le code est supérieur à 127), Analytics n’enregistre pas le nom de page où ils apparaissent et affiche, à la place, l’URL de la page.

Si la valeur *`pageName`* n’est pas renseignée, l’URL est utilisée pour représenter le nom de la page. Le fait de laisser la variable *`pageName`* vide s’avère généralement problématique, car l’URL n’est pas nécessairement toujours la même pour une page `www.mysite.com` et `mysite.com` font référence à la même page avec des URL différentes).

**Syntaxe et valeurs possibles** {#section_7A61EE70F1A84D26B414404998C84BA8}

La variable *`pageName`* doit contenir un identifiant utile pour les utilisateurs professionnels d’Analytics.

```js
s.pageName="page_name"
```

*`pageName`* n’est concerné par aucune limite, à l’exception des limites standard.

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

Assurez-vous que la valeur *`pageName`* ne contient pas de caractères interdits.
