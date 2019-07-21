---
description: Création d’un élément de données dans Dynamic Tag Management.
keywords: Gestion dynamique des balises ; data element ; créer un élément de données ; name ; type ; valeur par défaut ; forcer la valeur en minuscules ; mémoriser cette valeur pour
seo-description: Création d’un élément de données dans Dynamic Tag Management.
seo-title: Création d’un élément de données
solution: Marketing Cloud, Analytics, Target, gestion dynamique des balises
title: Création d’un élément de données
uuid: eacd 5 c 60-6197-4129-a 9 e 1-a 39 e 9 a 58 b 38 a
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Création d’un élément de données

Création d’un élément de données dans Dynamic Tag Management.

1. [Créez une propriété web](../../implement/c-implement-with-dtm/t-create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123), si ce n’est pas déjà fait.
1. Dans la propriété web, cliquez sur **Règles** &gt; **[!UICONTROL Eléments de données]**.
1. Cliquez sur **[!UICONTROL Créer un élément de données]**.
1. Renseignez les champs et options suivants :

   <table id="choicetable_681F7D5B86534FF0B6DB67E117B8E381"> 
    <thead class="chhead sthead"> 
      <th class="choptionhd"> Option</th> 
      <th class="chdeschd"> Description</th> 
    </thead> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Nom</strong></td> 
      <td class="chdesc stentry"> <p>Nom convivial de l’élément de données qu’un spécialiste du marketing peut facilement identifier. Par exemple : 
        <code>
          ID de produit
        </code>. </p> <p> <p>Remarque : Le nom est référencé par le créateur de règles, et non par un ID. Si vous modifiez le nom de l’élément de données, vous devez changer sa référence dans chaque règle qui l’utilise. </p> </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Type</strong></td> 
      <td class="chdesc stentry"> <p> Indique d’où sont extraites les données : objet JS Object, sélecteur CSS, cookie, paramètres d’URL ou script personnalisé. </p> <p>Selon le type que vous avez sélectionné, différentes options s’affichent. Voir <a href="https://marketing.adobe.com/resources/help/en_US/dtm/data_elements.html" format="html" scope="external">Types d’éléments de données</a> dans la documentation du produit Dynamic Tag Management pour obtenir plus d’informations ainsi que des exemples. </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Valeur par défaut</strong></td> 
      <td class="chdesc stentry"> <p>Élément par défaut. Cette valeur permet de s’assurer que l’élément de données possède toujours une valeur, même si un paramètre d’URL n’existe pas ou est introuvable. </p> <p> <p>Remarque : S’il n’existe pas de valeur ni de valeur pas défaut, rien n’est renvoyé. Les variables référençant cet élément de données ne sont pas définies. Le champ de valeur par défaut est également ignoré s’il s’agit d’un élément de données « code personnalisé ». </p> </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Forcer l’utilisation de minuscules pour la valeur</strong> </td> 
      <td class="chdesc stentry"> <p>Dynamic Tag Management met automatiquement la valeur en minuscules. </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Mémoriser cette valeur pour</strong></td> 
      <td class="chdesc stentry"> <p>Durée pendant laquelle Dynamic Tag Management doit mémoriser cette valeur. </p> <p> Les valeurs valides sont les suivantes : </p> 
      <ul id="ul_52F6CD8FC22942208F3F45492E914104"> 
        <li id="li_32E4366C5B2E46D788CD8478620FE3E0"> <p>Session : la durée de la session varie selon l’implémentation. Les éléments de données de session sont définis sur le cookie de session. Ce paramètre peut toutefois reposer sur le serveur web ou le navigateur. Il n’est pas lié à la session utilisée dans les Reports &amp; Analytics marketing. </p> </li> 
        <li id="li_8A944564BF7643E4B21F0EF2394B3FE8"> <p>Pageview </p> </li> 
        <li id="li_5C8A2F2392FD475AA89DDA7D5B5CF88B"> <p>Visitor </p> </li> 
      </ul> </td> 
    </tr> 
   </table>

   Voir [Éléments de données](https://marketing.adobe.com/resources/help/en_US/dtm/data_elements.html) dans la documentation du produit Tag Management d’Adobe pour plus d’informations sur l’utilisation des éléments de données.
1. Cliquez sur **[!UICONTROL Enregistrer l’élément de données]**.
