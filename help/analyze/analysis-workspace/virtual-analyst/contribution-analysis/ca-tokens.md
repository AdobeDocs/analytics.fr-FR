---
description: valeur nulle
seo-description: valeur nulle
seo-title: Présentation de l'analyse des contributions
title: Présentation de l'analyse des contributions
uuid: 2 bd 295 b 0-c 5 ce -4443-86 af -024 efd 20 c 021
translation-type: tm+mt
source-git-commit: ca632da6b6181298af4b313fbd232926fbbfa125

---


# Présentation de l&#39;analyse des contributions

## Contribution Analysis Tokens - overview {#section_3EF8D2BBCE6E4C309D753BCF04A453D0}

>[!IMPORTANT]
>
>L&#39;analyse des contributions a été supprimée du jeu de fonctionnalités des rapports et analyses et n&#39;est désormais disponible que via Analysis Workspace.

Tous les clients autorisés à utiliser l’analyse des contributions peuvent exécuter une analyse complète un nombre limité de fois par mois dans Analysis Workspace. Cela **exclut** les clients (SiteCatalyst 15) du produit, les clients d’Analytics Foundation et les clients d’Analytics Select, qui n’obtiennent aucune analyse de contributions.

Le nombre d’exécutions par société est limité à un certain nombre de jetons mensuels attribués en fonction du produit Adobe Analytics acquis par la société. Cela inclut la possibilité de restreindre l’accès à l’analyse des contributions pour éviter l’usage impropre des jetons.

## Questions fréquentes {#section_11D0431AD2014B96AB9561CA66A367CE}

<table id="table_357775E5058644099E26B15A6790E8AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Réponse </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Pourquoi Adobe a-t-il introduit des jetons ? </b> </p> </td> 
   <td colname="col2"> <p>L’analyse des contributions a été l’une des fonctionnalités les plus intéressantes d’Adobe Analytics depuis sa sortie en 2015. En autorisant un petit nombre d’exécutions « complètes » par mois (plutôt que seulement 3 dimensions pour certains produits Analytics), vous pouvez mieux voir ce que l’analyse des contributions complète illimitée peut vous apporter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Comment fonctionnent les jetons dans l’analyse des contributions ? Le chargement d’un projet avec une analyse des contributions existante coûte-t-il un jeton ? Ou ce coût existe-t-il uniquement lors de l’exécution d’une nouvelle analyse ?</b> </p> </td> 
   <td colname="col2"> <p>Chaque société de connexion (et non chaque utilisateur) obtient un certain nombre de jetons par mois, ce qui permet d’exécuter une analyse des contributions « complète » dans Analysis Workspace. </p> <p>Chaque fois que vous générez une nouvelle analyse des contributions, vous payez un jeton. Le chargement de projets avec des analyses des contributions pré-exécutées ne coûte pas de jeton. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Les jetons s’appliquent-ils à l’analyse des contributions dans les Reports &amp; Analytics ?</b> </p> </td> 
   <td colname="col2"> <p>Non. L’analyse des contributions n’est plus disponible dans les Reports &amp; Analytics à compter de la version d’avril 2018. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Si ma société n’a plus de jetons et souhaite exécuter des analyses des contributions supplémentaires, que pouvons-nous faire ?</b> </p> </td> 
   <td colname="col2"> <p>Vous pouvez passer à une autre version d’Adobe Analytics, par exemple de Standard (2 jetons/mois) à Ultimate (20 jetons/mois). Vous ne pouvez pas acheter plus de jetons : vous devez effectuer une mise à niveau dans le cadre de la structure de package existante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Comment puis-je restreindre l’accès à l’analyse des contributions ?</b> </p> </td> 
   <td colname="col2"> <p>By default, only admins have access to run Contribution Analyses, but admins can grant access to other users by creating a permission group in the <a href="https://https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html" format="html" scope="external"> Admin Console </a>. Vous devez accorder l'autorisation d'utiliser l'analyse des contributions uniquement pour les utilisateurs qui ont une raison légitime de l'utiliser et qui sont approuvés pour n'avoir pas accès à leur accès. </p> <p>L’autorisation est appelée « Analyse des contributions » sous <span class="ignoretag"><span class="uicontrol">Analytics</span> &gt; <span class="uicontrol">Admin</span> &gt; <span class="uicontrol">Gestion utilisateur</span> &gt; <span class="uicontrol">Modifier les groupes</span> &gt; <span class="uicontrol">Modifier l’accès à tous les rapports</span> &gt; <span class="uicontrol">Personnaliser les outils de suites de rapports</span> &gt; <span class="uicontrol">Outils et rapports</span></span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Comment puis-je connaître le nombre de jetons auxquels ma société a droit par mois et combien de jetons avons-nous utilisés durant le mois en cours ?</b> </p> </td> 
   <td colname="col2"> <p>Accédez à <span class="ignoretag"><span class="uicontrol">Admin</span> &gt; <span class="uicontrol">Paramètres de la société</span> &gt; <span class="uicontrol">Afficher les niveaux d’accès aux fonctions</span></span>. Cette page comporte 2 nouveaux éléments : </p> <p><img placement="break"  src="assets/ca_access_level.png" id="image_16012FE1162C485EA768D175F43D7563" width="500px" /> </p> </td> 
  </tr> 
 </tbody> 
</table>


## Anomaly Detection and Contribution Analysis entitlements {#section_9278D58F21A840AA9B1ED1BD07A1EF0A}

Vous trouverez ci-dessous une liste des autorisations détaillées pour la détection des anomalies et l’analyse des contributions dans Analysis Workspace.

>[!IMPORTANT]
>
>La détection des anomalies et l’analyse des contributions ont été supprimées de l’ensemble de fonctionnalités Reports &amp; Analytics et sont désormais disponibles uniquement via Analysis Workspace. Remarque : Les clients Adobe Analytics Select et Adobe Analytics Foundation ne profitent que d’une détection des anomalies « à granularité journalière » dans Workspace.

<table id="table_5C9B7E4AE82640B5A913519E576889B5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Droit Adobe Analytics </th> 
   <th colname="col2" class="entry"> Détection des anomalies </th> 
   <th colname="col3" class="entry"> Analyse des contributions </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Foundation </p> </td> 
   <td colname="col2"> <p>Granularité quotidienne uniquement </p> </td> 
   <td colname="col3" colsep="1"> <p>Aucun jeton </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://www.adobe.com/data-analytics-cloud/analytics/select.html?promoid=B4XQ3X7G&amp;mv=other" format="html" scope="external">Select</a> </p> </td> 
   <td colname="col2"> <p>Granularité quotidienne uniquement </p> </td> 
   <td colname="col3"> <p>Aucun jeton </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://www.adobe.com/data-analytics-cloud/analytics/prime.html?promoid=91BF51TR&amp;mv=other" format="html" scope="external">Prime</a> </p> </td> 
   <td colname="col2"> <p>Oui </p> </td> 
   <td colname="col3"> <p>10 jetons par mois </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html?promoid=8N4B5F1V&amp;mv=other" format="html" scope="external"> Ultimate</a> </p> </td> 
   <td colname="col2"> <p>Oui </p> </td> 
   <td colname="col3"> <p>20 jetons par mois </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>+Predictive Workbench </p> </td> 
   <td colname="col2"> <p>Oui </p> </td> 
   <td colname="col3"> <p>Jetons illimités </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standard </p> 
    <ul id="ul_73D52020793B44868C9CE0F90893075D"> 
     <li id="li_21EE0871C87E43C8B781219B2BA0FA74">Adobe Analytics Core </li> 
     <li id="li_AB3593200F33439BAEE8FEB13CAE57F4">Adobe Analytics OD </li> 
     <li id="li_2B7D625519BC4A4CB598C95F15D3029B">Adobe Analytics MA </li> 
    </ul> </td> 
   <td colname="col2"> <p>Oui </p> </td> 
   <td colname="col3"> <p>2 jetons par mois </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premium (360, Attribution) </p> </td> 
   <td colname="col2"> <p>Oui </p> </td> 
   <td colname="col3"> <p>2 jetons par mois </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premium (Complete, <a href="https://www.adobe.com/data-analytics-cloud/analytics/predictive-intelligence.html" format="html" scope="external">Predictive Intelligence</a>) </p> </td> 
   <td colname="col2"> <p>Oui </p> </td> 
   <td colname="col3"> <p>Jetons illimités </p> </td> 
  </tr> 
 </tbody> 
</table>
