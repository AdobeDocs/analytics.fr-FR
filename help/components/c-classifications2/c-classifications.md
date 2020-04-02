---
description: Une classification est une méthode permettant de catégoriser des données de variables Analytics, puis de les afficher de différentes manières lors de la création de rapports.
subtopic: Classifications
title: À propos des classifications
topic: Admin tools
uuid: abc1a1be-8e37-4b7e-81fd-3e99ac27fc6a
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# À propos des classifications

Une classification est une méthode permettant de catégoriser des données de variables Analytics, puis de les afficher de différentes manières lors de la création de rapports.

Présentation vidéo des [classifications Analytics](https://video.tv.adobe.com/v/16853/?captions=fre_fr).

**[!UICONTROL Admin]** > **[!UICONTROL Suite de rapports]** > **[!UICONTROL Modifier les paramètres]** >*`<Traffic or Conversion>`*

Lors de la classification, vous établissez une relation entre la variable et les métadonnées qui y sont liées. Les classifications sont le plus souvent utilisées dans des campagnes. Les données collectées à l’aide de variables (eVars, props et événements) peuvent être collationnées en appliquant des métadonnées aux valeurs collectées dans les variables.

![Infos sur l’étape](assets/sub_class_create.png)

Une fois classifié, tout rapport pouvant être généré en utilisant la variable clé peut aussi l’être en utilisant les attributs associés. Par exemple, il est possible de classer les [!UICONTROL ID de produits] avec des attributs de produit supplémentaires, tels que le nom, la couleur, la taille, la description et la référence du produit. Enrichir les données de rapports et analyses avec des attributs supplémentaires vous permet de disposer de rapports plus approfondis et complexes.

>[!IMPORTANT]
>
>La possibilité d’importer des classifications numériques 2 et des classifications activées par date a été supprimée du code base. Cette modification prendra effet lors de la version de maintenance de juin 2019. S’il y a des colonnes numériques ou des colonnes activées par date dans le fichier d’importation, ces cellules seront ignorées et les autres données de ce fichier seront importées normalement. Les classifications existantes peuvent toujours être exportées par un workflow de classification standard et continuent à être disponibles dans les rapports.

> [!NOTE] Dans la version de maintenance du 10 mai 2018 d’Analytics, Adobe a commencé à limiter les fonctionnalités des classifications activées par date et numériques. Ces types de classifications ont été supprimés des interfaces Administration et Importateur de classifications. Il n’est plus possible d’ajouter de nouvelles classifications numériques et activées par date. Il sera possible de continuer à gérer les classifications actuelles (les transférer, les supprimer) par l’intermédiaire des processus de classification standard et elles resteront disponibles dans le reporting.

Après avoir créé les classifications, vous pouvez exploiter les nouveaux attributs de données dans Adobe Analytics.

**Exemples de codes de suivi**

Supposons qu’au lieu de visualiser des campagnes sur la seule base du code de suivi, vous souhaitiez afficher les résultats de campagne par Moteur de recherche, Mot-clé ou Canal de campagne. Plutôt que de consacrer des variables de conversion à chacun de ces éléments, vous pouvez créer trois classifications de la variable de campagne afin de représenter Moteur de recherche, Mot-clé ou Canal de campagne. Cette stratégie vous permet d’afficher les événements de succès du site selon les quatre variables, sans aucun balisage supplémentaire.

Les rapports et analyses contiennent des classifications prédéfinies pour la variable Code de suivi, ce qui génère des rapports basés sur les classifications appelés Éléments créatifs et Campagnes. Vous devez configurer manuellement les classifications pour toutes les autres variables de conversion et de trafic.

Reportez-vous aux sections [Classifications de trafic](/help/admin/admin/c-traffic-variables/traffic-classifications.md) et [Classifications des conversions](https://marketing.adobe.com/resources/help/fr_FR/reference/conversion_classifications.html).

Le tableau ci-après décrit les différents types de classifications disponibles et les types de variables les prenant en charge. Consultez les informations de la section  [Structure générale d’un fichier](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md) avant de télécharger les fichiers de données.

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
   <td colname="col3"> <p>Les classifications de texte définissent une catégorie qui vous permet de regrouper les données de variable aux fins de création de rapports. </p> <p>Par exemple, si vous vendez des chemises, vous souhaiterez peut-être classer leurs ventes (conversions) par couleur, taille et style afin de générer des rapports vous permettant de voir les ventes organisées selon ces catégories. </p> </td> 
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

