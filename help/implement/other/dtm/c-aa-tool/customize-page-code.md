---
description: Utilisez la description des champs de Dynamic Tag Management pour personnaliser le code de page lors du déploiement d’Analytics.
keywords: Dynamic Tag Management;customize page code;open editor;execute
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Personnalisation du code de page
uuid: b7cad069-3eb8-4388-b0b0-34f54001e05f
translation-type: tm+mt
source-git-commit: 4b6107fe57787e639fb06ef957d6230d1bc45bd1
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 95%

---


# Personnalisation du code de page

Utilisez la description des champs de Dynamic Tag Management pour personnaliser le code de page lors du déploiement d’Analytics.

**[!UICONTROL `Property`]** > **[!UICONTROL Modifier l’outil]** ![](assets/settings_gear.png) > **[!UICONTROL Personnaliser le code de page]**

<table id="table_A4676A5FEE814DF9A05DA0E56F8B4C6D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ouvrir l’éditeur </p> </td> 
   <td colname="col2"> <p>Vous pouvez insérer un appel JavaScript qui doit être déclenché avant l’appel final de <code> s.t()</code> contenu dans <code> s_code</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exécuter </p> </td> 
   <td colname="col2"> <p> <b>Avant les paramètres de l’IU</b> : les paramètres de l’interface prévalent sur le code personnalisé (par exemple, si vous souhaitez remplacer une eVar si un paramètre de l’interface a été activé). </p> <p> <b>Après les paramètres de l’IU</b> : le code personnalisé prévaut sur les paramètres de l’interface. </p> </td> 
  </tr> 
 </tbody> 
</table>

