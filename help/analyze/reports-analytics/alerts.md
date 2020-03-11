---
description: valeur nulle
subtopic: Alerts
title: Alertes
topic: Reports and analytics
uuid: e1333a9b-eba0-45b7-b7e6-46e06190db64
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Alertes

## Alertes {#concept_8AB25AF6FB52478DB98C1BA4577A2E16}

Grâce aux alertes intelligentes du nouveau système d’alerte d’Adobe Analytics, vous pouvez créer et gérer des alertes, les prévisualiser et gérer les contributions. Vous pouvez

* Créer des alertes en fonction des anomalies (seuils de 90 %, 95 % ou 99 % ; % de changement ; au-dessus/au-dessous).
* Prévisualiser le nombre de fois où une alerte sera déclenchée.
* Envoyer des alertes par e-mail ou par SMS, avec des liens pour générer automatiquement les projets Analysis Workspace.
* Créer des alertes « empilées » qui présentent plusieurs mesures dans une seule alerte.

Pour accéder à ce nouveau système d’alertes, cliquez sur **[!UICONTROL Plus]** > **[!UICONTROL Alertes]** dans n’importe quel rapport de Reports &amp; Analytics.

Pour en savoir plus, consultez la documentation d’Analysis Workspace à propos des [alertes intelligentes](https://marketing.adobe.com/resources/help/fr_FR/analytics/analysis-workspace/intellligent_alerts.html).

## Ajout d’une alerte {#task_51187E8BF19544DDA9EF2057E6F11D35}

Cette procédure décrit comment ajouter une alerte dans Adobe Analytics.

<!-- 

t_add_an_alert.xml

 -->

Accédez au nouveau Générateur d’alertes dans le menu **[!UICONTROL Analytics]** > **[!UICONTROL Composants]**. Vous pouvez aussi y accéder depuis des rapports dans Reports &amp; Analytics :

1. Dans Reports &amp; Analytics, ouvrez le rapport dans lequel définir une alerte.
1. Cliquez sur **[!UICONTROL Plus]** > **[!UICONTROL Ajouter une alerte]**.
1. Le [nouveau Générateur d’alertes](https://marketing.adobe.com/resources/help/fr_FR/analytics/analysis-workspace/alert-builder.html) s’ouvre.

## Affichage ou modification des alertes existantes {#task_2ADF2A05EB784B8BBAFE293AC8243C46}

Contexte de la tâche

1. Sélectionnez **[!UICONTROL Analytics]** > **[!UICONTROL Composants]** > **[!UICONTROL Alertes]**. Le nouveau [Gestionnaire d’alertes](https://marketing.adobe.com/resources/help/fr_FR/analytics/analysis-workspace/alert-manager.html) s’ouvre.

## Migration des alertes héritées {#concept_7E8179F5EF6E4913B0CE5CF4FF186911}

Certaines des fonctions d’alertes actuelles d’Analytics ne seront pas incluses dans le nouveau Gestionnaire d’alertes, qui sera publié à l’automne 2016 (dans le cadre d’Analysis Workspace). Le tableau suivant répertorie les fonctions d’alerte obsolètes ainsi que certaines fonctions d’alerte qui seront migrées sous une autre forme dans le nouveau Gestionnaire d’alertes.

<!-- 

deprecated_alerts.xml

 -->

<table id="table_9307013B16AC4AC7BFC6F4C440FCFDE4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fonction d’alertes héritée </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Obsolète ou migrée ? </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Totaux (tous les éléments) </p> </td> 
   <td colname="col2"> <p>Permet de créer des alertes pour tous les éléments d’un rapport de dimension. </p> </td> 
   <td colname="col3"> <p>Il arrive que le résultat soit le même, que vous créiez une alerte pour tous les éléments d’un rapport de dimension ou que vous configuriez l’alerte pour la mesure agrégée seulement (non appliquée à une dimension). Par exemple, supposons que vous créiez une alerte mensuelle Tous les éléments pour la mesure Recettes. Vous obtiendrez le même résultat si vous exécutez le rapport Recettes et configurez une alerte mensuelle pour ce rapport. </p> <p>Dans ce cas, l’alerte héritée Totaux (tous les éléments) ne sera plus disponible et sera migrée vers la version plus récente et plus simple. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>1 000 principaux éléments </p> <p> </p> </td> 
   <td colname="col2"> <p>Permet de créer des alertes pour les 1 000 premiers éléments d’un rapport. </p> </td> 
   <td colname="col3"> <p>N’est plus disponible dans le nouveau Gestionnaire d’alertes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Alertes Visiteurs uniques en fonction du temps Visiteurs uniques) </p> <p> </p> </td> 
   <td colname="col2"> <p>Permet de créer des rapports sur les visiteurs uniques par heure, par jour, par semaine et par mois. </p> </td> 
   <td colname="col3"> <p>Dans le nouveau Gestionnaire d’alertes, certaines alertes Visiteurs uniques en fonction du temps ne sont plus prises en charge. Par exemple, lorsque auparavant vous configuriez une alerte hebdomadaire pour les visiteurs uniques par jour, vous pouvez à partir de maintenant configurer une alerte quotidienne, hebdomadaire, etc. pour la mesure Visiteurs uniques. (Analysis Workspace prend en charge une mesure Visiteurs uniques, mais pas les mesures Visiteurs uniques par jour/semaine/mois/etc.). </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Recherche </p> </td> 
   <td colname="col2"> <p>Permet de créer des alertes pour un rapport de dimension sur lequel une recherche est appliquée. S’applique seulement aux Totaux (Tous les éléments) ou aux 1 000 premiers éléments. </p> <p> </p> </td> 
   <td colname="col3"> <p>N’est plus disponible dans le nouveau Gestionnaire d’alertes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Rapports spécifiques à Reports &amp; Analytics </p> </td> 
   <td colname="col2"> <p>Permet de créer des alertes pour plusieurs rapports qui existent dans Reports &amp; Analytics, mais ne correspondent pas à un rapport Analysis Workspace, tel que : 
     <ul id="ul_9A690970A5AE4ED39E664DF23EF3164F"> 
      <li id="li_E2F44EDBA1D945CEBAC4802ED714E7A1">JavaScript </li> 
      <li id="li_B847C6A988854F76824F099681705EC9">Longueur de chemin </li> 
      <li id="li_4AF656460BC748E8802FAF258D01842F">Robots </li> 
      <li id="li_A300D2803B244774839BEC23D3EB533A">Fuseaux horaires </li> 
      <li id="li_7A0B4CF92F4D47238B7B329EEC213322">Domaines de haut niveau </li> 
     </ul> </p> <p> </p> </td> 
   <td colname="col3"> <p>N’est plus disponible dans le nouveau Gestionnaire d’alertes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Alertes avec un logement ASI comme la suite de rapports </p> </td> 
   <td colname="col2"> <p>Vous ne pouvez plus <a href="https://marketing.adobe.com/resources/help/fr_FR/reference/ASI_slots_admin.html"  >créer ni modifier de logements ASI</a> ; ils ne sont pas non plus disponibles dans Analysis Workspace. Ils ne sont donc pas pris en charge par les nouvelles alertes. </p> <p> </p> </td> 
   <td colname="col3"> <p>Indisponibles dans le nouveau Gestionnaire d’alertes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Alertes utilisant des mesures de participation </p> </td> 
   <td colname="col2"> <p>  Les <a href="https://marketing.adobe.com/resources/help/fr_FR/reference/metrics_participation.html"  >mesures de participation</a> sont disponibles dans Reports &amp; Analytics, mais ne sont actuellement pas disponibles dans le nouveau système d’alertes d’Analysis Workspace. </p> <p> </p> </td> 
   <td colname="col3"> <p>Indisponibles dans le nouveau Gestionnaire d’alertes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Alertes mensuelles pour les suites de rapports avec calendrier personnalisé </p> </td> 
   <td colname="col2"> <p>Seuls les clients qui ont configuré des alertes pour les suites de rapports dont les <a href="https://marketing.adobe.com/resources/help/fr_FR/arb/custom_calendar.html
"  >dates de début de mois sont personnalisées</a> (types NRF/National Retail Federation et Calendrier personnalisé) sont concernés. </p> <p>Les suites de rapports reposant sur un calendrier grégorien ou grégorien modifié ne sont pas concernées. Auparavant, ces alertes étaient envoyées le premier jour du mois grégorien (1er janvier, 1er février, etc.). Ceci ne fonctionnera plus avec la nouvelle fonction d’alertes de la détection des anomalies, qui prend en compte les données des mois précédents lors de la détection des anomalies. À l’avenir, nous comptons prendre en charge dans notre système de planification les calendriers personnalisés afin qu’il soit possible de planifier l’envoi des alertes et des projets planifiés le premier jour du mois du calendrier personnalisé, plutôt que simplement le premier jour du mois grégorien. </p> <p> </p> </td> 
   <td colname="col3"> <p>Indisponible pour l’instant dans le nouveau Gestionnaire d’alertes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Alertes qui n’ont pas été exécutées depuis septembre 2015 </p> </td> 
   <td colname="col2"> <p>Il peut y avoir plusieurs raisons pour lesquelles les alertes n’ont pas été exécutées depuis septembre 2015, notamment : </p> 
    <ul id="ul_15812938A2454537AF6ADDB039DE16BC"> 
     <li id="li_D079A819CEE04F609AF18C09EEE83F0D">Vous avez cliqué sur Désactiver sur l’alerte dans le Gestionnaire d’alertes. </li> 
     <li id="li_E23D01FA0B1341AD8BC1DDD16FB1366F">L’alerte s’exécute mais rencontre des erreurs. </li> 
    </ul> <p> </p> </td> 
   <td colname="col3"> Ces alertes ne seront pas migrées vers le nouveau système. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alertes marquées comme « désactivées » </td> 
   <td colname="col2"> Il n’est actuellement pas possible de désactiver/réactiver les alertes dans la nouvelle interface utilisateur, mais cette fonctionnalité devrait être ajoutée à l’avenir. <p> </p> </td> 
   <td colname="col3"> Ces alertes ne seront pas migrées vers le nouveau système. </td> 
  </tr> 
 </tbody> 
</table>

