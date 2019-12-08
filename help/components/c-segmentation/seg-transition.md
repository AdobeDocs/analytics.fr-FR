---
description: valeur nulle
keywords: segmentation;segments
title: Questions fréquentes
topic: Segments
uuid: f49dc829-1d53-4183-9add-1aeaa5219d89
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Questions fréquentes

Répond aux questions fréquemment posées sur les fonctionnalités de segmentation, l’accès, les autorisations, les bonnes pratiques et la gestion des segments hérités.

## Fonctionnalités {#section_BD58629D1A9346BF879E229FA6BEC7A2}

* Segmentation dans Analysis Workspace :

   * Vous pouvez [comparer des segments](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/segment-comparison.html).
   * Utilisez les [segments comme dimensions](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/segments_as_dimensions.html) dans une comparaison.
   * Utilisez des segments dans [l’analyse des abandons](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/graphics/compare-segments-fallout.html).

* Vous pouvez [appliquer plusieurs segments à un rapport ou à un projet](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md).
* Les segments fonctionnent dans toutes les suites de rapports.
* Le [Créateur de segments](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md) simplifie la création de segments.
* Le [gestionnaire de segments](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md) permet de configurer des [processus](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md) pour le partage, le marquage, la vérification et l’approbation des segments.

* Vous pouvez [marquer les segments](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md) pour les organiser et les rechercher ultérieurement au lieu d’utiliser des dossiers. Par le passé, vous utilisiez des dossiers (dans les [!DNL Ad Hoc Analysis]) pour organiser vos segments.

* Vous pouvez créer des [segments séquentiels](/help/components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md) en dehors des Ad Hoc Analysis.
* Le conteneur de pages vues a été renommé « conteneur d’accès » afin d’indiquer que ce conteneur segmente tous les types de données et pas uniquement les pages vues. Par exemple, les appels de suivi des liens et les appels trackAction provenant des Kits de développement logiciel (SDK) mobiles sont tous inclus ou exclus par le conteneur d’accès. Notez qu’aucune modification n’a été apportée au fonctionnement de ce conteneur, il a simplement été renommé.

Voir l’article [Amélioration de la segmentation dans Adobe Analytics](https://blogs.adobe.com/digitalmarketing/analytics/improving-segmentation-adobe-analytics/) sur le blog de Digital Marketing pour en savoir plus.

## Accès aux outils de segmentation {#section_088AD0E4E21943DFA8CF7206AEC485DD}

**Comment puis-je accéder au Créateur de segments ?**

Accédez au Créateur de segments en procédant comme suit :

* Affichez un rapport existant, puis cliquez sur l’icône Segments ![](assets/segment_icon.png) dans le volet de navigation de gauche. Dans le rail du segment qui s’affiche, cliquez ensuite sur **[!UICONTROL Ajouter]**, ou

* Dans la partie supérieure du Gestionnaire de segments, cliquez sur **[!UICONTROL + Ajouter]**.  ![](assets/add_button.png)

   ou

* cliquez sur le titre d’un segment existant dans le Gestionnaire de segments afin de le modifier dans le Créateur de segments.

**Comment puis-je accéder au Gestionnaire de segments ?**

Accédez au Gestionnaire de segments en procédant comme suit :

* Sélectionnez **[!UICONTROL Analytics]** &gt; **[!UICONTROL Composants]** dans le volet de navigation supérieur. Cliquez ensuite sur **[!UICONTROL Segments]**, ou

* Affichez un rapport existant, puis cliquez sur l’icône Segments ![](assets/segment_icon.png) dans le volet de navigation de gauche. Cliquez ensuite sur **[!UICONTROL Gérer]**, ou

* appuyez sur la barre oblique « / » n’importe où dans l’interface et recherchez le Gestionnaire de segments.

**Vers quel emplacement le menu déroulant des segments existants a-t-il été déplacé ?**

Le menu déroulant des segments dans les Reports &amp; Analytics a été remplacé par une interface du [Créateur de segments](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md) bien plus riche en fonctionnalités qui permet de créer des segments « universels » utilisables dans les suites de rapports et dans les solutions d’Adobe Analytics. Pour afficher la liste des segments existants, cliquez sur l’icône Segments ![](assets/segment_icon.png)

dans le volet de navigation de gauche pour ainsi afficher le rail de segments.

**Vers quel emplacement le menu déroulant des suites de rapports existantes a-t-il été déplacé ?**

Le menu déroulant des suites de rapports a été déplacé en regard du sélecteur de dates dans le coin supérieur droit de chaque rapport ou tableau de bord.

![](assets/report_suite_selector.png)

## Autorisations {#section_648DFA3A882146C485A84ED014EEC707}

**Quels droits et privilèges dois-je posséder pour utiliser, créer et gérer des segments ?**

Par défaut, tous les utilisateurs sont autorisés à créer et à modifier des segments personnels. Toutefois, les administrateurs peuvent distribuer des [autorisations de créer des segments](https://marketing.adobe.com/resources/help/en_US/reference/groups.html) aux utilisateurs et en affecter à des groupes spécifiques. Ces segments peuvent être partagés directement avec tout autre utilisateur d’Analytics.

Les administrateurs peuvent modifier n’importe quel segment et partager les segments avec des groupes et toute personne de l’entreprise. [Plus...](/help/components/c-segmentation/seg-reference/seg-rights.md)

**Puis-je consulter tous les segments de mon entreprise ?**

Oui, les administrateurs peuvent voir tous les segments dans les interfaces utilisateur d’[!DNL Analysis Workspace] et d’[!DNL Reports & Analytics].

Les analyses ad hoc et le Report Builder affichent les segments que vous possédez et les segments qui sont partagés avec vous.

**Puis-je gérer tous les segments Analytics dans le Gestionnaire de segments ?**

Oui, vous pouvez gérer tous les segments dans le Gestionnaire de segments dans Analysis Workspace, dans les Reports &amp; Analytics et dans les analyses ad hoc. Le Gestionnaire de segments affiche des segments que le propriétaire (utilisateur qui a créé le segment), les utilisateurs partagés et les administrateurs peuvent consulter. Le sélecteur de segments affiche les segments possédés par l’utilisateur et partagés avec ce dernier.

Les administrateurs peuvent voir tous les segments dans les interfaces utilisateur d’Analysis Workspace et d’[!DNL Reports & Analytics].

Les analyses ad hoc et le Créateur de rapports affichent uniquement les segments que vous avez créés ou les segments qui ont été partagés avec vous.

**Pourquoi ne puis-je pas supprimer ce segment ?**

Si le segment a été [publié sur Experience Cloud](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md), vous ne pouvez pas le supprimer ni le modifier. Vous pouvez toutefois le copier et modifier la version copiée.

## Bonnes pratiques {#section_E2C3A1B4B4274D1B86CAA9C0359D049C}

**Que dois-je faire des segments en double portant le même nom mais ayant des définitions différentes ?** Maintenant que les segments fonctionnent dans plusieurs suites de rapports, il est possible que vous disposiez de plusieurs segments portant le même nom. Il est conseillé d’effectuer les opérations suivantes :

* renommer les segments portant le même nom mais ayant des définitions différentes, ou
* supprimer les segments qui ne sont plus utiles.

**Quelles sont les recommandations d’Adobe au sujet du nettoyage des segments ?**

* Marquez tous les segments avec une balise héritée.
* Examinez les segments à votre disposition.
* Ajoutez les segments à la bibliothèque de segments lorsque cela est possible.
* Approuvez les segments canoniques.
* Marquez les segments en fonction des [bonnes pratiques](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md).

## Gestion des segments existants {#section_76CF47142D1A4FB6A0718AD9073049FE}

**Qu’est-il advenu de mes segments existants ?**

Vos segments existants continueront à fonctionner comme auparavant. Tout rapport auquel ces segments sont appliqués continuera à fonctionner correctement. [Plus...](/help/components/c-segmentation/seg-transition.md)

La plupart des anciens segments prédéfinis et de suite seront migrés sous la forme de modèles de segments dans le Créateur de segments. Les modèles de segments sont utilisés pour créer rapidement des segments personnalisés avec des audiences courantes. Ils ne peuvent pas être directement appliqués à un rapport, mais peuvent être facilement enregistrés dans un segment personnalisé.

Les modèles de segments sont marqués par une icône spéciale dans le Créateur de segments :

![](assets/seg_templates.png)

**Qu’est-il advenu de mes dossiers de segments existants ?**

À la place des dossiers (analyses ad hoc), le Gestionnaire de segments utilise des balises. Les noms de dossiers sont automatiquement convertis en balises et ces balises sont appliquées aux segments respectifs.

**Qu’est-il advenu des rapports planifiés auxquels des segments avaient été appliqués ?**

Les rapports planifiés continuent de fonctionner correctement avec les segments que vous avez définis.

Lorsque vous supprimez un segment, les rapports planifiés et les tableaux de bord auxquels ce segment est appliqué continuent de fonctionner normalement, c’est-à-dire que le segment ou le tableau de bord continue à utiliser le segment supprimé.

Les rapports planifiés ne sont pas mis à jour lorsque vous modifiez un segment portant le même nom. Par exemple, supposons que 2 segments portant le même nom figurent dans différentes suites de rapports :

![](assets/duplicate_seg_names.png)

Vous êtes doté d’un signet qui référence le segment pour la suite de rapports mainprod. Puis, vous supprimez ce segment, car il s’agit d’un doublon. Le signet continue à fonctionner, référençant la définition du segment supprimé. Si vous modifiez la définition de segment du segment maindev pour inclure l’île Catalina et Tijuana au Mexique, le segment appliqué au signet ne change pas. Il utilise l’ancienne définition. Pour corriger ce problème, mettez à jour le signet qui référence la nouvelle définition. Si vous n’êtes pas certain qu’un signet, tableau de bord ou rapport planifié utilise un segment supprimé, vous pouvez modifier le nom du segment restant afin qu’il soit plus clair que le signet utilise le segment restant.

**Qu’advient-il des segments Data Warehouse ?**

Tous les segments Data Warehouse existants fonctionnent toujours dans l’entrepôt de données. La plupart des segments de Data Warehouse fonctionneront également dans d’autres composants tels qu’Analysis Workspace, Les Ad Hoc Analysis et les Reports &amp; Analytics.

Vous pouvez créer ou modifier de nouveaux segments Data Warehouse depuis le Créateur/Gestionnaire de segments. Le mécanisme de compatibilité des produits du Créateur de segments détermine automatiquement si un segment est compatible avec Data Warehouse.

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

**Qu’advient-il des segments Experience Cloud (Suite) ?**

* Non-acheteurs
* Acheteurs
* Premières visites
* Visites depuis les sites sociaux
* Visites de plus de 10 minutes*
* Visites avec 5+ visites précédentes*
* Visites depuis Facebook*

La plupart de ces segments (sauf ceux marqués d’un astérisque *) seront migrés en tant que modèles de segments dans le Créateur de segments. En outre, plusieurs nouveaux modèles de segments ont été ajoutés.

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

* Ville/région/pays géo : recherchez et sélectionnez des villes, des régions ou des pays spécifiques au lieu d’utiliser une correspondance partielle.
* Navigateurs : utilisez la dimension Types de navigateur afin de regrouper tous les navigateurs dans un type, par exemple Google Chrome.
* Systèmes d’exploitation : utilisez les dimensions des types de système d’exploitation pour regrouper tous les systèmes d’exploitation dans un type, par exemple Microsoft Windows.

* [Dimensions nouvelles et renommées](/help/components/c-segmentation/seg-transition.md#section_73CF121B64A24DEF8E6499F3167BF742)
* [Modifications apportées aux conteneurs](/help/components/c-segmentation/seg-transition.md#section_1A9EDEE5CBC44B5AA6262560052ABE77)
* [Modifications apportées à Inférieur à et à Supérieur à](/help/components/c-segmentation/seg-transition.md#section_84A8AAD0344148AD9F9211D3EB271903)

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
   <td colname="col1"> Profondeur de couleur </td> 
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
| prise en charge de l’audio sur le périphérique mobile | type de navigateur | state |
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

Les opérateurs « inférieur à », « supérieur à » et similaires sont désormais compatibles avec les segments Data Warehouse uniquement. Les segments prévus pour être compatibles avec toutes les interfaces de création de rapports doivent utiliser la version « Regroupement » de la mesure avec l’opérateur « égal à ».
