---
description: Vous pouvez personnaliser la planification de la distribution des rapports. Il est possible d’interrompre la distribution après un certain temps ou de spécifier le nombre d’envois d’un rapport. Les nouveaux programmes utilisent la période définie dans le rapport. Par exemple, si vous créez un rapport pour les 90 derniers jours et planifiez une exécution quotidienne, vous recevrez, chaque jour, un rapport portant sur les 90 derniers jours. Si vous créez un rapport avec une période statique à partir du calendrier, le même rapport sera affiché lors de chaque envoi.
title: Gestionnaire de planification
topic: Ad hoc analysis
uuid: 82a054ef-109d-414d-a6e1-e09ee57c163f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Gestionnaire de planification

Vous pouvez personnaliser la planification de la distribution des rapports. Il est possible d’interrompre la distribution après un certain temps ou de spécifier le nombre d’envois d’un rapport. Les nouveaux programmes utilisent la période définie dans le rapport. Par exemple, si vous créez un rapport pour les 90 derniers jours et planifiez une exécution quotidienne, vous recevrez, chaque jour, un rapport portant sur les 90 derniers jours. Si vous créez un rapport avec une période statique à partir du calendrier, le même rapport sera affiché lors de chaque envoi.

## Gestionnaire de planification {#concept_A1CDE14B72A54DD6AE17B816092CAB8B}

Vous pouvez personnaliser la planification de la distribution des rapports. Il est possible d’interrompre la distribution après un certain temps ou de spécifier le nombre d’envois d’un rapport. Les nouveaux programmes utilisent la période définie dans le rapport. Par exemple, si vous créez un rapport pour les 90 derniers jours et planifiez une exécution quotidienne, vous recevrez, chaque jour, un rapport portant sur les 90 derniers jours. Si vous créez un rapport avec une période statique à partir du calendrier, le même rapport sera affiché lors de chaque envoi.

> [!NOTE] Lorsqu’un compte utilisateur est désactivé, toutes les livraisons de rapports planifiées créées par cet utilisateur sont suspendues.

Pour vous assurer que les éléments de ligne d’une ventilation sont persistants dans les rapports enregistrés et planifiés, utilisez la fonction **[!UICONTROL Modifier les éléments]** du Générateur [de](/help/analyze/ad-hoc-analysis/c-tablebuilder.md) tableau pour créer des listes de dimensions fixes dans les ventilations.

>[!IMPORTANT]
>
>Les analyses ad hoc vous permettent de définir et de planifier rapidement des rapports pour répondre à des besoins spécifiques, ponctuels et ponctuels en matière de création de rapports ad hoc. Elles ne sont pas destinées aux exportations complètes de données comprenant un très grand nombre de lignes, de colonnes, d’évaluations de mesure ou de ventilations complètes à l’aide d’extractions de données.
>
>Dans les Ad Hoc Analysis, les contraintes pratiques des rapports planifiés reposent sur ce principe : si le rapport n’est pas généré dans un délai de dix minutes (délai d’attente des Ad Hoc Analysis), cela signifie qu’il est probablement trop complexe.
>
>Il contient probablement trop de mesures, de ventilations d’élément de dimension, de lignes, de colonnes ou autres qui rendent le processus de génération trop long pour les Ad Hoc Analysis. Ce type de rapport doit être exécuté dans Data Warehouse, fonctionnalité d’Adobe Analytics conçue pour une extraction complète des données s’exécutant hors ligne et une génération de rapport pouvant prendre plusieurs heures, voire plusieurs jours.
>
>Par exemple, les Ad Hoc Analysis peuvent gérer 50 000 lignes de données, mais la ventilation de ces données pour 10 types de navigateurs (50 000 fois 10) entraîne une augmentation exponentielle du nombre de lignes, ce qui peut être trop complexe à gérer pour un outil de création de rapports ad hoc. Les ventilations supplémentaires augmentent de manière exponentielle le nombre de lignes de données. Il est impossible de définir clairement le nombre réel de lignes, de colonnes et de ventilations pouvant être utilisés pour les rapports des Ad Hoc Analysis. La limite est un ensemble de tous ces facteurs.

## Planification de la distribution d’un rapport {#task_7A3165C8C5C349718FE3B2B0C727ACFD}

Cette procédure explique comment planifier la distribution d’un rapport.

<!-- 

t_schedule_delivery.xml

 -->

1. Click **[!UICONTROL Tools]**, then click **[!UICONTROL Schedule Manager]**.
1. Dans le [!UICONTROL Gestionnaire de planification]**, cliquez sur[!UICONTROL Nouveau].**

## Options de distribution - Définitions {#reference_CA49AC560258471AAE959BCA243F170C}

Définitions des paramètres du menu Options de distribution.

<!-- 

r_delivery_options.xml

 -->

Vous pouvez envoyer vos informations, telles qu’elles sont affichées dans le rapport sélectionné, au format indiqué. Cette opération peut être réalisée une ou plusieurs fois en fonction d’un calendrier de distribution ; vous pouvez spécifier votre format de fichier préféré. Vous pouvez créer et envoyer une signature numérique pour garantir l’authenticité du fichier à son destinataire. Vous pouvez envoyer le fichier à une adresse de courriel ou le télécharger vers un serveur FTP.

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
     <li id="li_36E8DEFDA1B84890A4204A6DFF4E0267">Excel : votre rapport est généré sous forme d’une feuille de calcul comprenant toutes les images. Il peut être modifié dans Microsoft Excel. </li> 
     <li id="li_C918FA3AE8194BD2B59E554DAC7CBBE2">CSV : votre rapport est généré au format CSV (valeurs séparées par des virgules). Ce type de fichier peut être modifié dans un simple éditeur de texte (tel que Bloc-notes) ou un éditeur de feuille de calcul (tel que Microsoft Excel). Il ne contient aucune image. </li> 
     <li id="li_B7C8C098C5264B349C21077A0DEFE059">PDF : votre rapport est généré au format PDF (Portable Document Format). Ce type de fichier ne peut pas être modifié, mais vous pouvez le visualiser dans Adobe Acrobat ou Adobe Reader. </li> 
     <li id="li_B1183DB25DE34B689FBD0E5B44691F49">HTML : votre rapport est généré dans une pièce jointe HTML (HyperText Markup Language). Ce format est utilisé pour composer la plupart des sites Web. Il ne doit pas être modifié, sauf si vous êtes rompu à l’utilisation du code HTML. </li> 
     <li id="li_5ED5F1862AB1490A9FF5695FF9F52C5E">Word : votre rapport est généré sous la forme d’un fichier RTF contenant toutes les images. Il peut être modifié dans Microsoft Word ou WordPad. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Avancé </p> </td> 
   <td colname="col2"> <p> See <a href="/help/analyze/ad-hoc-analysis/c-schedule.md"   > Advanced Format Settings</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Description du fichier </p> </td> 
   <td colname="col2"> <p>E-mail : paramètres d’envoi par courriel. </p> <p>FTP : paramètres pour l’envoi de données vers un serveur FTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Période du rapport et calendrier de remise </p> </td> 
   <td colname="col2"> <p>Indique le moment de remise du rapport. Les nouveaux programmes utilisent la période définie dans le rapport. Par exemple, si vous créez un rapport pour les 90 derniers jours et planifiez une exécution quotidienne, vous recevrez, chaque jour, un rapport portant sur les 90 derniers jours. Si vous créez un rapport avec une période statique à partir du calendrier, le même rapport sera affiché lors de chaque envoi. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Paramètres de format avancé - Définitions {#reference_F99B65BF7C9746638D8147EED147015B}

Définitions des paramètres du menu Paramètres de format avancé.

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
   <td colname="col1"> <p>Ajouter un identifiant au nom de fichier </p> </td> 
   <td colname="col2"> <p>Ajoute automatiquement l’identifiant du rapport au nom de fichier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Ajouter une date au nom de fichier </p> </td> 
   <td colname="col2"> <p> Ajoute automatiquement la date du rapport au nom de fichier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Langue </p> </td> 
   <td colname="col2"> <p> Permet de sélectionner la langue du rapport. Vous pouvez envoyer le rapport dans l’une des langues suivantes, quelle que soit la langue que vous utilisez : </p> 
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
   <td colname="col1"> <p>Codage </p> </td> 
   <td colname="col2"> <p>Indique le type de codage. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Envoyer le rapport sous la forme d’un fichier comprimé </p> </td> 
   <td colname="col2"> <p> Compresse le fichier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Envoyer le fichier de signature numérique </p> </td> 
   <td colname="col2"> <p>Crée une signature numérique à envoyer avec le courriel. </p> </td> 
  </tr> 
 </tbody> 
</table>

