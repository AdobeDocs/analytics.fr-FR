---
description: Une classification est une méthode permettant de catégoriser des données de variables Analytics, puis de les afficher de différentes manières lors de la création de rapports.
subtopic: Classifications
title: À propos des classifications
topic: Admin tools
uuid: abc1a1be-8e37-4b7e-81fd-3e99ac27fc6a
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# À propos des classifications

Une classification est une méthode permettant de catégoriser des données de variables Analytics, puis de les afficher de différentes manières lors de la création de rapports.

Présentation vidéo des [classifications Analytics](https://video.tv.adobe.com/v/16853/?captions=fre_fr).

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > *`<Traffic or Conversion>`*

Lors de la classification, vous établissez une relation entre la variable et les métadonnées associées à cette variable. Les classifications sont le plus souvent utilisées dans les campagnes. Les données collectées à l’aide de variables (eVars, props et ) peuvent être cumulées en appliquant des métadonnées aux valeurs collectées dans les variables.

![Infos sur l’étape](assets/sub_class_create.png)

Une fois classifié, tout rapport que vous pouvez générer à l’aide de la variable clé peut également être généré à l’aide des attributs associés. Vous pouvez, par exemple, classer les produits [!UICONTROL Product IDs] avec des attributs de produit supplémentaires, tels que le nom, la couleur, la taille, la description et le SKU du produit. L’augmentation des données d’ et d’analyses à l’aide d’attributs supplémentaires offre des opportunités de plus approfondies et plus complexes.

>[!IMPORTANT]
>
>La possibilité d’importer des classifications numériques 2 et des classifications activées par date a été supprimée du code base. Cette modification prendra effet avec la version de maintenance de juin 2019. S’il y a des colonnes numériques ou des colonnes activées par date dans le fichier d’importation, ces cellules seront ignorées et les autres données de ce fichier seront importées normalement. Les classifications existantes peuvent toujours être exportées par le biais du workflow de classification standard et sont toujours disponibles dans les rapports.

>[!NOTE] Dans la version de maintenance du 10 mai 2018 d’Analytics, Adobe a commencé à limiter les fonctionnalités des classifications activées par date et numériques. Ces types de classifications ont été supprimés des interfaces Administration et Importateur de classifications. Aucune nouvelle classification numérique et à date d’activation ne peut être ajoutée. Il sera possible de continuer à gérer les classifications actuelles (les transférer, les supprimer) par l’intermédiaire des processus de classification standard et elles resteront disponibles dans le reporting.

Après avoir créé les classifications, vous pouvez exploiter les nouveaux attributs de données dans Adobe Analytics.

**Exemple de codes de suivi**

Supposons qu’au lieu d’afficher les campagnes uniquement en fonction du code de suivi, vous souhaitiez afficher les résultats des campagnes par moteur de recherche, mot-clé et Campaign de. Plutôt que de consacrer des variables de conversion à chacune de ces variables, vous pouvez créer trois classifications de la variable de campagne pour représenter les  Moteur de recherche, Mot-clé et Campaign. Cette stratégie vous permet de voir le de réussite du site en fonction des quatre variables, sans balisage supplémentaire.

Les  et analyses de comprennent des classifications prédéfinies pour la variable de code de suivi, qui  des rapports basés sur les classifications de, appelés Eléments créatifs et Campagnes. Vous devez configurer manuellement les classifications pour toutes les autres variables de conversion et de trafic.

Voir Classifications [du](/help/admin/admin/c-traffic-variables/traffic-classifications.md) trafic et Classifications [des](https://marketing.adobe.com/resources/help/fr_FR/reference/conversion_classifications.html)conversions.

Le tableau suivant décrit les différents types de classifications disponibles et les types de variables qui les prennent en charge. Consultez les informations de la section  [Structure générale d’un fichier](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md) avant de télécharger les fichiers de données.

<table id="table_279728C28D9C40EE832ACC9F211B5F17"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>TYPE </p> </th> 
   <th colname="col2" class="entry"> <p>DISPONIBILITÉ </p> </th> 
   <th colname="col3" class="entry"> <p>DESCRIPTION </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Texte</span> </p> </td> 
   <td colname="col2"> <p>Variables de conversion et de trafic </p> </td> 
   <td colname="col3"> <p>Les classifications de texte définissent un  de qui vous permet de regrouper des données de variable à des fins de  de. </p> <p>Par exemple, si vous vendez des chemises, vous pouvez classer les ventes de chemises (conversions) par couleur, taille et style afin de générer des rapports qui vous permettent de voir les ventes de chemises organisées par ces . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Texte par date d’activation</span> </p> <p>Dans la version de maintenance du 10 mai 2018 d’Analytics, Adobe a commencé à limiter les fonctionnalités des classifications activées par date. Ces types de classifications ont été supprimés des interfaces Administration et Importateur de classifications. Il n’est plus possible d’ajouter de nouvelles classifications activées par date. Il sera possible de continuer à gérer les classifications actuelles (les transférer, les supprimer) par l’intermédiaire des processus de classification standard et elles resteront disponibles dans le reporting. </p> </td> 
   <td colname="col2"> <p>Variables de conversion </p> </td> 
   <td colname="col3"> <p>Une classification de texte par date d’activation vous permet d’affecter des plages de dates à une classification de texte. En règle générale, ce type de classification est utilisé avec les classifications de campagne pour tirer parti de l’affichage de diagramme de Gantt du rapport de <span class="wintitle">campagnes</span>. </p> <p>Vous pouvez inclure les dates de campagnes actuelles dans le fichier de données qui remplit les données de classification. </p> <p>Les Reports &amp; Analytics rassemblent les codes de suivi de campagne même si la date de fin de la campagne est passée. Toutefois, les données de campagne rassemblées après la date de fin ne sont pas associées à la campagne. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Numérique</span> <p>Dans la version de maintenance du 10 mai 2018 d’Analytics, Adobe a commencé à limiter les fonctionnalités des classifications numériques. Ces types de classifications ont été supprimés des interfaces Administration et Importateur de classifications. Il n’est plus possible d’ajouter de nouvelles classifications numériques. Il sera possible de continuer à gérer les classifications actuelles (les transférer, les supprimer) par l’intermédiaire des processus de classification standard et elles resteront disponibles dans le reporting. </p> </p> </td> 
   <td colname="col2"> <p>Variables de conversion </p> </td> 
   <td colname="col3"> <p>Les classifications numériques vous permettent d’appliquer des valeurs numériques fixes aux rapports de <span class="wintitle">conversion</span>. Ces classifications apparaissent comme des mesures dans les rapports. </p> <p>Lorsque vous envisagez d’ajouter une classification <span class="wintitle">numérique</span>, sachez que la valeur numérique doit être fixe et inchangée au fil du temps. </p> </td> 
  </tr> 
 </tbody> 
</table>

