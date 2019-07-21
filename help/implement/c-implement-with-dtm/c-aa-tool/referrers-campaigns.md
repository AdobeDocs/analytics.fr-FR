---
description: Cette section décrit les champs de Dynamic Tag Management pour les options de référent et de campagne lors du déploiement de Dynamic Tag Management dans Adobe Analytics.
keywords: Gestion dynamique des balises ; référents ; campagnes ; referrer override ; variable de campagne ; query param
seo-description: Cette section décrit les champs de Dynamic Tag Management pour les options de référent et de campagne lors du déploiement de Dynamic Tag Management dans Adobe Analytics.
seo-title: Référents et campagnes
solution: Marketing Cloud, Analytics, gestion dynamique des balises
title: Référents et campagnes
uuid: 56580206-a 382-4993-9 bba-a 488 da 65 cf 89
translation-type: tm+mt
source-git-commit: e271cf73e7fd31d8893ed57112f2f3bb7821fbdd

---


# Référents et campagnes

Field descriptions in [!UICONTROL Dynamic Tag Management] for referrers and campaign options when deploying [!UICONTROL Dynamic Tag Management] in Adobe [!DNL Analytics].

**[!UICONTROL *`Property`*]** &gt; ![](assets/settings_gear.png)**[!UICONTROL Modifier l'outil]** &gt; **[!UICONTROL Référents et campagnes]**

<table id="table_09AE3BFF0F12442F9C19CD96451F93E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Remplacement du référent </td> 
   <td colname="col2"> <p>Permet de remplacer la valeur définie dans la variable <span class="varname"> variable s. referrer</span> , qui est généralement renseignée par le référent défini dans le navigateur. </p> <p>Voir [Variables de page] (/help/implementation/js-implementation/c-variables/page-variables. md). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campagne </td> 
   <td colname="col2"> <p>Variable qui identifie les campagnes marketing utilisées pour rediriger les utilisateurs vers votre site. La valeur de cette variable provient généralement d’un paramètre de chaîne de requête. </p> <p>Voir [Variables de page] (/help/implementation/js-implementation/c-variables/page-variables. md). </p> </td> 
  </tr> 
 </tbody> 
</table>

Utilisez l’interface de la gestion dynamique des balises pour choisir si vous voulez utiliser une chaîne de requête ou une valeur (qui peut être extraite d’un élément de données) :

![](assets/dtm-queryparam.png)

Vous pouvez saisir directement la chaîne de requête dans l’interface ou vous pouvez référencer un élément de données distinct si vous disposez d’autres moyens pour suivre une campagne.
