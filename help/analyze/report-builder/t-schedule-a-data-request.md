---
description: Vous pouvez planifier l’envoi des rapports en fonction de l’heure et du format de fichier définis.
seo-description: Vous pouvez planifier l’envoi des rapports en fonction de l’heure et du format de fichier définis.
seo-title: Planification d'une requête de données
solution: Analytics
title: Planification d'une requête de données
topic: Créateur de rapports
uuid: f 6 d 8 c 90 f-e 185-4 d 60-8035-f 20 f 74 bfcd 89
translation-type: tm+mt
source-git-commit: 6a70b32b576cc7b5b6a6f0037d98e35b3f8c1426

---


# Planification d'une requête de données

Vous pouvez planifier l’envoi des rapports en fonction de l’heure et du format de fichier définis.

**Pour planifier une requête de données**

1. Générez un rapport et enregistrez-le.
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]**.

   L’onglet [!UICONTROL Rapports programmés] affiche un récapitulatif de toutes les tâches que vous avez créées, ainsi que le nombre de tâches restantes.
1. Sur l’onglet **Rapports programmés**, cliquez sur **[!UICONTROL Nouveau]**.
1. L’Assistant de planification - Options de base s’affiche :

   ![](assets/simple-schedule-wizard.png)

1. Dans [!UICONTROL l’Assistant de planification - Options de base], configurez les options suivantes :

* **Sélectionner un rapport**: Nom du rapport. Dans le cas des nouveaux rapports programmés, ce champ contient le nom du classeur actif.

<table id="table_6D5B1B832EB0451293F1902E2A1D1068"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Champ </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Sélectionner le rapport </p> </td> 
   <td colname="col2"> <p>Nom du rapport. Dans le cas des nouveaux rapports programmés, ce champ contient le nom du classeur actif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sélectionner </p> </td> 
   <td colname="col2"> <p>Affiche la page <span class="wintitle">Sélectionner le rapport</span>. Vous pouvez sélectionner un rapport sur le serveur (où sont stockés tous les classeurs déjà programmés) ou sur votre machine locale. Si vous sélectionnez un classeur sur le disque local au format <span class="filepath">.xls</span>, le système convertit le fichier au format <span class="filepath">.xlsx</span>. Dans le cadre de cette conversion, le fichier est ouvert dans Excel et rendu actif. Si le classeur sélectionné pour le rapport planifié porte le même nom de fichier que celui ouvert actuellement dans Excel, le système sélectionne le fichier local au lieu de celui transféré précédemment. Si vous sélectionnez un rapport dans le référentiel de planification, une copie du classeur est créée sur le serveur (le chiffre 1 est ajouté à son nom de fichier) et le nouveau rapport planifié utilise le classeur copié. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Personnaliser </p> </td> 
   <td colname="col2"> <p>Vous permet de personnaliser le format de date. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A </p> </td> 
   <td colname="col2"> <p>Affiche le Carnet d’adresses Outlook, le cas échéant. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Envoyer à : Courriel </p> </td> 
   <td colname="col2"> <p>Adresse électronique du destinataire du rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Envoyer à : Liste de publication </p> </td> 
   <td colname="col2"> <p>Répertorie les listes de distribution disponibles pour cette société. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Power BI </p> </td> 
   <td colname="col2"> <p>Voir <a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#section_BA137EA92A46483F83BB5C1C40FBA002" format="dita" scope="local">Publier le classeur sur Microsoft Power BI</a> pour en savoir plus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Objet </p> </td> 
   <td colname="col2"> <p>Description définie par l’utilisateur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Planification </p> </td> 
   <td colname="col2"> <p> Vous permet d’indiquer le moment où le rapport doit être envoyé (Immédiatement, Horaire, Quotidiennement, Hebdomadairement, Mensuellement et Annuellement). </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL Advanced Delivery Options]** to configure file and publishing options:

<table id="table_1BA8A5600DE94A33B83B096E69CE15F3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Champ </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Onglet <b>Planification</b> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Heure de remise </p> </td> 
   <td colname="col2"> <p>Cette option permet d’envoyer immédiatement le rapport ou de planifier une remise différée. L’heure indiquée est fonction du fuseau horaire défini sur votre ordinateur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modèle de répétition </p> </td> 
   <td colname="col2"> <p>Le rapport est envoyé sur la base des options sélectionnées. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Plage de répétition </p> </td> 
   <td colname="col2"> <p>Vous permet d’indiquer les heures de début et de fin de réception du rapport. </p> <p> <p>Remarque : si vous planifiez un rapport le premier jour d’une période en cours (semaine, mois, trimestre ou année), le système renverra uniquement les données relatives à ce jour. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Onglet <b>Options de fichier</b> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Format du fichier </p> </td> 
   <td colname="col2"> <p>Permet de sélectionner le format de remise : Excel 2007 (<span class="filepath">.xlsx</span>) ou 2003 (<span class="filepath">.xls</span>), <span class="filepath">.pdf</span>, <span class="filepath">.csv</span>, <span class="filepath">.mht</span>, <span class="filepath">.txt</span> et <span class="filepath">.xml</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Description du fichier </p> </td> 
   <td colname="col2"> <p> Précise E-mail ou FTP. Les options disponibles sur cette page varient en fonction de la sélection. Dans le cas de FTP, vous devez vous assurer que l’hôte est disponible en externe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Liste de publication </p> </td> 
   <td colname="col2"> <p> Si vous envoyez le rapport planifié à plusieurs listes de publication, il s’exécute une fois pour chaque liste. Les suites de rapports variables sont remplacées par celle qui est affectée à la liste de publication. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Langue du contenu du fichier </p> </td> 
   <td colname="col2"> <p>Indique la langue que vous souhaitez utiliser pour la lettre d’envoi. Vous avez le choix entre l’allemand, le portugais (du Brésil), le chinois (simplifié ou traditionnel), le coréen, l’espagnol, le français ou le japonais. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Onglet <b>Options de publication</b> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Publication sur Power Bi </p> </td> 
   <td colname="col2"> 
    <ul id="ul_40697E4FB2CE4F34B857FBF153D6D6D5"> 
     <li id="li_023E4750814D415EBC899269C9EA5D46"><a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#section_BA137EA92A46483F83BB5C1C40FBA002" format="dita" scope="local"> Publier le classeur sur Power BI</a> </li> 
     <li id="li_9B684BE22AF94ABC903405EE83951A80"><a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#section_E48148793E794169B766C73995897B9F" format="dita" scope="local"> Publier toutes les requêtes du Créateur de rapports sous forme de jeux de données Power BI</a> </li> 
     <li id="li_7B0BD285BC1749D1B2C65759CA97877B"><a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#section_6F8422B90D3F4F7EB5D4C97BFFA807AD" format="dita" scope="local"> Publier tous les tableaux formatés sous forme de jeux de données Power BI</a> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Intituler ce rapport Power BI par </p> </td> 
   <td colname="col2"> <p>Informations d’intitulé </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL OK]**, then click **[!UICONTROL Exit]**.

   Le Créateur de rapports affiche le rapport planifié dans le [Gestionnaire de tâches planifiées](../../analyze/report-builder/r-arb-scheduled-reports.md#section_69306B8D833F4DF7BBFA53753B0E6C31).
