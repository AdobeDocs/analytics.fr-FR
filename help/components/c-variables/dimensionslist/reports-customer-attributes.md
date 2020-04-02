---
description: Questions fréquentes liées à Analytics portant sur les attributs du client et sur la manière d’exécuter le rapport Attributs du client.
solution: Experience Cloud,Analytics
title: Attributs du client
uuid: 94721265-ba23-45d5-8807-76f81b0b8a30
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Attributs du client

Questions fréquentes liées à Analytics portant sur les attributs du client et sur la manière d’exécuter le rapport Attributs du client.

**[!UICONTROL Rapports]** > **[!UICONTROL Profil du visiteur]** > **[!UICONTROL Attributs du client]**

Si vous capturez les données clients d’entreprise dans une base de données de gestion de la relation client, vous pouvez les transférer dans une source de données d’attributs du client dans Experience Cloud. Vous pouvez ensuite exécuter le rapport Attributs du client dans les Reports &amp; Analytics.

* [Attributs du client et mesures de création de rapports dans Analytics](/help/components/c-variables/dimensionslist/reports-customer-attributes.md#section_EF343662146B460A882D3DF772ADD86D)
* [Questions fréquentes – Attributs du client dans Analytics](/help/components/c-variables/dimensionslist/reports-customer-attributes.md#section_E29641D1F3D649C1AC9EA5231921F038)

Voir [Attributs du client](https://marketing.adobe.com/resources/help/fr_FR/mcloud/attributes.html) dans l’aide d’Experience Cloud pour en savoir plus sur le transfert des données d’attributs du client.

## Attributs du client et mesures de création de rapports dans Analytics  {#section_EF343662146B460A882D3DF772ADD86D}

Après avoir transféré les attributs du client et validé le schéma (dans Experience Cloud), le système crée les mesures d’après les noms conviviaux (du type *`age`* ou *`gender`*) que vous mappez aux chaînes et entiers d’attribut. Ces mesures apparaissent dans les rapports **[!UICONTROL Profil du visiteur]** > **[!UICONTROL Attributs du client]**.

Par exemple :

**[!UICONTROL Profil du visiteur]** > **[!UICONTROL Attributs du client]** > **[!UICONTROL Age]**

![](assets/report_age.png)

**Exemple – Mesures d’âge**

Si vous spécifiez une chaîne du type *`age`*, le système crée les mesures et dimensions suivantes :

* Dimension Age : vous permet d’exécuter un rapport d’après l’attribut Age.
* Mesure Age : mesure que vous pouvez ajouter à un rapport, par exemple un rapport Visiteurs uniques.
* Mesure Nombre de Age : vous permet de comprendre, par exemple, si les visiteurs ont spécifié une valeur  *`age`* sur un formulaire.

Puisque les mesures sont des sommes dans un tableau de rapports, envisagez de  [créer une mesure calculée](https://marketing.adobe.com/resources/help/fr_FR/analytics/calcmetrics/) qui vous indique l’âge moyen. La formule de cette mesure est `Age / Count of Age`.

## Questions fréquentes – Attributs du client dans Analytics {#section_E29641D1F3D649C1AC9EA5231921F038}

<table id="table_88631069013B408EBB0A810657662B36"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Réponse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Pourquoi est-il préférable d’utiliser le service d’identité pour définir l’ID de client plutôt que de le renseigner dans une prop ou une eVar ? </p> </td> 
   <td colname="col2"> <p>L’utilisation du service d’identité offre plusieurs avantages : </p> 
    <ul id="ul_5D3659604D43419F9CA5920B4F93728E"> 
     <li id="li_BA2EF0715C5A47EFAFA7191CFAD088A4">Si vous ne définissez pas l’ID de client avec le service d’identité, les dossiers du client sont disponibles uniquement pour Adobe Analytics. Pour utiliser les dossiers du client pour le ciblage en temps réel, vous devez utiliser le service d’identité. </li> 
     <li id="li_228358684E474A298E39578D427BF932">Le recours au service d’identité pour définir l’ID de client réduit le temps nécessaire pour synchroniser les identifiants avec Experience Cloud. Si vous placez l’ID de client dans une prop ou une eVar, les ID de client sont envoyés vers Experience Cloud lors de la synchronisation du serveur principal qui survient par lots. Le service d’identité synchronise immédiatement l’ID de client avec Experience Cloud. </li> 
     <li id="li_BCF28219E4014FCF9F747C3D8D270526"> Le fait d’utiliser le service d’identité plutôt qu’une prop ou une eVar libère cette prop ou cette eVar pour d’autres fins. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Si je stocke déjà un ID de client dans une prop ou une eVar, pourquoi devrais-je utiliser cette nouvelle fonctionnalité plutôt que de classer mes prop ou eVar avec des attributs de gestion de la relation client ? </p> </td> 
   <td colname="col2"> <p>Les prop et eVar sont soumises à des limitations de valeurs uniques dépassées. Grâce à cette fonctionnalité, vous pouvez importer des données d’attribut pour un nombre illimité d’ID de client. En outre, le recours à la méthode prop/eVar limite les informations de gestion de la relation client à Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Comment s’affichent mes attributs de gestion de la relation client dans Adobe Analytics ? </p> </td> 
   <td colname="col2"> <p>Les attributs de gestion de la relation client seront manifestes dans Analysis Workspace, les Reports &amp; Analytics, les Ad Hoc Analysis, l’API de création de rapports et le Report Builder. Les attributs textuels apparaîtront sous forme de rapports et dimensions. Les attributs numériques apparaîtront sous forme de dimensions et de mesures. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Les données de gestion de la relation client seront-elles disponibles dans Data Warehouse et dans les flux de données ? </p> </td> 
   <td colname="col2"> <p>Les données de gestion de la relation client ne sont actuellement pas disponibles dans Data Warehouse ou dans les flux de données Analytics. </p> </td> 
  </tr> 
 </tbody> 
</table>

