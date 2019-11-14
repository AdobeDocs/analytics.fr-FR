---
description: L’assistant d’intégration des connecteurs de données vous guide tout au long du processus d’intégration des connecteurs de données.
title: Exécution de l’assistant d’intégration des connecteurs de données
uuid: 714417f7-c1df-4e61-a07f-d319f6581c9c
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Exécution de l’assistant d’intégration des connecteurs de données{#running-the-data-connectors-integration-wizard}

L’assistant d’intégration des connecteurs de données vous guide tout au long du processus d’intégration des connecteurs de données.

Pour configurer l’intégration :

1. Connectez-vous à Experience Cloud.
1. Sur la page d’accueil d’Adobe Analytics, cliquez sur l’icône Connecteurs de données™ sur la molette ou la barre d’outils.
1. Sur la page Connecteurs de données, sélectionnez la suite de rapports dans laquelle vous souhaitez configurer l’intégration.

   >[!NOTE]
   >
   >Veillez à sélectionner la suite de rapports de votre choix dans la liste déroulante Suite **de** rapports située dans le coin supérieur gauche de la page Connecteurs de données.

1. Cliquez sur l’onglet **alphabétique** en haut de la liste **des** partenaires sur le côté gauche de l’interface utilisateur des connecteurs de données, puis localisez l’icône **Datran** .
1. Faites glisser l’icône **Datran** vers un emplacement de module externe vide dans votre suite de rapports Adobe Analytics pour lancer l’Assistant d’intégration des connecteurs de données.

1. Dans la page d’introduction de l’intégration de Datran, passez en revue le texte, cochez la case pour accepter les frais associés à l’intégration, puis cliquez sur **Suivant**.

   Cette page présente un aperçu de l’intégration, ainsi que des liens utiles conduisant vers davantage d’informations. Cette intégration entraîne des frais Adobe et Datran. Contactez votre représentant commercial au sujet des deux organisations et veillez à comprendre la structure des frais.
1. Sur chaque page de l’assistant d’intégration des connecteurs de données, fournissez les informations requises, comme décrit dans le tableau suivant :

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" valign="top" align="left" class="entry"> <p><b>PAGE D’ASSISTANT N°</b> </p> </th> 
   <th colname="col2" class="entry"> <p><b>CHAMP</b> </p> </th> 
   <th colname="col3" class="entry"> <p><b>DESCRIPTION</b> </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2" valign="top" align="left"> <p>Nom d’intégration </p> </td> 
   <td colname="col3"> <p>Spécifiez le nom d’intégration que les Connecteurs de données affichent dans la liste d’intégration active de la suite de rapports. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>Adresse de courriel d’intégration </p> </td> 
   <td colname="col3"> <p>Spécifiez l’adresse électronique qui reçoit toutes les notifications liées à cette intégration, puis cliquez sur <b>Suivant</b> pour passer à l’étape 2 de l’Assistant. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>ID de compte </p> </td> 
   <td colname="col3"> <p>Indiquez votre ID de compte de date (l’identifiant unique attribué à votre organisation par Datran), puis cliquez sur <b>Suivant</b> pour passer à l’étape 3 de l’Assistant. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>ID du message </p> </td> 
   <td colname="col3"> <p>Identifiez l’eVar Adobe Analytics utilisée pour le suivi de l’ID de message électronique. </p> <p>L’ID de message est utilisé pour les campagnes marketing/remarketing. L’ID de message est souvent appelé "Code de suivi". </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Recipient ID </p> </td> 
   <td colname="col3"> <p>Identifiez l’eVar Adobe Analytics utilisée pour le suivi de l’ID de destinataire du courrier électronique. </p> <p>L’ID de destinataire est utilisé pour les campagnes marketing/remarketing. L’ID de message est souvent appelé "Code visiteur". </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Case à cocher Acceptation </p> </td> 
   <td colname="col3"> <p>Vérifiez les informations affichées en regard de la case à cocher Acceptation : </p> <p><i>Je comprends qu’en activant le suivi "ID du destinataire", cette fonctionnalité peut suivre les informations d’identification personnelle des visiteurs de notre site. Cela a des répercussions sur la vie privée qui exigent la mise en oeuvre de procédures appropriées par mon organisation, comme la notification et le consentement des visiteurs de notre site. </i> </p> <p>Si vous acceptez la déclaration d’acceptation, cochez la case, puis cliquez sur <b>Suivant</b> pour passer à l’étape 4 de l’Assistant. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>Segments définis par le client au niveau de la suite de rapports </p> </td> 
   <td colname="col3"> <p>Cette intégration crée les segments définis par les partenaires affichés sur le côté gauche de la page Segments d’intégration de l’assistant d’intégration. </p> <p>De plus, vous pouvez sélectionner des segments existants au niveau de la suite de rapports à inclure dans l’intégration. </p> <p>Sélectionnez les segments de votre choix sur le côté droit de la page, puis cliquez sur <b>Suivant</b> pour passer à l’étape 5 de l’Assistant. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Cliqué </p> </td> 
   <td colname="col3"> <p>Spécifiez l’événement Adobe Analytics qui stocke les données de clic par courrier électronique importées du système de messagerie. </p> <p>L’événement Cliqué vous permet d’afficher le nombre de visiteurs qui ont cliqué sur le message électronique. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Ouvert </p> </td> 
   <td colname="col3"> <p>Spécifiez l’événement Adobe Analytics qui stocke les données de courrier électronique ouvertes importées à partir du système de courrier électronique. </p> <p>L’événement Ouvert vous permet de voir le nombre de visiteurs qui ont ouvert le message électronique. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Envoyé </p> </td> 
   <td colname="col3"> <p>Spécifiez l’événement Adobe Analytics qui stocke les données d’envoi de courrier électronique importées du système de messagerie. </p> <p>L’événement Cliqué vous permet de voir le nombre de messages électroniques envoyés. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Rebonds totaux </p> </td> 
   <td colname="col3"> <p>Spécifiez l’événement Adobe Analytics qui stocke les données de rebonds totaux du courrier électronique importées du système de messagerie. </p> <p>L’événement Total-Rebonds vous permet de voir le nombre de messages électroniques qui n’ont pas été remis aux destinataires en raison d’un problème de remise. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Non abonné </p> </td> 
   <td colname="col3"> <p>Spécifiez l’événement Adobe Analytics qui stocke les données de désabonnement par courrier électronique importées du système de messagerie. </p> <p>L’événement Désabonné vous permet de voir le nombre de visiteurs qui ont ouvert le message électronique, puis cliqué sur le lien Désabonner pour exclure les futurs messages électroniques de votre organisation. </p> <p>Cliquez sur Suivant pour passer à l’étape 6 de l’Assistant. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>Collecte de données : Module externe JavaScript </p> </td> 
   <td colname="col3"> <p>Sélectionnez Module externe <b>JavaScript</b> si vous souhaitez utiliser le module externe comme modèle de collecte pour cette intégration, puis cliquez sur <b>Suivant</b> pour passer à l’étape 7 de l’Assistant. </p> <p> <p>Remarque :  La solution automatisée est la sélection par défaut. </p> </p> <p>Contactez votre consultant Adobe pour obtenir une copie du module externe JavaScript utilisé pour cette intégration. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>Collecte de données : Solution automatisée </p> </td> 
   <td colname="col3"> <p>Sélectionnez Solution <b></b> automatisée si vous souhaitez utiliser un modèle de collecte automatisée pour cette intégration, puis spécifiez les identifiants uniques utilisés pour cette intégration. </p> <p> <p>Remarque :  La solution automatisée est la sélection par défaut. </p> </p> <p>Si vous sélectionnez cette option, spécifiez les identifiants uniques utilisés pour cette intégration : </p> <p><b>Paramètre de chaîne de requête d’ID de message :</b>cette valeur représente l’ID de message annexé à l’URL de la page d’entrée par votre partenaire de messagerie. </p> <p><b></b> Paramètre de chaîne de requête d’ID de destinataire : Cette valeur représente l’ID du destinataire annexé à l’URL de la page d’entrée par votre partenaire de messagerie. </p> <p>Cliquez sur <b>Suivant</b> pour passer à l’étape 7 de l’Assistant. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>Résumé de l’intégration </p> </td> 
   <td colname="col3"> <p>Vérifiez les paramètres d’intégration en cliquant sur le signe plus (+) en regard de chaque catégorie, puis cliquez sur <b>Enregistrer</b> pour passer à l’étape 8 de l’Assistant. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p>Intégration terminée </p> </td> 
   <td colname="col3"> <p>Cliquez sur <b>Terminer</b> pour terminer l’intégration. </p> <p><b></b> IMPORTANT : Adobe Analytics n’enregistre pas les paramètres d’intégration tant que vous n’avez pas cliqué sur <b>Terminer</b>. </p> </td> 
  </tr> 
 </tbody> 
</table>
