---
description: Utilisez la description des champs de Dynamic Tag Management pour personnaliser le code de page lors du déploiement d’Analytics.
keywords: Gestion dynamique des balises ; personnaliser le code de page ; open editor ; execute
seo-description: Utilisez la description des champs de Dynamic Tag Management pour personnaliser le code de page lors du déploiement d’Analytics.
seo-title: Personnalisation du code de page
solution: Marketing Cloud, Analytics, Target, gestion dynamique des balises
title: Personnalisation du code de page
uuid: b 7 cad 069-3 eb 8-4388-b 0 b 0-34 f 54001 e 05 f
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Personnalisation du code de page

Utilisez la description des champs de Dynamic Tag Management pour personnaliser le code de page lors du déploiement d’Analytics.

Ajoutez des modules externes pour veiller à ce que le code s’exécute en même temps que l’outil Analytics. Pour plus d’informations sur les modules externes d’Analytics, voir  [Modules externes de mise en œuvre](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

**[!UICONTROL *`Property`*]** &gt;** [! UICONTROL ![](assets/settings_gear.png)

Edit Tool]** &gt; **[!UICONTROL Customize Page Code]**

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
   <td colname="col2"> <p>Vous pouvez insérer un appel JavaScript qui doit être déclenché avant l’appel final de <code>s.t()</code> contenu dans <code>s_code</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exécuter </p> </td> 
   <td colname="col2"> <p> <b>Avant les paramètres de l’IU</b> : les paramètres de l’interface prévalent sur le code personnalisé (par exemple, si vous souhaitez remplacer une eVar si un paramètre de l’interface a été activé). </p> <p> <b>Après les paramètres de l’IU</b> : le code personnalisé prévaut sur les paramètres de l’interface. </p> </td> 
  </tr> 
 </tbody> 
</table>

