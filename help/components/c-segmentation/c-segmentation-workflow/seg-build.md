---
description: Le créateur de segments fournit un canevas permettant de faire glisser et de déposer des dimensions de mesure, des segments et des  de segmentation des en fonction de la logique de hiérarchie de l’, des règles et des opérateurs. Cet outil de développement intégré vous permet de créer et d’enregistrer des segments simples ou complexes qui identifient les attributs et actions des visiteurs entre les visites et accès aux pages.
title: Création de segments
topic: Segments
uuid: c01393df-ccdd-431c-83a6-3c2700bd4999
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Créateur de segments

The [!UICONTROL Segment Builder] provides a canvas to drag and drop Metrics, Dimensions, Segments, and Events to segment visitors based on container hierarchy logic, rules, and operators. Cet outil de développement intégré vous permet de créer et d’enregistrer des segments simples ou complexes qui identifient les attributs et actions des visiteurs entre les visites et accès aux pages.

>[!IMPORTANT]
>
>Nous avons introduit des modèles d’attribution de dimension dans la version de juin 2019. Voir #6 sous Fonctionnalités de l’interface utilisateur Web ci-dessous.

Il existe plusieurs façons d’accéder au Créateur de segments :

* **Navigation** supérieure dans Analytics : Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Segments]**.
* **[!UICONTROL Analysis Workspace]**: Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**, ouvrez un projet et cliquez sur **[!UICONTROL + New]** > **[!UICONTROL Create Segment]**.
* **[!UICONTROL Reports & Analytics]**: Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Reports]**, ouvrez un rapport existant et cliquez sur l’icône Segments ![](assets/segment_icon.png) dans le volet de navigation de gauche, puis cliquez sur **[!UICONTROL Add]**.
* **[!UICONTROL Ad Hoc Analysis]**: [Créez des segments dans les  ad hoc](/help/components/c-segmentation/c-segmentation-workflow/seg-build.md#build-segments).
* **[!UICONTROL Report Builder]**: Ajouter [ou modifiez des segments dans le créateur](https://marketing.adobe.com/resources/help/fr_FR/arb/segmentation.html)de rapports.

## Interface utilisateur du Créateur de segments {#concept_643F2DF74C544796B58F4656ABC5F726}

Le [!UICONTROL Segment Builder] module vous permet de créer des segments simples ou complexes qui identifient les attributs et actions du entre les visites et les accès aux pages. Il fournit un canevas permettant de faire glisser des dimensions de mesure, des  de ou d’autres segments afin de segmenter les en fonction de la logique de hiérarchie, des règles et des opérateurs.

## Fonctionnalités de l’interface utilisateur Web  {#section_F61C4268A5974C788629399ADE1E6E7C}

The [!UICONTROL Segment Builder] lets you build and edit segments in the web UI (or in a [Java UI in Ad Hoc Analysis](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md)). Vous pouvez ajouter des définitions de règle et des conteneurs afin d’affiner vos segments en les empilant et les imbriquant. Vous pouvez également valider le nombre de de page, de visites et de uniques résultant de votre définition de segment actuelle. Enregistrez ensuite le segment en fonction des besoins futurs.

Accédez au créateur de segments en procédant comme suit :

* Affichez un rapport existant, puis cliquez sur l’icône Segments ![](assets/segment_icon.png) dans le volet de navigation de gauche. In the segment rail that displays, click **[!UICONTROL Add]**.

* From within the Segment Manager, clicking **[!UICONTROL + Add]**.
* Cliquez sur le titre d’un segment existant dans le Gestionnaire de segments afin de modifier le segment dans le Créateur de segments.

![](assets/segment_builder_ui.png)

1. **[!UICONTROL Title]**: Permet de nommer ou de renommer le segment.
1. **[!UICONTROL Description]** : fournissez une description du segment. Vous devez fournir une description si vous souhaitez partager le segment.
1. **[!UICONTROL Tags]**: [Balisez le segment](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md) que vous créez en sélectionnant à partir d’un de balises existantes ou en créant une nouvelle balise.
1. **[!UICONTROL Definitions]**: C’est là que vous [créez et configurez des segments](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md), ajoutez des règles et imbriquez et séquencez des  de. Permet de fournir une description du nouveau segment en sélectionnant le conteneur et en faisant glisser-déposer les dimensions, segments ou mesures dans la définition.
1. **[!UICONTROL Show]**: (Sélecteur  supérieur.) Vous permet de sélectionner le [](/help/components/c-segmentation/seg-overview.md) de niveau supérieur ( [!UICONTROL Visitor], [!UICONTROL Visit], [!UICONTROL Hit]). Le conteneur de niveau supérieur par défaut est le conteneur Accès.
1. **[!UICONTROL Options]**: (engrenage) icône

   * **[!UICONTROL + Add container]**: Vous permet d’ajouter une nouvelle  de (sous le de niveau supérieur) à la définition de segment.
   * **[!UICONTROL + Add container from selection]**: Permet de créer un nouveau  à partir du ou des éléments que vous avez (multi-) sélectionné dans le champ Définitions.
   * **[!UICONTROL Exclude]**: Permet de définir le segment en excluant une ou plusieurs dimensions, segments ou mesures.

1. **[!UICONTROL Attribution Models]**: Pour la segmentation des dimensions. Les modèles de dimension sont particulièrement utiles pour la segmentation séquentielle, comme dans ceux qui prennent en charge les visualisations de flux :

   * **[!UICONTROL Repeating]** (par défaut) : Inclut des instances et des valeurs persistantes pour la dimension.
   * **[!UICONTROL Instance]** : inclut des instances pour la dimension.
   * **[!UICONTROL Non-repeating instance]**: Inclut les instances uniques (non répétitives) pour la dimension.
   ![](assets/attribution-models.jpg)

1. **[!UICONTROL Dimensions]** : les dimensions sont glissées et déposées depuis la liste Dimensions (barre latérale orange).
1. **[!UICONTROL Comparison]**: Vous pouvez comparer et contraindre des valeurs à l’aide d’opérateurs sélectionnés.
1. **[!UICONTROL Value]**: Valeur saisie ou sélectionnée pour la dimension, le segment ou la mesure.
1. **[!UICONTROL And/Or/Then]**: Attribue les [!UICONTROL AND/OR/THEN] opérateurs entre les  ou les règles du. L’opérateur ALORS permet de [définir des segments séquentiels](/help/components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md).
1. **[!UICONTROL Metric]**: (Barre latérale verte) Mesure qui a été glissée et déposée depuis le de mesures.
1. **[!UICONTROL Comparison]** opérateur : Vous pouvez comparer et contraindre des valeurs à l’aide d’opérateurs sélectionnés.
1. **[!UICONTROL Value]**: Valeur saisie ou sélectionnée pour la dimension, le segment ou la mesure.
1. **[!UICONTROL X]** : (Supprimer) permet de supprimer la partie en question de la définition de segment.
1. **[!UICONTROL Save]** ou **[!UICONTROL Cancel]**: Enregistre ou annule le segment. After clicking **[!UICONTROL Save]**, you are taken to the Segment Manager where you can manage the segment.
1. **[!UICONTROL Search]**: Recherche le  de dimensions, de segments ou de mesures.
1. **[!UICONTROL Dimensions]** : (Liste) cliquez sur l’en-tête pour développer la liste.
1. **[!UICONTROL Metrics]** : cliquez sur l’en-tête pour développer la liste.
1. **[!UICONTROL Segments]** : cliquez sur l’en-tête pour développer la liste.
1. **[!UICONTROL Report suite selector]**: Permet de sélectionner la suite de rapports sous laquelle ce segment sera enregistré. Vous pouvez tout de même utiliser le segment dans toutes les suites de rapport.
1. **[!UICONTROL Segment Preview]**: Vous permet d’ les mesures clés afin de déterminer si vous disposez d’un segment valide et sa largeur. Représente la ventilation du jeu de données auquel vous pouvez vous attendre si vous appliquez ce segment. Affiche 3 cercles concentriques et un  pour afficher le nombre et le pourcentage de correspondances pour [!UICONTROL Hits], [!UICONTROL Visits]et [!UICONTROL Visitors] pour un segment exécuté par rapport à un jeu de données. Ce graphique est mis à jour immédiatement après avoir créé ou apporté des modifications à votre définition de segment.
1. **[!UICONTROL Product Compatibility]**: Fournit un dont les produits Adobe Analytics (  Espace de travail, [!UICONTROL Reports & Analytics]les, les ad hoc, l’entrepôt de données) avec lesquels le segment que vous avez créé est compatible. La plupart des segments sont compatibles avec tous les produits. Néanmoins, tous les opérateurs et dimensions ne sont pas compatibles avec l’ensemble des produits Analytics, notamment  [Data Warehouse](/help/components/c-segmentation/seg-reference/seg-compatibility.md). Ce graphique est mis à jour instantanément quand vous modifiez votre définition de segment.

Les segments avec des plages de dates incorporées fonctionnent toujours différemment dans Analysis Workspace par rapport au composant [!UICONTROL Reports & Analytics] : dans Workspace, un segment avec une plage de dates incorporée remplace la plage de dates du panneau. En revanche, le composant [!UICONTROL Reports & Analytics] indique l’intersection de la plage de dates du rapport avec la plage de dates incorporée du segment.

**[!UICONTROL Publish to Experience Cloud (for `<report suite name>`)]**: (Non affiché à l’écran) Cette option s’affiche uniquement si la suite de rapports dans laquelle vous enregistrez ce segment est [activée pour Experience Cloud](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md). By publishing a segment to the Experience Cloud, you can use the segment for marketing activity in the [!UICONTROL Audience Library], [!DNL Target], and [!DNL Audience Manager]. Un titre et une description du segment sont requis.

>[!NOTE]Dans Analytics, vous pouvez modifier ou supprimer un segment publié. Si le segment est en cours d’utilisation, un message d’avertissement s’affiche lorsque vous le modifiez. Vous ne pouvez pas supprimer un segment publié en cours d’utilisation par Adobe [!DNL Target].

![](assets/segment_publish_to_mac_copy.png)

>[!IMPORTANT]
>
>Vous devez limiter à 20 le nombre d’audiences partagées depuis Analytics pour éviter des retards de traitement supplémentaires. Les audiences partagées avec Experience Cloud depuis Analytics ne doivent pas dépasser 20 millions de membres. En outre, en raison de la mise en cache, les suites de rapports supprimées dans Analytics nécessitent 12 heures avant que la suppression ne s’affiche dans Experience Cloud.

>[!IMPORTANT]
>
>Une fois qu’un visiteur se qualifie pour l’audience partagée depuis Analytics, un délai de 24 à 48 heures est nécessaire avant que les informations soient exploitables dans [!DNL Target], [!DNL Advertising Cloud] et [!DNL Campaign].

## Création de segments {#build-segments}

1. Faites simplement glisser un  de dimension, de segment ou de mesure du volet de gauche vers le [!UICONTROL Definitions] champ.

   ![](assets/drag_n_drop_dimension.png)

   Le  de niveau [!UICONTROL Hit] supérieur par défaut s’affiche après avoir fait glisser un élément vers [!UICONTROL Definitions]. You can change the container type to Visit or Visitor from the **[!UICONTROL Show]** drop-down menu.

1. Définissez l’[opérateur](/help/components/c-segmentation/seg-reference/seg-operators.md) dans le menu déroulant.
1. Saisissez ou sélectionnez une valeur pour l’élément sélectionné.
1. Ajouter un supplémentaire  si nécessaire, en utilisant **[!UICONTROL And]**, **[!UICONTROL Or]** ou **[!UICONTROL Then]** des règles.
1. Après avoir placé le  et défini les règles, consultez les résultats du segment dans le graphique de validation en haut à droite. Le programme de validation indique le pourcentage et le nombre absolu de  de page, de visites et de uniques qui correspondent au segment que vous avez créé.
1. Under **[!UICONTROL Tags]**, [tag](/help/components/c-segmentation/c-segmentation-workflow/seg-tag.md) the container by selecting an existing tag or creating a new one.
1. Click **[!UICONTROL Save]** to save the segment.

Vous accédez maintenant au [Gestionnaire de segments](/help/components/c-segmentation/c-segmentation-workflow/seg-manage.md), où vous pouvez marquer, partager et gérer votre segment de différentes manières.

## Créer et imbriquer des conteneurs {#section_1C38F15703B44474B0718CEF06639EFD}

Vous pouvez [créer une structure de conteneurs](/help/components/c-segmentation/seg-overview.md) et y placer des règles logiques et des opérateurs.

1. Cliquez sur **[!UICONTROL Options > Add Container]**.

   ![](assets/add_container.png)

   Un nouveau [!UICONTROL Hit] s’ouvre sans [!UICONTROL Hit] ( de de page) identifié.

   ![](assets/new_container.png)

1. Modifiez le type de  du selon vos besoins.
1. Faites glisser une dimension, un segment ou un  du volet de gauche vers le  du.
1. Continue to add new containers from the top-level **[!UICONTROL Options]** > **[!UICONTROL Add container]** button at the top of the definition, or add containers from within a container to nest logic.

   **OU**

   Sélectionnez une ou plusieurs règles, puis cliquez sur **[!UICONTROL Options]** > **[!UICONTROL Add container from selection]**. Votre sélection devient ainsi un conteneur distinct.

## Utiliser des périodes dans les segments {#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE}

Vous pouvez créer des segments qui contiennent des périodes flottantes afin d’obtenir des réponses sur les campagnes ou les événements en cours.

Vous pouvez par exemple créer facilement un segment qui comprend « toutes les personnes qui ont effectué un achat au cours des 60 derniers jours ».

Vous créez un  Visite et, dans celui-ci, ajoutez la [!UICONTROL Last 60 days] période et la mesure [!UICONTROL Orders is greater than or equal to 1], avec un opérateur ET :

![](assets/date-ranges.png)

## Empiler des segments {#task_58140F17FFD64FF1BC30DC7B0A1B0E6D}

L’empilement des segments fonctionne en combinant les critères de chaque segment à l’aide d’un opérateur &quot;et&quot;, puis en appliquant les critères combinés.

Par exemple, l’empilement d’un segment &quot;utilisateurs de téléphones mobiles&quot; et d’un segment &quot;géographie américaine&quot; renvoyait des données uniquement pour les utilisateurs de téléphones mobiles aux États-Unis.

Considérez ces segments comme des blocs de création ou des modules que vous pouvez inclure dans une bibliothèque de segments pour que les utilisateurs les utilisent comme bon leur semble. Vous pouvez ainsi réduire considérablement le nombre de segments nécessaires. Supposons, par exemple, que vous ayez 40 segments :

* 20 pour les utilisateurs de téléphones mobiles dans différents pays (Etats-Unis_mobile, Allemagne_mobile, France_mobile, Brésil_mobile, etc.)
* 20 pour les utilisateurs de tablettes dans différents pays (Etats-Unis_tablette, Allemagne_tablette, France_tablette, Brésil_tablette, etc.)

À l’aide de l’empilement de segments, vous pouvez réduire votre nombre de segments à 22 et les empiler, le cas échéant. Vous devez créer les segments suivants :

* un segment pour les utilisateurs mobiles
* un segment pour les utilisateurs de tablette
* 20 segments pour les différentes géographies

>[!NOTE] Lors de l’empilement de deux segments, ils sont par défaut associés à une instruction ET, Il n’est pas possible de changer cela en instruction OU.

1. Accédez au Créateur de segments.
1. Fournissez un titre et une description pour le segment.

   Résultat de l’étape 1. Click **[!UICONTROL Show Segments]** to bring up the list of segments in the left navigation.

   Résultat de l’étape 1. Faites glisser et déposez les segments à empiler dans le canevas de définition de segment. Voici un exemple de segment qui empile les segments existants &quot;Visites à partir de tablettes&quot; et &quot;Géo US&quot; :

   ![](assets/seg_stack2.png)

1. Enregistrez le segment.

   Résultat de l’étape

## Utiliser des modèles de segments {#concept_5098446CC78D441E93B8E4D1D1EA6558}

Les modèles représentent les anciens segments préconfigurés et de suite.

In the Segment Manager, click **[!UICONTROL Add]**, which takes you to the Segment Builder. Cliquez maintenant sur l’icône Segments ![](assets/segment_icon.png)

pour afficher le rail des segments. Les modèles de segments apparaissent au bas du  de segments. Ils se distinguent par une icône de dossier à gauche du nom du modèle :

![](assets/seg_template.png)

Vous pouvez faire glisser ces modèles dans le canevas Définitions et les utiliser tels qu’ils ont été définis, ou les modifier.

<table id="table_98B87D807E9344C9BEBF072C65D87B1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nom du modèle </th> 
   <th colname="col2" class="entry"> Définition </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Abandonner le panier </td> 
   <td colname="col2">Données  pour les qui ont ajouté des éléments à leur panier mais n’ont rien commandé. Dans la définition de segment, le est Visite. La règle de ce segment séquentiel est <p> Les ajouts au panier ne sont pas nuls </p> <p>Alors </p> <p>Les commandes sont égales à 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Premières visites </td> 
   <td colname="col2">Données  pour les qui ont visité le site au maximum une [1] fois. Dans la définition de segment, le est Visite. La règle est <p>Nombre de visites = 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Non-acheteurs </td> 
   <td colname="col2">Affiche les données concernant les visiteurs qui n’ont pas participé à un événement de commande. Dans la Définition de segment, le  de est. Ce segment utilise la logique Exclure. La règle est <p>Les commandes ne sont pas nulles. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite sur plusieurs pages (hors rebonds) </td> 
   <td colname="col2"> de données pour les qui ont effectué plusieurs visites. Dans la Définition de segment, le  de est. Ce segment utilise la logique Exclure. La règle est <p>Accès unique n’est pas nul. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recherche payante </td> 
   <td colname="col2">Affiche les données concernant les visiteurs provenant d’une recherche payante. Dans la définition de segment, le est Visite. La règle est <p>Recherche payée est égal à 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Acheteurs </td> 
   <td colname="col2">Affiche les données concernant les visiteurs qui ont participé à un événement de commande. Dans la Définition de segment, le  de est. La règle est <p>Les commandes ne sont pas nulles. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visites retours </td> 
   <td colname="col2"> de données provenant de qui ont effectué au moins une visite. Dans la définition de segment, le est Visite. La règle est <p>Nombre de visites est supérieur à 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visites sur une seule page </td> 
   <td colname="col2"> de données provenant de visites dans lesquelles vous voyez une seule valeur de page, même si vous pouvez envoyer plusieurs  de page pendant cette visite. Les visites mono-page avec de liens de sortie sont incluses dans le segment. Dans la définition de segment, le est Visite. La règle est <p>Visites mono-page = 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Produit consulté Ajouter au panier </td> 
   <td colname="col2">Données  pour les qui ont consulté des produits mais n’ont pas ajouté de panier. Dans la définition de segment, le est Visite. La règle de ce segment séquentiel est <p>La  du produit n’est pas nulle </p> <p>Alors </p> <p> Ajouts au panier est égal à 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visites à partir de la campagne </td> 
   <td colname="col2">Données  des référencés par les campagnes. Dans la définition de segment, le est Visite. La règle est <p>Le code de suivi n’est pas nul. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visites depuis des périphériques mobiles </td> 
   <td colname="col2"> de données provenant de utilisant des périphériques mobiles. Dans la définition de segment, le est Visite. La règle est <p>Périphérique mobile non nul. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visites depuis la recherche naturelle </td> 
   <td colname="col2">Données  des ne provenant pas d’une recherche payante. Dans la définition de segment, le est Visite. La règle est <p>Recherche payante = 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visites depuis des périphériques non mobiles </td> 
   <td colname="col2"> données des n’utilisant pas de périphériques mobiles. Dans la définition de segment, le est Visite. Ce segment utilise la logique Exclure. La règle est <p>Type de périphérique mobile = Téléphone mobile </p> <p>OU </p> <p>Type de périphérique mobile = Tablette. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visites à partir de téléphones </td> 
   <td colname="col2"> données des utilisant des téléphones. Dans la définition de segment, le est Visite. La règle est <p>Type de périphérique = Téléphone mobile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visites à partir de moteurs de recherche </td> 
   <td colname="col2">Données  des provenant des moteurs de recherche. Dans la définition de segment, le est Visite. La règle est <p>Type  est égal à Moteurs de recherche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visites issues des réseaux sociaux </td> 
   <td colname="col2">Affiche les données concernant les visiteurs venus par l’entremise des sites sociaux. Dans la définition de segment, le est Visite. La règle est <p>Type de  est égal à Réseaux sociaux. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visites à partir de tablettes </td> 
   <td colname="col2"> données des utilisant des tablettes. Dans la définition de segment, le est Visite. La règle est <p>Type de périphérique = Tablette. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visites avec cookie d’identifiant visiteur </td> 
   <td colname="col2">des données des sur votre site, où un cookie persistant est requis. Dans la définition de segment, le est Visite. La règle est <p>Cookie persistant = 1. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemple : segment de visiteurs de campagnes {#concept_61AC6115097B4EB3AEFE8CE98F38315D}

Montre un exemple de ce segment fréquemment utilisé.

De nombreux clients souhaitent afficher les mesures des qui ont répondu à des campagnes spécifiques. La création d’un segment de campagne est un moyen facile d’obtenir ces données.

La création de ce segment dans le créateur de segments signifie que, à partir d’un de visites de niveau supérieur, vous faites glisser une dimension de campagne, dans ce cas Campaign Nom :

![](assets/seg_campaign_visitor.png)

(Facultatif) Vous pouvez également appliquer une balise Campagnes à ce segment si vous souhaitez facilement filtrer tous les segments liés à la campagne.
