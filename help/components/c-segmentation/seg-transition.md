---
description: valeur nulle
keywords: segmentation ; segments
seo-description: valeur nulle
seo-title: Questions fréquentes
solution: Analytics
title: Questions fréquentes
topic: Segments
uuid: f 49 dc 829-1 d 53-4183-9 add -1 aeaa 5219 d 89
translation-type: tm+mt
source-git-commit: fb27d500a725a540e632952295aa2ea3a3a21fb6

---


# Questions fréquentes

Répond fréquemment aux questions fréquentes sur les fonctionnalités de segmentation, l'accès, les autorisations, les bonnes pratiques et la gestion des segments hérités.

## Fonctionnalités {#section_BD58629D1A9346BF879E229FA6BEC7A2}

* Segmentation dans Analysis Workspace :

   * Vous pouvez [comparer des segments](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/segment-comparison.html).
   * Utilisez les [segments comme dimensions](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/segments_as_dimensions.html) dans une comparaison.
   * Utilisez des segments dans [l’analyse des abandons](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/graphics/compare-segments-fallout.html).

* Vous pouvez [appliquer plusieurs segments à un rapport ou à un projet](../../components/c-segmentation/c-segmentation-workflow/seg-workflow.md#task_13E69C7D428A43EF9CCCA7F1104F1E8F).
* Les segments fonctionnent dans toutes les suites de rapports.
* The [Segment Builder](../../components/c-segmentation/c-segmentation-workflow/seg-workflow.md#concept_643F2DF74C544796B58F4656ABC5F726) simplifies segment creation.
* Le [gestionnaire de segments](../../components/c-segmentation/c-segmentation-workflow/seg-workflow.md#concept_7A2E019317864065B7C641DC3315928F) permet de configurer des [processus](../../components/c-segmentation/c-segmentation-workflow/seg-workflow.md#concept_6D2E1A72A3AD4EBBB9135094F2D9DEDF) pour le partage, le marquage, la vérification et l’approbation des segments.

* Vous pouvez [marquer les segments](../../components/c-segmentation/c-segmentation-workflow/seg-workflow.md#concept_CD892CEB326C4986A1B67487052DBA50) pour les organiser et les rechercher ultérieurement au lieu d’utiliser des dossiers. Previously, you used folders (in [!DNL Ad Hoc Analysis]) to organize your segments.

* Vous pouvez créer des [segments séquentiels](/help/components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md) en dehors des Ad Hoc Analysis.
* Le conteneur de pages vues a été renommé « conteneur d’accès » afin d’indiquer que ce conteneur segmente tous les types de données et pas uniquement les pages vues. Par exemple, les appels de suivi des liens et les appels trackAction provenant des Kits de développement logiciel (SDK) mobiles sont tous inclus ou exclus par le conteneur d’accès. Notez qu’aucune modification n’a été apportée au fonctionnement de ce conteneur, il a simplement été renommé.

Voir l’article [Amélioration de la segmentation dans Adobe Analytics](https://blogs.adobe.com/digitalmarketing/analytics/improving-segmentation-adobe-analytics/) sur le blog de Digital Marketing pour en savoir plus.

## Access the Segmentation Tools {#section_088AD0E4E21943DFA8CF7206AEC485DD}

**Comment puis-je accéder au Créateur de segments ?**

Accédez au Créateur de segments en procédant comme suit :

* Affichez un rapport existant, puis cliquez sur l’icône Segments ![ dans le volet de navigation de gauche. ](assets/segment_icon.png) In the segment rail that displays, then click **[!UICONTROL Add]**, or

* At the top of the Segment Manager, clicking **[!UICONTROL + Add]**.  ![](assets/add_button.png)

   ou

* cliquez sur le titre d’un segment existant dans le Gestionnaire de segments afin de le modifier dans le Créateur de segments.

**Comment puis-je accéder au Gestionnaire de segments ?**

Accédez au Gestionnaire de segments en procédant comme suit :

* Going to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** in the top navigation. Then click **[!UICONTROL Segments]**, or

* Affichez un rapport existant, puis cliquez sur l’icône Segments ![ dans le volet de navigation de gauche. ](assets/segment_icon.png) Then click **[!UICONTROL Manage]**, or

* appuyez sur la barre oblique « / » n’importe où dans l’interface et recherchez le Gestionnaire de segments.

**Vers quel emplacement le menu déroulant des segments existants a-t-il été déplacé ?**

The segment drop-down in Reports &amp; Analytics has been replaced by a much more feature rich [Segment Builder](../../components/c-segmentation/c-segmentation-workflow/seg-workflow.md#concept_643F2DF74C544796B58F4656ABC5F726) interface that lets you to create "universal" segments usable across report suites and across Adobe Analytics solutions. To view a list of existing segments, click the Segments icon  ![](assets/segment_icon.png)

dans la navigation de gauche et le rail de segments s'affiche.

**Vers quel emplacement le menu déroulant des suites de rapports existantes a-t-il été déplacé ?**

Le menu déroulant des suites de rapports a été déplacé en regard du sélecteur de dates dans le coin supérieur droit de chaque rapport ou tableau de bord.

![](assets/report_suite_selector.png)

## Autorisations {#section_648DFA3A882146C485A84ED014EEC707}

**De quels droits et privilèges ai-je besoin pour utiliser, créer et gérer les segments ?**

Par défaut, tous les utilisateurs sont autorisés à créer et à modifier des segments personnels. Toutefois, les administrateurs peuvent distribuer des [autorisations de créer des segments](https://marketing.adobe.com/resources/help/en_US/reference/groups.html) aux utilisateurs et en affecter à des groupes spécifiques. Ces segments peuvent être partagés directement avec tout autre utilisateur d’Analytics.

Les administrateurs peuvent modifier n’importe quel segment et partager les segments avec des groupes et toute personne de l’entreprise. [Plus…](../../components/c-segmentation/seg-reference/seg-rights.md)

**Puis-je consulter tous les segments de mon entreprise ?**

Yes, Admins can see all segments within the [!DNL Analysis Workspace] and [!DNL Reports & Analytics] user interfaces.

Les analyses ad hoc et le Créateur de rapports affichent les segments que vous possédez et les segments qui sont partagés avec vous.

**Puis-je gérer tous les segments Analytics dans le Gestionnaire de segments ?**

Oui, vous pouvez gérer tous les segments dans le Gestionnaire de segments dans Analysis Workspace, dans les rapports et analyses et dans les analyses ad hoc. Le Gestionnaire de segments affiche des segments que le propriétaire (utilisateur qui a créé le segment), les utilisateurs partagés et les administrateurs peuvent consulter. Le sélecteur de segments affiche les segments possédés par l’utilisateur et partagés avec ce dernier.

Admins can see all segments within the Analysis Workspace and [!DNL Reports & Analytics] user interfaces.

Les analyses ad hoc et le Créateur de rapports affichent uniquement les segments que vous avez créés ou les segments qui ont été partagés avec vous.

**Pourquoi ne puis-je pas supprimer ce segment ?**

Si le segment a été [publié sur Experience Cloud](../../components/c-segmentation/c-segmentation-workflow/seg-workflow.md#concept_1E9FC92437D748C392546542B6511D01), vous ne pouvez pas le supprimer ni le modifier. Vous pouvez toutefois le copier et modifier la version copiée.

## Bonnes pratiques {#section_E2C3A1B4B4274D1B86CAA9C0359D049C}

**Que dois-je faire des segments en double portant le même nom mais ayant des définitions différentes ?** Maintenant que les segments fonctionnent dans plusieurs suites de rapports, il est possible que vous disposiez de plusieurs segments portant le même nom. Il est conseillé d’effectuer les opérations suivantes :

* renommer les segments portant le même nom mais ayant des définitions différentes, ou
* supprimer les segments qui ne sont plus utiles.

**Quelles sont les recommandations d’Adobe au sujet du nettoyage des segments ?**

* Marquez tous les segments avec une balise héritée.
* Examinez les segments à votre disposition.
* Ajoutez les segments à la bibliothèque de segments lorsque cela est possible.
* Approuvez les segments canoniques.
* Marquez les segments en fonction des  [bonnes pratiques](../../components/c-segmentation/c-segmentation-workflow/seg-workflow.md#concept_CD892CEB326C4986A1B67487052DBA50).

## Gestion des segments existants {#section_76CF47142D1A4FB6A0718AD9073049FE}

**Qu’est-il advenu de mes segments existants ?**

Vos segments existants continueront à fonctionner comme auparavant. Tout rapport auquel ces segments sont appliqués continuera à fonctionner correctement. [Plus...](../../components/c-segmentation/seg-transition.md#section_83ACAB256F394DCD8B424D8920BDD853)

La plupart des anciens segments prédéfinis et de suite seront migrés sous la forme de  modèles de segments dans le Créateur de segments. Les modèles de segment servent à créer rapidement des segments personnalisés avec des audiences courantes. Ils ne peuvent pas être directement appliqués à un rapport, mais peuvent être facilement enregistrés dans un segment personnalisé.

Les modèles de segments sont marqués par une icône spéciale dans le Créateur de segments :

![](assets/seg_templates.png)

**Qu’est-il advenu de mes dossiers de segments existants ?**

À la place des dossiers (analyses ad hoc), le Gestionnaire de segments utilise des  balises. Les noms de dossiers sont automatiquement convertis en balises et ces balises sont appliquées aux segments respectifs.

**Qu’est-il advenu des rapports planifiés auxquels des segments avaient été appliqués ?**

Les rapports planifiés continuent de fonctionner correctement avec les segments que vous avez définis.

Lorsque vous supprimez un segment, les rapports planifiés et les tableaux de bord auxquels ce segment est appliqué continuent de fonctionner normalement, c’est-à-dire que le segment ou le tableau de bord continue à utiliser le segment supprimé.

Les rapports planifiés ne sont pas mis à jour lorsque vous modifiez un segment portant le même nom. Par exemple, supposons que 2 segments portant le même nom figurent dans différentes suites de rapports :

![](assets/duplicate_seg_names.png)

Vous êtes doté d’un signet qui référence le segment pour la suite de rapports mainprod. Puis, vous supprimez ce segment car il s’agit d’un doublon. Le signet continue à fonctionner, référençant la définition du segment supprimé. Si vous modifiez la définition de segment du segment maindev pour inclure l’île Catalina et Tijuana au Mexique, le segment appliqué au signet ne change pas. Il utilise l’ancienne définition. Pour corriger ce problème, mettez à jour le signet qui référence la nouvelle définition. Si vous n’êtes pas certain qu’un signet, tableau de bord ou rapport planifié utilise un segment supprimé, vous pouvez modifier le nom du segment restant afin qu’il soit plus clair que le signet utilise le segment restant.

**Qu’advient-il des segments d’entrepôt de données ?**

Tous les segments d’entrepôt de données existants fonctionnent toujours dans l’entrepôt de données. La plupart des segments d'entrepôt de données fonctionneront aussi dans d'autres composants tels que Analysis Workspace, Ad - Analyses ad hoc et Rapports et analyses.

Vous pouvez créer ou modifier de nouveaux segments d’entrepôt de données depuis le Créateur/Gestionnaire de segments. Le mécanisme de compatibilité des produits du Créateur de segments détermine automatiquement si un segment est compatible avec l’entrepôt de données.

**Qu’advient-il des segments favoris (analyses ad hoc) ?**

Ces segments des analyses ad hoc s’affichent sous forme de segments standard dans Adobe Analytics.

Ils ne doivent pas être confondus avec la fonctionnalité Favoris du Gestionnaire de segments qui permet de marquer les segments comme favoris.

**Qu’advient-il des segments préconfigurés ?**

* **Visites sur une seule page**
* **Visites depuis des périphériques mobiles**
* **Visites depuis la recherche naturelle**
* **Visites d’une recherche payante**
* **Visites avec cookie d’identifiant visiteur**

Ces segments seront migrés sous forme de modèles de segments dans le Créateur de segments.

Les rapports existants auxquels sont appliqués ces segments continueront de fonctionner correctement.

** Qu'advient-il des segments d'Experience Cloud (Suite) : **

* Non-acheteurs
* Acheteurs
* Premières visites
* Visites depuis les sites sociaux
* Visites de plus de 10 minutes*
* Visites avec 5+ visites précédentes*
* Visites depuis Facebook*

La plupart de ces segments (sauf ceux marqués d’un astérisque *) seront migrés en tant que  modèles de segments dans le Créateur de segments. En outre, plusieurs nouveaux modèles de segments ont été ajoutés.

Les rapports existants auxquels sont appliqués ces segments continueront de fonctionner correctement.

**Qu’advient-il des segments administrateur (également appelés « segments globaux ») ?**

Les segments d’**administrateur** seront migrés vers la nouvelle interface de segment et s’afficheront en tant que segments partagés avec tout le monde.

Le propriétaire de ces segments est défini sur l’administrateur doté du compte le plus ancien dans la liste des administrateurs de la société de connexion. Toutefois, tous les administrateurs peuvent supprimer, modifier et partager ces segments.

L’interface de gestion des segments d’Admin Console dans laquelle les administrateurs ont créé et géré ces segments globaux n’est plus disponible. Les administrateurs doivent désormais utiliser le nouveau Créateur de segments pour créer des segments et les partager avec les groupes ou individus appropriés ou à l’échelle de l’entreprise.

<!-- 

seg_definition.xml

 -->

Les segments existants qui utilisent une logique qui a été modifiée comme indiqué dans ce document continuent à fonctionner correctement, bien qu’ils doivent être mis à jour pour pouvoir être enregistrés à nouveau. Par exemple, si vous êtes doté d’un segment existant pour lequel États-Unis contient « New-York », il continue à fonctionner correctement, mais la prochaine fois que vous modifiez le segment, vous devrez le mettre à jour afin d’utiliser le type énuméré avec la condition « égal à ».

**Conseils de migration**

Les conseils suivants vous aideront à migrer les dimensions courantes :

* Ville géo/région/pays : recherchez et sélectionnez des villes, régions ou pays spécifiques au lieu d'utiliser une correspondance partielle.
* Navigateurs : utilisez la dimension Types de navigateur pour obtenir tous les navigateurs dans un type, par exemple Google Chrome.
* Systèmes d'exploitation : utilisez les dimensions du système d'exploitation pour obtenir tous les systèmes d'exploitation sous un type, par exemple Microsoft Windows.

* [Dimensions nouvelles et renommées](../../components/c-segmentation/seg-transition.md#section_73CF121B64A24DEF8E6499F3167BF742)
* [Modifications apportées à](../../components/c-segmentation/seg-transition.md#section_1A9EDEE5CBC44B5AA6262560052ABE77)
* [Modifications apportées à plus petit et plus grand que](../../components/c-segmentation/seg-transition.md#section_84A8AAD0344148AD9F9211D3EB271903)

## Dimensions nouvelles et renommées {#section_73CF121B64A24DEF8E6499F3167BF742}

Le tableau suivant contient une liste de dimensions renommées dans le Créateur de segments.

<table id="table_1A8C1940FD0446FA8414C6A7DE66E44C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nouveau nom de la dimension </th> 
   <th colname="col2" class="entry"> Ancien nom </th> 
   <th colname="col3" class="entry"> Remarques </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Types de systèmes d’exploitation </td> 
   <td colname="col2"> Nouveau </td> 
   <td colname="col3"> Ajoutée au printemps 2015. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Largeur du navigateur - Regroupement </td> 
   <td colname="col2"> Largeur du navigateur </td> 
   <td colname="col3"> Cette dimension est compatible avec toutes les interfaces et est fractionnée en une liste énumérée de plages au lieu de valeurs d’entiers spécifiques. Si vous devez segmenter des valeurs spécifiques, utilisez la version granulaire de cette dimension dans un segment d’entrepôt de données. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hauteur du navigateur - Regroupement </td> 
   <td colname="col2"> Hauteur du navigateur </td> 
   <td colname="col3"> Cette dimension est compatible avec toutes les interfaces et est fractionnée en une liste énumérée de plages au lieu de valeurs d’entiers spécifiques. Si vous devez segmenter des valeurs spécifiques, utilisez la version granulaire de cette dimension dans un segment d’entrepôt de données. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Largeur du navigateur - Granulaire </td> 
   <td colname="col2"> Largeur du navigateur </td> 
   <td colname="col3"> <p>A été renommée et est à présent compatible avec l’entrepôt de données uniquement. Lors de la définition de segments qui sont compatibles avec toutes les interfaces, utilisez le type énuméré Largeur du navigateur - Regroupement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hauteur du navigateur - Granulaire </td> 
   <td colname="col2"> Hauteur du navigateur </td> 
   <td colname="col3"> <p>A été renommée et est à présent compatible avec l’entrepôt de données uniquement. Lors de la définition de segments qui sont compatibles avec toutes les interfaces, utilisez le type énuméré Hauteur du navigateur - Regroupement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Prise en charge des cookies </td> 
   <td colname="col2"> Cookies </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intensité de couleur </td> 
   <td colname="col2"> Intensité de couleur de l’écran </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> - </td> 
   <td colname="col2"> "App - *" </td> 
   <td colname="col3"> Les préfixes "App -" ont été supprimés de plusieurs types de dimensions. Les données des applications mobiles étant généralement capturées dans une suite de rapports qui ne contient pas de données Web, ces préfixes n’étaient pas nécessaires. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Page d’accès d’origine </td> 
   <td colname="col2"> Page d’accès originale </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Compatible Java </td> 
   <td colname="col2"> Java </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mobile - Longueur max. d’URL de navigateur </td> 
   <td colname="col2"> Longueur d’URL de navigateur mobile </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mobile - Décoration de courrier </td> 
   <td colname="col2"> Prise en charge de Decoration Mail mobile </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Périphérique mobile </td> 
   <td colname="col2"> Nom du périphérique mobile </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mobile - Longueur max. du signet </td> 
   <td colname="col2"> Longueur maxi d’URL en signet pour mobile </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mobile - Longueur max. d’adresse électronique </td> 
   <td colname="col2"> Longueur maxi d’URL de messagerie pour mobile </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Système d’exploitation mobile (obsolète) </td> 
   <td colname="col2"> SE Mobile </td> 
   <td colname="col3"> Utilisez la dimension du système d’exploitation et appliquez à la place une visite depuis les segments de périphériques mobiles. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mobile - Presser pour parler </td> 
   <td colname="col2"> PTT mobile </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vues d’une enquête </td> 
   <td colname="col2"> Total des vues d’une enquête </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Réponses de l’enquête </td> 
   <td colname="col2"> Total des réponses de l’enquête </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profondeur de visite </td> 
   <td colname="col2"> Longueur de chemin </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Code postal </td> 
   <td colname="col2"> Code postal </td> 
   <td colname="col3"> - </td> 
  </tr> 
 </tbody> 
</table>

## Modifications apportées à des dimensions basées sur des chaînes possédant des valeurs connues {#section_1A9EDEE5CBC44B5AA6262560052ABE77}

Les dimensions basées sur des chaînes dotées d’un jeu connu de valeurs ont été modifiées en types énumérés. Lors de la création d’un segment utilisant ces dimensions, la liste est pré-remplie avec toutes les valeurs connues et le seul opérateur pris en charge est « égal à ». Vous pouvez ainsi segmenter rapidement les valeurs exactes que vous recherchiez sans sélectionner des valeurs non voulues lors de l’utilisation d’une correspondance moins stricte.

Les dimensions suivantes ont été modifiées en listes énumérées :

| fabricant du périphérique mobile | longueur d’adresse électronique du périphérique mobile | intensité de couleur |
|---|---|---|
| taille de l’écran du périphérique mobile | numéro du périphérique mobile | résolution de l’écran |
| hauteur d’écran du périphérique mobile | mobile - presser pour parler | module externe |
| prise en charge des cookies sur le périphérique mobile | mobile - décoration de courrier | système d’exploitation |
| prise en charge des images sur le périphérique mobile | services d’informations mobiles | type de référent |
| intensité de couleur du périphérique mobile | type de périphérique mobile | moteur de recherche |
| prise en charge de l’audio sur le périphérique mobile | type de navigateur | état |
| prise en charge de la vidéo sur le périphérique mobile | navigateur | pays géo |
| DRM mobile | type de connexion | région géo |
| protocoles Net mobile | opérateur de téléphonie mobile | ville géo |
| SE Mobile | cookie | DMA géo |
| java VM de mobile | fidélisation des clients | cookie persistant |
| longueur du signet du périphérique mobile | compatible java | recherche payante |
| longueur de l’URL du périphérique mobile | langage |  |

## Modifications apportées à des dimensions basées sur des entiers possédant des valeurs connues {#section_84A8AAD0344148AD9F9211D3EB271903}

Les dimensions basées sur des entiers (la largeur du navigateur par exemple) avec un jeu connu de valeurs ont été fractionnées en plages énumérées afin que vous puissiez définir rapidement les segments pour une plage spécifique. « - Regroupement » est ajouté à ces listes énumérées après le nom de la dimension. L’écran suivant montre comment ces dimensions sont segmentées en utilisant les interfaces du Créateur de segments antérieure et nouvelle :

![](assets/seg_browser_dimension.png)

Les opérateurs « inférieur à », « supérieur à » et similaires sont désormais compatibles avec les segments d’entrepôt de données uniquement. Les segments prévus pour être compatibles avec toutes les interfaces de création de rapports doivent utiliser la version « Regroupement » de la mesure avec l’opérateur « égal à ».
