---
description: Utilisez la description des champs de Dynamic Tag Management pour personnaliser le code de page lors du déploiement d’Analytics.
keywords: Dynamic Tag Management;personnaliser le code de page;ouvrir l’éditeur;exécuter
seo-description: Utilisez la description des champs de Dynamic Tag Management pour personnaliser le code de page lors du déploiement d’Analytics.
seo-title: Personnalisation du code de page
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Personnalisation du code de page
uuid: b7cad069-3eb8-4388-b0b0-34f54001e05f
translation-type: tm+mt
source-git-commit: 2fc1a01aced4cf2b165b46353418fbee9b83bee5

---


# Personnalisation du code de page

Utilisez la description des champs de Dynamic Tag Management pour personnaliser le code de page lors du déploiement d’Analytics.

Ajoutez des modules externes pour veiller à ce que le code s’exécute en même temps que l’outil Analytics. Pour plus d’informations sur les modules externes d’Analytics, voir [Modules externes de mise en œuvre](/help/implement/js-implementation/plugins/impl-plugins.md).

**[!UICONTROL *`Property`*]** &gt; **[!UICONTROL   ![](assets/settings_gear.png)

Modifier l’outil]** &gt; **[!UICONTROL Personnaliser le code de page]**

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
   <td colname="col2"> <p>You can insert any JavaScript call that must be triggered before the final <code> s.t()</code> call, which is contained in the <code> s_code</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exécuter </p> </td> 
   <td colname="col2"> <p> <b>Avant les paramètres de l’IU</b> : les paramètres de l’interface prévalent sur le code personnalisé (par exemple, si vous souhaitez remplacer une eVar si un paramètre de l’interface a été activé). </p> <p> <b>Après les paramètres de l’IU</b> : le code personnalisé prévaut sur les paramètres de l’interface. </p> </td> 
  </tr> 
 </tbody> 
</table>

