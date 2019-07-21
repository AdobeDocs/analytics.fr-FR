---
description: Cette section contient la description des champs de Dynamic Tag Management pour le suivi des liens lors du déploiement d’Analytics.
keywords: Gestion dynamique des balises ; suivi des liens ; activer clickmap ; suivre les liens de téléchargement ; télécharger des extensions ; suivre les liens sortants ; conserver les paramètres d'URL
seo-description: Cette section contient la description des champs de Dynamic Tag Management pour le suivi des liens lors du déploiement d’Analytics.
seo-title: Suivi des liens
solution: Marketing Cloud, Analytics, gestion dynamique des balises
title: Suivi des liens
uuid: 982 b 744 b -5696-4 c 31-b 1 d 1-410486 b 0 eedd
translation-type: tm+mt
source-git-commit: 1bc1c7a1e00d7b59cd39f368ac9afb745bea9e47

---


# Suivi des liens

Cette section contient la description des champs de Dynamic Tag Management pour le suivi des liens lors du déploiement d’Analytics.

**[!UICONTROL *`Property`*]** &gt;** [! UICONTROL ![](assets/settings_gear.png)

Edit Tool]** &gt; **[!UICONTROL Link Tracking]**

<table id="table_F23FB0B284E74B66A107B1D69D22A51C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Activer ClickMap </td> 
   <td colname="col2"> <p>Permet de déterminer si les données de mise en correspondance des clics des visiteurs sont collectées. </p> <p>Voir  <a href="../../../implement/js-implementation/c-variables/configuration-variables.md#concept_8FCA630706334F54B4DCB607378BCD00" format="dita" scope="local"> s.trackInlineStats</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Suivi des liens de téléchargement </td> 
   <td colname="col2"> <p>Permet d’effectuer le suivi des liens vers des fichiers téléchargeables de votre site. </p> <p>Voir [Variables de configuration] (/help/implementation/js-implementation/c-variables/configuration-variables. md).</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Extensions de téléchargement </td> 
   <td colname="col2"> <p>Si votre site contient des liens vers des fichiers dotés des extensions répertoriées, les URL de ceux-ci figurent dans les rapports. </p>Voir [Variables de configuration] (/help/implementation/js-implementation/c-variables/configuration-variables. md). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Suivi des liens sortants </td> 
   <td colname="col2"> <p>Permet de déterminer si un lien faisant l’objet d’un clic est un lien de sortie. </p> <p>Voir [Variables de configuration] (/help/implementation/js-implementation/c-variables/configuration-variables. md). </p> <p><b>Points à prendre en compte concernant les applications monopages :</b> en raison du codage de certains sites web d’application monopage, un lien interne sur le site peut ressembler à un lien sortant. </p> <p>Vous pouvez utiliser l’une des méthodes suivantes pour suivre les liens sortants à partir des sites des applications monopages : </p> 
    <ul id="ul_A4179633ED0644C3BA5F548A58CA4EC9"> 
     <li id="li_1959FBF14E42469FA8724B37EB58BC54"> <p>Si vous ne souhaitez pas suivre les liens sortants à partir de vos applications monopages, insérez une entrée dans la section <span class="wintitle">Ne jamais effectuer de suivi</span>. </p> <p>For example, <span class="filepath"> https://testsite.com/spa/#</span> </p> <p>Tous les liens # vers cet hôte sont ignorés. All outbound links to other hosts are tracked, such as <span class="filepath"> https://www.google.com</span>. </p> </li> 
     <li id="li_37DD4D37887243FB928C9C04ACE9D39E"> <p>Si vous souhaitez suivre certains liens sur vos applications monopages, utilisez la section <span class="wintitle">Toujours effectuer le suivi</span>. </p> <p>Par exemple, si vous disposez d’une page <span class="filepath">spa/#/about</span>, vous pouvez insérer "about" dans la section <span class="wintitle">Toujours effectuer le suivi</span>. </p> <p>La page "about" est le seul lien sortant qui est suivi. Any other links on the page (for example, <span class="filepath"> https://www.google.com</span>) are not tracked. </p> </li> 
    </ul> <p>Notez que ces deux options s’excluent mutuellement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Conserver les paramètres d’URL </td> 
   <td colname="col2"> <p>Permet de conserver les chaînes de requête. </p> <p>Voir [Variables de configuration] (/help/implementation/js-implementation/c-variables/configuration-variables. md). </p> </td> 
  </tr> 
 </tbody> 
</table>

