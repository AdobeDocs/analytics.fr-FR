---
description: Cette section contient la description des champs des paramètres généraux des cookies utilisés pour le déploiement de Dynamic Tag Management dans Adobe Analytics.
keywords: Gestion dynamique des balises;cookies;id visiteur;espace de noms du visiteur;périodes du domaine;périodes du domaine fp;ID de transaction;durée de vie du cookie
seo-description: Cette section contient la description des champs des paramètres généraux des cookies utilisés pour le déploiement de Dynamic Tag Management dans Adobe Analytics.
seo-title: Cookies
solution: Experience Cloud,Analytics,Gestion dynamique des balises
title: Cookies
uuid: 9c81ecbb-0f02-4c1a-a5a5-426cdea57f38
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Cookies

Field descriptions for the Cookies global settings used for deploying [!UICONTROL Dynamic Tag Management] in Adobe Analytics.

**[!UICONTROL *`Property`*]** &gt; **[!UICONTROL ![](assets/settings_gear.png)

Edit Tool]** &gt; **[!UICONTROL Cookies]**

<table id="table_2758C770C91B4025AD74009B360D71F7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Identifiant visiteur </td> 
   <td colname="col2"> <p>Valeur unique qui représente un client dans les systèmes en ligne et hors ligne. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Espace de nom du visiteur </td> 
   <td colname="col2"> <p>Variable permettant d’identifier le domaine avec lequel les cookies sont définis. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> Nombre de points du domaine </td> 
   <td colname="col2"> <p>Domaine sur lequel les cookies <code>s_cc</code> et <code>s_sq</code> sont définis en déterminant le nombre de points contenus dans le domaine de l’URL de la page. Elle est également utilisée par certains modules externes pour déterminer le domaine correct afin de définir le cookie du module externe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre de points du domaine FP </td> 
   <td colname="col2"> <p>La variable <span class="term"> fpCookieDomainPeriods</span> variable is for cookies set by JavaScript (<code> s_sq</code>, <code> s_cc</code>, plug-ins) that are inherently first-party cookies, even if your implementation uses the third-party <span class="filepath"> 2o7.net</span> or <span class="filepath"> omtrdc.net</span> domains. </p> <p>Voir <a href="../../../implement/js-implementation/c-variables/configuration-variables.md#concept_8FCA630706334F54B4DCB607378BCD00" format="dita" scope="local"> s.fpCookieDomainPeriods</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID de transaction </td> 
   <td colname="col2"> <p>Valeur unique qui représente une transaction en ligne issue d’une activité hors ligne. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Durée de vie du cookie </td> 
   <td colname="col2"> <p>Permet de déterminer la durée de vie d’un cookie. </p> </td> 
  </tr> 
 </tbody> 
</table>

