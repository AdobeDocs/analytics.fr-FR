---
description: Cette section contient la description des champs de Dynamic Tag Management pour le suivi des liens lors du déploiement d’Analytics.
keywords: Dynamic Tag Management;link tracking;enable clickmap;track download links;download extensions;track outbound links;keep url parameters
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: Suivi des liens
uuid: 982b744b-5696-4c31-b1d1-410486b0eedd
translation-type: tm+mt
source-git-commit: 354785439a5920d8fc53d566fa9306c74e2504d2
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 96%

---


# Suivi des liens

Cette section contient la description des champs de Dynamic Tag Management pour le suivi des liens lors du déploiement d’Analytics.

**[!UICONTROL Propriété]** > Icône ![](assets/settings_gear.png) Gear > **[!UICONTROL Modifier l’outil]** > Suivi des **[!UICONTROL liens]**

<table id="table_F23FB0B284E74B66A107B1D69D22A51C">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Élément </th>
   <th colname="col2" class="entry"> Description </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Enable ClickMap (Activer ClickMap) </td>
   <td colname="col2"> <p>Permet de déterminer si les données de mise en correspondance des clics des visiteurs sont collectées. </p> <p>Voir <a href="../../../vars/config-vars/trackinlinestats.md">trackInlinestats</a>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Track download links (Suivi des liens de téléchargement) </td>
   <td colname="col2"> <p>Permet d’effectuer le suivi des liens vers des fichiers téléchargeables de votre site. </p> <p>See <a href="../../../vars/config-vars/trackdownloadlinks.md">trackDownloadLinks</a>.</p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> Download Extensions (Téléchargement d’extensions) </td> 
   <td colname="col2"> <p>Si votre site contient des liens vers des fichiers dotés des extensions répertoriées, les URL de ceux-ci figurent dans les rapports. </p>Voir <a href="../../../vars/config-vars/linkdownloadfiletypes.md">linkDownloadFileTypes</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> Track outbound links (Suivi des liens sortants) </td>
   <td colname="col2"> <p>Permet de déterminer si un lien faisant l’objet d’un clic est un lien de sortie. </p> <p>Voir <a href="../../../vars/config-vars/trackexternallinks.md">trackExternalLinks</a>. </p> <p><b>Points à prendre en compte concernant les applications d’une seule page :</b> en raison du codage de certains sites web d’applications d’une seule page, un lien interne sur le site peut ressembler à un lien sortant. </p> <p>Vous pouvez utiliser l’une des méthodes suivantes pour suivre les liens sortants à partir des sites des applications d’une seule page : </p>
    <ul id="ul_A4179633ED0644C3BA5F548A58CA4EC9">
     <li id="li_1959FBF14E42469FA8724B37EB58BC54"> <p>Si vous ne souhaitez pas suivre les liens sortants à partir de vos applications monopages, insérez une entrée dans la section <span class="wintitle">Ne jamais effectuer de suivi</span>. </p> <p>Par exemple, <span class="filepath">https://testsite.com/spa/#</span> </p> <p>Tous les liens # vers cet hôte sont ignorés. Tous les autres liens sortants vers d’autres hôtes tels que <span class="filepath">https://www.google.com</span> sont suivis. </p> </li>
     <li id="li_37DD4D37887243FB928C9C04ACE9D39E"> <p>Si vous souhaitez suivre certains liens sur vos applications monopages, utilisez la section <span class="wintitle">Toujours effectuer le suivi</span>. </p> <p>Par exemple, si vous disposez d’une page <span class="filepath">spa/#/about</span>, vous pouvez insérer "about" dans la section <span class="wintitle">Toujours effectuer le suivi</span>. </p> <p>La page "about" est le seul lien sortant qui est suivi. Tous les autres liens de la page (<span class="filepath">https://www.google.com</span>, par exemple) ne sont pas suivis. </p> </li>
    </ul> <p>Notez que ces deux options s’excluent mutuellement. </p> </td> 
  </tr>
  <tr>
   <td colname="col1"> Conserver les paramètres d’URL </td>
   <td colname="col2"> <p>Permet de conserver les chaînes de requête. </p> <p>Voir <a href="../../../vars/config-vars/linkleavequerystring.md">linkLeaveQueryString</a>. </p> </td>
  </tr>
 </tbody>
</table>
