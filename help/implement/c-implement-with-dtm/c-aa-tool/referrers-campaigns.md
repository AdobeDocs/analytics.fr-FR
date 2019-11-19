---
description: Cette section décrit les champs de Dynamic Tag Management pour les options de référent et de campagne lors du déploiement de Dynamic Tag Management dans Adobe Analytics.
keywords: Dynamic Tag Management;referrers;campaigns;referrer override;campaign variable;query param
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: Référents et campagnes
uuid: 56580206-a382-4993-9bba-a488da65cf89
translation-type: tm+mt
source-git-commit: e9820869d16b8656ebebe11e397a3d7d8123fbcf

---


# Référents et campagnes

Cette section décrit les champs de [!UICONTROL Dynamic Tag Management] pour les options de référent et de campagne lors du déploiement de [!UICONTROL Dynamic Tag Management] dans Adobe [!DNL Analytics].

**[!UICONTROL *`Property`*]** &gt; ![](assets/settings_gear.png) **[!UICONTROL Modifier l’outil]** &gt; **[!UICONTROL Référents et campagnes]**

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
   <td colname="col2"> <p>Permet de remplacer la valeur définie dans la variable Variable <span class="varname"> s.referrer,</span>, qui correspond généralement au référent défini dans le navigateur. </p> <p>Voir <a href="/help/implement/js-implementation/page-variables/page-variables.md">Variables de page</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campagne </td> 
   <td colname="col2"> <p>Variable qui identifie les campagnes marketing utilisées pour rediriger les utilisateurs vers votre site. La valeur de cette variable provient généralement d’un paramètre de chaîne de requête. </p> <p>See [<a href="/help/implement/js-implementation/page-variables/campaign.md">Page Variables</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

Utilisez l’interface de la gestion dynamique des balises pour choisir si vous voulez utiliser une chaîne de requête ou une valeur (qui peut être extraite d’un élément de données) :

![](assets/dtm-queryparam.png)

Vous pouvez saisir directement la chaîne de requête dans l’interface ou vous pouvez référencer un élément de données distinct si vous disposez d’autres moyens pour suivre une campagne.
