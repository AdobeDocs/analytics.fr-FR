---
description: L'assistant d'intégration des connecteurs de données vous guide tout au long du processus d'intégration des connecteurs de données.
seo-description: L'assistant d'intégration des connecteurs de données vous guide tout au long du processus d'intégration des connecteurs de données.
seo-title: Exécution de l'assistant d'intégration des connecteurs de données
title: Exécution de l'assistant d'intégration des connecteurs de données
uuid: 714417 f 7-c 1 df -4 e 61-a 07 f-d 319 f 6581 c 9 c
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Running the Data Connectors Integration Wizard{#running-the-data-connectors-integration-wizard}

L'assistant d'intégration des connecteurs de données vous guide tout au long du processus d'intégration des connecteurs de données.

Pour configurer l'intégration :

1. Connectez-vous à Marketing Cloud.
1. Sur la page d'accueil d'Adobe Analytics, cliquez sur l'icône Connecteurs de données sur la pulsation ou la barre d'outils.
1. Sur la page Connecteurs de données, sélectionnez la suite de rapports dans laquelle vous souhaitez configurer l'intégration.

   >[!NOTE]
   >
   >Make sure that you select the desired report suite from the **Report Suite** drop-down list in the upper-left corner of the Data Connectors page.

1. Click the **Alphabetical** tab at the top of the **Partner List** on the left side of the Data Connectors UI, then locate the **Datran** icon.
1. Drag the **Datran** icon to an empty plug-in slot in your Adobe Analytics report suite to launch the Data Connectors Integration Wizard.

1. On the Datran Integration introduction page, review the text, then select the check box to accept the fees associated with the integration, then click **Next**.

   Cette page présente un aperçu de l’intégration, ainsi que des liens utiles conduisant vers davantage d’informations. Cette intégration engendre des frais Adobe et Datran. Contactez votre représentant commercial au sujet des deux organisations et veillez à comprendre la structure des frais.
1. Sur chaque page de l'assistant d'intégration des connecteurs de données, fournissez les informations requises, comme décrit dans le tableau suivant :

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" valign="top" align="left" class="entry"> <p><b>WIZARD PAGE #</b> </p> </th> 
   <th colname="col2" class="entry"> <p><b>FIELD</b> </p> </th> 
   <th colname="col3" class="entry"> <p><b>DESCRIPTION</b> </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2" valign="top" align="left"> <p>Nom d’intégration </p> </td> 
   <td colname="col3"> <p>Spécifiez le nom d'intégration affiché par les Connecteurs de données dans la liste d'intégration active de la suite de rapports. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>Adresse de courriel d’intégration </p> </td> 
   <td colname="col3"> <p>Specify the email address that receives all notifications related to this integration, then click <b>Next</b> to proceed to Step 2 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>ID de compte </p> </td> 
   <td colname="col3"> <p>Specify your Datran Account ID (the unique identifier assigned to your organization by Datran), then click <b>Next</b> to proceed to Step 3 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>ID de message </p> </td> 
   <td colname="col3"> <p>Identifiez l'evar Adobe Analytics utilisée pour le suivi de l'ID de courriel. </p> <p>L'ID de message est utilisé pour les campagnes de marketing/remarketing. L'ID de message est souvent appelé « Code de suivi ».  » » </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Recipient ID </p> </td> 
   <td colname="col3"> <p>Identifiez l'evar Adobe Analytics utilisée pour le suivi de l'ID du destinataire de courrier électronique. </p> <p>L'ID de destinataire est utilisé pour les campagnes marketing/remarketing. L'ID de message est souvent appelé « Code du visiteur ».  » » </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Case à cocher d'acceptation </p> </td> 
   <td colname="col3"> <p>Examinez les informations affichées à côté de la case à cocher Accepter : </p> <p><i>Je comprends qu'en activant le suivi « ID de destinataire », cette fonction peut suivre les informations personnelles des visiteurs de notre site. This has privacy implications requiring the implementation of appropriate procedures by my organization, such as providing notice to, and consent of, our site visitors. </i> </p> <p>If you agree to the acceptance statement, select the check box, then click <b>Next</b> to proceed to Step 4 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>Segments au niveau de la suite de rapports définis par le client </p> </td> 
   <td colname="col3"> <p>Cette intégration crée les segments définis par le partenaire affichés sur le côté gauche de la page Segments d'intégration de l'Assistant d'intégration. </p> <p>De plus, vous pouvez sélectionner des segments au niveau de la suite de rapports existants à inclure dans l'intégration. </p> <p>Select the desired segments on the right side of the page, then click <b>Next</b> to proceed to Step 5 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Cliqué </p> </td> 
   <td colname="col3"> <p>Spécifiez l'événement Adobe Analytics qui stocke les données avec clic sur les données importées depuis le système de courrier électronique. </p> <p>L'événement Clicked vous permet de voir le nombre de visiteurs qui ont cliqué sur le courriel. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Ouvert </p> </td> 
   <td colname="col3"> <p>Spécifiez l'événement Adobe Analytics qui stocke les données ouvertes par courrier électronique importées à partir du système de courrier électronique. </p> <p>L'événement Ouvert vous permet de voir le nombre de visiteurs qui ont ouvert le courriel. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Envoyé </p> </td> 
   <td colname="col3"> <p>Spécifiez l'événement Adobe Analytics qui stocke les données envoyées par courrier électronique importées à partir du système de courrier électronique. </p> <p>L'événement Clicked vous permet de voir le nombre de courriers électroniques envoyés. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Nombre total de rebonds </p> </td> 
   <td colname="col3"> <p>Spécifiez l'événement Adobe Analytics qui stocke le nombre total de données par courriel importées à partir du système de courrier électronique. </p> <p>L'événement Total-retours vous permet de voir le nombre de messages électroniques qui n'ont pas été remis aux destinataires en raison d'un problème de remise. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Désabonné </p> </td> 
   <td colname="col3"> <p>Spécifiez l'événement Adobe Analytics qui stocke les données de désabonnement envoyées à partir du système de courrier électronique. </p> <p>L'événement Non abonné vous permet de voir le nombre de visiteurs qui ont ouvert le courriel mais, d'autre part, cliquent sur le lien Désabonner pour exclure les futurs courriers électroniques de votre organisation. </p> <p>Cliquez sur Suivant pour passer à l'étape 6 de l'Assistant. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>Collecte de données : Module JavaScript </p> </td> 
   <td colname="col3"> <p>Select <b>JavaScript Plug-in</b> if you want to use the plug-in as the collection model for this integration, then click <b>Next</b> to proceed to Step 7 of the Wizard. </p> <p> <p>Remarque : La solution automatisée est la sélection par défaut. </p> </p> <p>Contactez votre consultant Adobe pour obtenir une copie du module JavaScript utilisé pour cette intégration. You can also copy and paste the plug-in contained in <a href="datran-plug-in-code.md#concept_28E7C834A6804A949AA9306F8896B36E" type="concept" format="dita" scope="local"> Analytics Plug-In Code</a>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>Collecte de données : Solution automatisée </p> </td> 
   <td colname="col3"> <p>Select <b>Automated Solution</b> if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. </p> <p> <p>Remarque : La solution automatisée est la sélection par défaut. </p> </p> <p>Si vous sélectionnez cette option, spécifiez les identifiants uniques utilisés pour cette intégration : </p> <p><b>Paramètre de chaîne de requête d'ID de message :</b>Cette valeur représente l'ID de message annexé à l'URL de la page d'entrée par votre partenaire de courrier électronique. </p> <p><b>Paramètre de chaîne de requête d'ID du destinataire :</b> Cette valeur représente l'ID de destinataire annexé à l'URL de la page d'entrée par votre partenaire de messagerie. </p> <p>Click <b>Next</b> to proceed to Step 7 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>Résumé de l'intégration </p> </td> 
   <td colname="col3"> <p>Verify the integration parameters by clicking the plus sign (+) next to each category, then click <b>Save</b> to proceed to Step 8 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p>Intégration terminée </p> </td> 
   <td colname="col3"> <p>Click <b>Finish</b> to complete the integration. </p> <p><b>IMPORTANT :</b> Adobe Analytics n'enregistre pas les paramètres d'intégration tant que vous n'avez pas cliqué <b>sur Terminer</b>. </p> </td> 
  </tr> 
 </tbody> 
</table>

