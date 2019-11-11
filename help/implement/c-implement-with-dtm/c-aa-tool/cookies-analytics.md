---
description: Cette section contient la description des champs des paramètres généraux des cookies utilisés pour le déploiement de Dynamic Tag Management dans Adobe Analytics.
keywords: Dynamic Tag Management;cookies;identifiant visiteur;espace de noms du visiteur;nombre de points du domaine;nombres de points du domaine fp;id de transaction;durée de vie des cookies
seo-description: Cette section contient la description des champs des paramètres généraux des cookies utilisés pour le déploiement de Dynamic Tag Management dans Adobe Analytics.
seo-title: Cookies
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: Cookies
uuid: 9c81ecbb-0f02-4c1a-a5a5-426cdea57f38
translation-type: tm+mt
source-git-commit: 9b946238b48fa4532d136d2f7aa0187fdabd005b

---


# Cookies

Cette section contient la description des champs des paramètres généraux des cookies utilisés pour le déploiement de [!UICONTROL Dynamic Tag Management] dans Adobe Analytics.

*`Property`* &gt; Modifier l’outil &gt; Cookies

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
   <td colname="col2"> <p>Domaine sur lequel les cookies <code> s_cc</code> et <code> s_sq</code> sont définis en déterminant le nombre de points contenus dans le domaine de l’URL de la page. Elle est également utilisée par certains modules externes pour déterminer le domaine correct afin de définir le cookie du module externe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre de points du domaine FP </td> 
   <td colname="col2"> <p>La variable <span class="term"> fpCookieDomainPeriods</span> variable is for cookies set by JavaScript (<code> s_sq</code>, <code> s_cc</code>, plug-ins) that are inherently first-party cookies, even if your implementation uses the third-party <span class="filepath"> 2o7.net</span> or <span class="filepath"> omtrdc.net</span> domains. </p> <p>Voir <a href="/help/implement/js-implementation/c-variables/configuration-variables.md"  > s.fpCookieDomainPeriods</a>. </p> </td> 
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

