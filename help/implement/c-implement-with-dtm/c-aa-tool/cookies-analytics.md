---
description: Cette section contient la description des champs des paramètres généraux des cookies utilisés pour le déploiement de Dynamic Tag Management dans Adobe Analytics.
keywords: Gestion dynamique des balises ; cookies ; identifiant visiteur ; espace de noms du visiteur ; périodes de domaine ; fp domain points ; transaction id ; durée de vie du cookie
seo-description: Cette section contient la description des champs des paramètres généraux des cookies utilisés pour le déploiement de Dynamic Tag Management dans Adobe Analytics.
seo-title: Cookies
solution: Marketing Cloud, Analytics, gestion dynamique des balises
title: Cookies
uuid: 9 c 81 ecbb -0 f 02-4 c 1 a-a 5 a 5-426 cdea 57 f 38
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Cookies

Field descriptions for the Cookies global settings used for deploying [!UICONTROL Dynamic Tag Management] in Adobe Analytics.

**[!UICONTROL *`Property`*]** &gt;** [! UICONTROL ![](assets/settings_gear.png)

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
   <td colname="col2"> <p>La variable <span class="term"> Fpcookiedomainperiods</span> concerne les cookies définis par JavaScript (<code> s_ sq</code>, <code> s_ cc</code>, plug-ins) qui sont intrinsèquement des cookies propriétaires, même si votre implémentation utilise les domaines tiers <span class="filepath"> 2 o 7. net</span> ou <span class="filepath"> omtrdc. net</span> . </p> <p>See <a href="../../../implement/js-implementation/c-variables/configuration-variables.md#concept_8FCA630706334F54B4DCB607378BCD00" format="dita" scope="local"> s.fpCookieDomainPeriods</a>. </p> </td> 
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

