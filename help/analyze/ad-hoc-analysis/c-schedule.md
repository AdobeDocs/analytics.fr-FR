---
description: Vous pouvez personnaliser la planification des  du pour les rapports. Vous pouvez arrêter le à un certain moment ou spécifier le nombre de fois où vous souhaitez envoyer un rapport. Les nouveaux calendriers utilisent la plage de dates définie dans le rapport. Par exemple, si vous créez un rapport pour les 90 derniers jours et planifiez son exécution quotidienne, vous recevrez un rapport pour les 90 derniers jours chaque jour. Si vous créez un rapport avec une plage de dates statique à partir du calendrier, vous verrez le même rapport chaque fois qu'il est envoyé.
title: Gestionnaire de planification
topic: Ad hoc analysis
uuid: 82a054ef-109d-414d-a6e1-e09ee57c163f
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Gestionnaire de planification

Vous pouvez personnaliser la planification des  du pour les rapports. Vous pouvez arrêter le à un certain moment ou spécifier le nombre de fois où vous souhaitez envoyer un rapport. Les nouveaux calendriers utilisent la plage de dates définie dans le rapport. Par exemple, si vous créez un rapport pour les 90 derniers jours et planifiez son exécution quotidienne, vous recevrez un rapport pour les 90 derniers jours chaque jour. Si vous créez un rapport avec une plage de dates statique à partir du calendrier, vous verrez le même rapport chaque fois qu&#39;il est envoyé.

## Gestionnaire de planification {#concept_A1CDE14B72A54DD6AE17B816092CAB8B}

Vous pouvez personnaliser la planification des  du pour les rapports. Vous pouvez arrêter le à un certain moment ou spécifier le nombre de fois où vous souhaitez envoyer un rapport. Les nouveaux calendriers utilisent la plage de dates définie dans le rapport. Par exemple, si vous créez un rapport pour les 90 derniers jours et planifiez son exécution quotidienne, vous recevrez un rapport pour les 90 derniers jours chaque jour. Si vous créez un rapport avec une plage de dates statique à partir du calendrier, vous verrez le même rapport chaque fois qu&#39;il est envoyé.

>[!NOTE] Lorsqu’un compte utilisateur est désactivé, toutes les distributions de rapport planifiées créées par l’utilisateur sont suspendues.

To ensure that line items in a breakdown are persistent in saved and scheduled reports, use the **[!UICONTROL Edit Items]** feature in the [Table Builder](/help/analyze/ad-hoc-analysis/c-tablebuilder.md) to create fixed dimension lists in breakdowns.

>[!IMPORTANT]
>
>Ad Hoc Analysis permet de définir et de planifier rapidement des rapports pour répondre aux besoins spécifiques et ponctuels en matière de rapports ad hoc. Il n’est pas conçu pour les exportations complètes de données avec un nombre important de lignes, de colonnes, d’évaluations de mesures ou de ventilations étendues à l’aide d’extractions de données.
>
>Les contraintes pratiques pour les  planifiées dans les  de ad hoc sont basées sur ce principe : Si votre rapport n’est pas généré dans les dix minutes (délai d’expiration pour les  ad hoc ), il est probable que votre rapport soit trop complexe.
>
>Il est probable que votre rapport comporte trop de mesures, trop de ventilations d’éléments de dimension, trop de lignes ou de colonnes, ou d’autres extrêmes, ce qui en fait un processus de génération de rapports trop long pour les   ad hoc. Ce type de rapport doit être exécuté dans l’entrepôt de données, une fonctionnalité d’Adobe Analytics conçue pour les données complètes  le  s’exécutant hors connexion avec la génération de rapports qui peut prendre plusieurs heures ou jours.
>
>Par exemple, les ad hoc  peuvent gérer 50 000 lignes de données, mais la ventilation de ces données pour dix types de navigateur signifie 50 000 fois 10, soit une augmentation exponentielle qui peut être trop complexe pour un outil de ad hoc. Les ventilations supplémentaires augmentent à nouveau les lignes de données de manière exponentielle. La définition du nombre réel de lignes, de colonnes et de ventilations à contraindre pour les ad hoc   le ne peut pas être définie en termes nets, mais est une combinaison de tous ces facteurs.

## Planification de la distribution d’un rapport {#task_7A3165C8C5C349718FE3B2B0C727ACFD}

Cette procédure explique comment planifier la distribution d’un rapport.

<!-- 

t_schedule_delivery.xml

 -->

1. Cliquez sur **[!UICONTROL Tools]**, puis sur **[!UICONTROL Schedule Manager]**.
1. Sur la [!UICONTROL Schedule Manager]page, cliquez sur **[!UICONTROL New.]**

## Options de distribution - Définitions {#reference_CA49AC560258471AAE959BCA243F170C}

Définitions des paramètres des options de .

<!-- 

r_delivery_options.xml

 -->

Vous pouvez envoyer vos informations, telles qu’elles s’affichent dans le rapport actuellement sélectionné, au format que vous sélectionnez. Vous pouvez l’envoyer une seule fois ou configurer un calendrier de  et spécifier le format de fichier de votre choix. Vous pouvez créer et envoyer une signature numérique pour assurer le destinataire du fichier qu’il est authentique. Vous pouvez envoyer le fichier à une adresse électronique ou le transférer vers un serveur FTP.

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Champ </p> </th> 
   <th colname="col2" class="entry"> <p>Définition </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nom </p> </td> 
   <td colname="col2"> <p> Nom configurable de ce rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> <p>Indique l’identifiant du rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Format du fichier </p> </td> 
   <td colname="col2"> 
    <ul id="ul_711C2D9B216C48359F7B42521D927872"> 
     <li id="li_36E8DEFDA1B84890A4204A6DFF4E0267">Excel : Génère votre rapport dans une feuille de calcul, y compris toutes les images. Modifiable dans Microsoft Excel. </li> 
     <li id="li_C918FA3AE8194BD2B59E554DAC7CBBE2">CSV : Génère votre rapport dans des valeurs séparées par des virgules. Modifiable dans un éditeur de texte simple (tel que le Bloc-notes) ou un éditeur de feuille de calcul (tel qu’Excel). Ne contient aucune image. </li> 
     <li id="li_B7C8C098C5264B349C21077A0DEFE059">PDF : Génère votre rapport au format  Portable. Non modifiable et affichable dans Adobe Acrobat ou Adobe Reader. </li> 
     <li id="li_B1183DB25DE34B689FBD0E5B44691F49">HTML : Génère votre rapport dans une pièce jointe du langage d’annotation hypertexte. Ce format est celui de la plupart des sites Web. Non modifiable sauf si vous êtes familiarisé avec le code HTML. </li> 
     <li id="li_5ED5F1862AB1490A9FF5695FF9F52C5E">Word : Génère votre rapport au format Rich Text, y compris toutes les images. Modifiable dans Microsoft Word ou WordPad. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Avancés </p> </td> 
   <td colname="col2"> <p> Voir <a href="/help/analyze/ad-hoc-analysis/c-schedule.md"   >Paramètres de format avancé</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Destination du fichier </p> </td> 
   <td colname="col2"> <p>Courriel : Paramètres à envoyer par courrier électronique. </p> <p>FTP : Paramètres de téléchargement sur un serveur FTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Plage de rapports et planification des  de </p> </td> 
   <td colname="col2"> <p>Indique le moment de remise du rapport. Les nouveaux calendriers utilisent la plage de dates définie dans le rapport. Par exemple, si vous créez un rapport pour les 90 derniers jours et planifiez son exécution quotidienne, vous recevrez un rapport pour les 90 derniers jours chaque jour. Si vous créez un rapport avec une plage de dates statique à partir du calendrier, vous verrez le même rapport chaque fois qu'il est envoyé. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Paramètres de format avancé - Définitions {#reference_F99B65BF7C9746638D8147EED147015B}

Définitions des paramètres dans Paramètres de format avancé.

<!-- 

r_advanced_format_settings_dsc.xml

 -->

<table id="table_CD0888E8390745F4B83DF6AC69CB0854"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Champ </p> </th> 
   <th colname="col2" class="entry"> <p>Définition </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nom de fichier </p> </td> 
   <td colname="col2"> <p>Nom de fichier défini par l’utilisateur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ajouter un ID au nom de fichier </p> </td> 
   <td colname="col2"> <p>Ajoute automatiquement l’identifiant du rapport au nom de fichier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Ajouter la date au nom de fichier </p> </td> 
   <td colname="col2"> <p> Ajoute automatiquement la date du rapport au nom de fichier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Langue </p> </td> 
   <td colname="col2"> <p> Permet de sélectionner une langue pour le rapport. Vous pouvez envoyer le rapport dans l’une des langues suivantes, quelle que soit la langue utilisée. </p> 
    <ul id="ul_BD3D331B0D6146F79A6D254136E43920"> 
     <li id="li_0EE6A371B1BB4627BD3F64BD0EF07E44">Anglais </li> 
     <li id="li_5EF76261928543FDB36D99E4C89DE994">Espagnol </li> 
     <li id="li_FABF47E8CD64486BA1567E02460422C5">Chinois simplifié </li> 
     <li id="li_8A6BC2DE92DB47DA9397B8931D8DCC6E">Chinois traditionnel </li> 
     <li id="li_EDA24D700BE040E8B839B82E31DABC28">Français </li> 
     <li id="li_A8D41DCCC91542BB8D0A522EC99575E8">Allemand </li> 
     <li id="li_E9F73C93C94A46B78BCE85A7261CEDD4">Japonais </li> 
     <li id="li_699B97050AA54D818659C191F4594E4E">Portugais </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Codage  </p> </td> 
   <td colname="col2"> <p>Spécifie un type de codage. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Envoyer le rapport sous forme de fichier comprimé </p> </td> 
   <td colname="col2"> <p> Compresse le fichier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Envoyer le fichier de signature numérique </p> </td> 
   <td colname="col2"> <p>Crée une signature numérique à envoyer avec le courrier électronique. </p> </td> 
  </tr> 
 </tbody> 
</table>

