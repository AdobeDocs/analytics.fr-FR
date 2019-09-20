---
description: L’assistant d’intégration des connecteurs de données vous guide tout au long du processus d’intégration des connecteurs de données.
seo-description: L’assistant d’intégration des connecteurs de données vous guide tout au long du processus d’intégration des connecteurs de données.
seo-title: Intégration de Silverpop
title: Intégration de Silverpop
uuid: dc5e6a09-3238-412d-9980-4a105ce14819
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Intégration de Silverpop{#silverpop-integration}

L’assistant d’intégration des connecteurs de données vous guide tout au long du processus d’intégration des connecteurs de données.

Pour configurer l’intégration :

1. Dans Adobe Experience Cloud, sélectionnez Connecteurs de données™ dans la liste déroulante des produits.
1. Cliquez sur **[!UICONTROL Ajouter nouveau]** et sélectionnez **[!UICONTROL Par nom]** dans la liste déroulante **[!UICONTROL Afficher]** .
1. Recherchez l’icône **Silverpop Engage 2.0** et faites-la glisser vers un emplacement de module externe vide dans votre suite de rapports Analytics pour lancer l’Assistant d’intégration des connecteurs de données.
1. Dans la page d’introduction à l’intégration Silverpop, passez en revue le texte, puis cochez la case pour accepter les frais associés à l’intégration.
1. Sélectionnez la Report Suite à utiliser pour cette intégration.
1. Attribuez un nom convivial pour identifier cette intégration, puis cliquez sur **[!UICONTROL Créer et configurer cette intégration]**.

   Cette page présente un aperçu de l’intégration, ainsi que des liens utiles conduisant vers davantage d’informations. Cette intégration entraîne des frais pour Adobe et Silverpop. Contactez votre représentant commercial au sujet des deux organisations et veillez à comprendre la structure des frais.
1. Sur chaque page de l’assistant d’intégration des connecteurs de données, fournissez les informations requises, comme décrit dans le tableau suivant :

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col2" class="entry"> <p> <b>Champ</b> </p> </th> 
   <th colname="col03" valign="top" align="left" class="entry"> <p> <b>Section de configuration</b> </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Description</b> </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col2" valign="top" align="left"> <p>Nom d’intégration </p> </td> 
   <td colname="col03"> <p>(1) Paramètres d’intégration </p> </td> 
   <td colname="col3"> <p>Spécifiez le nom d’intégration que les Connecteurs de données affichent dans la liste d’intégration active de la suite de rapports. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2" valign="top" align="left"> <p>Télécharger le fichier </p> </td> 
   <td colname="col03"> <p>(2) Correspondances de variables </p> </td> 
   <td colname="col3"> <p> Utilisation avec le remarketing de téléchargement de fichiers. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> Email Address </p> </td> 
   <td colname="col03"> <p>(2) Correspondances de variables </p> </td> 
   <td colname="col3"> <p>Utilisé pour le remarketing vers les visiteurs sans ID Silverpop connu. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>ID de compte </p> </td> 
   <td colname="col03"> <p>(2) Correspondances de variables </p> </td> 
   <td colname="col3"> <p>Indiquez votre ID de compte Silverpop (l'identifiant unique attribué à votre organisation par Silverpop), puis cliquez sur <b>Suivant</b> pour passer à l'étape 3 de l'Assistant. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Nom du formulaire </p> </td> 
   <td colname="col03"> <p>(2) Correspondances de variables </p> </td> 
   <td colname="col3"> <p>Utilisation avec le remarketing d’abandon de formulaire. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>ID de courrier </p> </td> 
   <td colname="col03"> <p>(2) Correspondances de variables </p> </td> 
   <td colname="col3"> <p>(Obligatoire) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Silverpop ID </p> </td> 
   <td colname="col03"> <p>(2) Correspondances de variables </p> </td> 
   <td colname="col3"> <p>(Obligatoire) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> Retours </p> </td> 
   <td colname="col03"> <p>(2) Correspondances de variables </p> </td> 
   <td colname="col3"> <p>(Obligatoire) Spécifiez l’événement Analytics qui stocke les données de rebonds totaux du courrier électronique importées du système de messagerie. </p> <p>L’événement Total-Rebonds vous permet de voir le nombre de messages électroniques qui n’ont pas été remis aux destinataires en raison d’un problème de remise. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Cliqué </p> </td> 
   <td colname="col03"> <p>(2) Correspondances de variables </p> </td> 
   <td colname="col3"> <p>(Obligatoire) Spécifiez l’événement Analytics qui stocke les données de clic par courrier électronique importées du système de messagerie. </p> <p>L’événement Cliqué vous permet d’afficher le nombre de visiteurs qui ont cliqué sur le message électronique. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> Fichier téléchargé </td> 
   <td colname="col03"> <p>(2) Correspondances de variables </p> </td> 
   <td colname="col3"> <p> Utilisation avec le remarketing de téléchargement de fichiers. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> Formulaire complété </td> 
   <td colname="col03"> <p>(2) Correspondances de variables </p> </td> 
   <td colname="col3"> <p>Utilisation avec le remarketing d’abandon de formulaire. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> Formulaire commencé </td> 
   <td colname="col03"> <p>(2) Correspondances de variables </p> </td> 
   <td colname="col3"> <p>Utilisation avec le remarketing d’abandon de formulaire. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Ouvert </p> </td> 
   <td colname="col03"> <p>(2) Correspondances de variables </p> </td> 
   <td colname="col3"> <p>(Obligatoire) Spécifiez l’événement Analytics qui stocke les données de courrier électronique ouvertes importées du système de messagerie électronique. </p> <p>L’événement Ouvert vous permet de voir le nombre de visiteurs qui ont ouvert le message électronique. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Envoyé </p> </td> 
   <td colname="col03"> <p>(2) Correspondances de variables </p> </td> 
   <td colname="col3"> <p>(Obligatoire) Spécifiez l’événement Analytics qui stocke les données envoyées par courrier électronique importées du système de messagerie. </p> <p>L’événement Envoyé vous permet de voir le nombre de messages électroniques envoyés. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Non abonné </p> </td> 
   <td colname="col03"> <p>(2) Correspondances de variables </p> </td> 
   <td colname="col3"> <p>(Obligatoire) Spécifiez l’événement Analytics qui stocke les données de désabonnement par courrier électronique importées du système de messagerie. </p> <p>L’événement Désabonné vous permet de voir le nombre de visiteurs qui ont ouvert le message électronique, puis cliqué sur le lien Désabonner pour exclure les futurs messages électroniques de votre organisation. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Segments </p> </td> 
   <td colname="col03"> <p>(3) Paramètres des données </p> </td> 
   <td colname="col3"> <p>Cette intégration crée les segments définis par les partenaires affichés dans la section Segments de partenaire. </p> <p>De plus, vous pouvez sélectionner des segments existants au niveau de la suite de rapports à inclure dans l’intégration. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> Demandes d’accès </p> </td> 
   <td colname="col03"> <p>(3) Paramètres des données </p> </td> 
   <td colname="col3"> <p> (Obligatoire) Activez <span class="uicontrol"> cette intégration pour télécharger les données</span>du produit. </p> <p>Facultatif : Permet à cette intégration de télécharger les recettes, les commandes et les unités. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Collecte de données </p> </td> 
   <td colname="col03"> <p>(3) Paramètres des données </p> </td> 
   <td colname="col3"> <p>Sélectionnez Module externe <b>JavaScript</b> si vous souhaitez utiliser le module externe s_code.js comme modèle de collecte pour cette intégration (voir Code <a href="../silverpop-overview/silverpop-analytics-code.md#concept-28e7c834a6804a949aa9306f8896b36e" format="dita" scope="local"> du module externe</a>Analytics). </p> <p>Sélectionnez Solution <b></b> automatisée si vous souhaitez utiliser un modèle de collecte automatisée pour cette intégration, puis spécifiez les identifiants uniques utilisés pour cette intégration. </p> <p>Si vous sélectionnez cette option, spécifiez les identifiants uniques utilisés pour cette intégration : </p> <p> <b>Paramètre de chaîne de requête d’ID de message :</b>cette valeur représente l’ID de message annexé à l’URL de la page d’entrée par votre partenaire de messagerie. </p> <p> <b></b> Paramètre de chaîne de requête d’ID de destinataire : Cette valeur représente l’ID du destinataire annexé à l’URL de la page d’entrée par votre partenaire de messagerie. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Génération de tableaux de bord et de signets </p> </td> 
   <td colname="col03"> <p>(4) Paramètres de rapport </p> </td> 
   <td colname="col3"> <p>Générer automatiquement un tableau de bord et des signets pour l’intégration. </p> </td> 
  </tr> 
 </tbody> 
</table>

