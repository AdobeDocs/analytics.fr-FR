---
description: Découvrez comment gérer les segments hérités.
title: FAQ sur les segments hérités
feature: Segmentation
exl-id: 316e2a2e-55d3-4c23-9985-9a6d90390e86
source-git-commit: c44bffa45ab8ed29ea28b91b2b3dc51811ab25fe
workflow-type: tm+mt
source-wordcount: '1431'
ht-degree: 57%

---

# Segments hérités

Cet article répond aux questions fréquentes sur les bonnes pratiques de gestion des segments hérités. Les segments hérités sont des segments créés avant 2014.

## Gestion des segments hérités {#legacy}

+++ **Qu’est-il advenu de mes segments existants ?**

Vos segments existants continuent à fonctionner comme avant. Tous les rapports auxquels ces segments sont appliqués continuent à fonctionner correctement.

La plupart des anciens segments prédéfinis et de suite sont migrés en tant que modèles de segment dans le créateur de segments. Les modèles de segment sont utilisés pour créer rapidement des segments personnalisés avec des audiences courantes. Ils ne peuvent pas être directement appliqués à un rapport, mais peuvent être facilement enregistrés dans un segment personnalisé.

Les modèles de segment sont marqués d’une icône spéciale ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) dans le créateur de segments.



+++

+++ **Qu’est-il advenu des rapports planifiés auxquels des segments avaient été appliqués ?**

Les rapports planifiés continuent de fonctionner correctement avec les segments que vous avez définis.

Lorsque vous supprimez un segment, les rapports planifiés et les tableaux de bord auxquels ce segment est appliqué continuent de fonctionner normalement, c’est-à-dire que le segment ou le tableau de bord continue à utiliser le segment supprimé.

Les rapports planifiés ne sont pas mis à jour lorsque vous modifiez un segment portant le même nom. Par exemple, supposons que 2 segments portant le même nom figurent dans différentes suites de rapports :

![](assets/duplicate_seg_names.png)

Vous disposez d’une visualisation qui fait référence au segment de la suite de rapports **[!UICONTROL mainprod]**. Puis, vous supprimez ce segment, car il s’agit d’un doublon. La visualisation continue de s’exécuter, référençant la définition du segment supprimé. Si vous modifiez la définition de segment pour que le segment principal inclue l’île de Catalina et Tijuana, au Mexique, le segment appliqué à la visualisation ne change pas et utilise l’ancienne définition. Pour utiliser la nouvelle définition, mettez à jour la visualisation afin de référencer la nouvelle définition. Si vous ne savez pas si une visualisation, un projet ou un rapport planifié utilise un segment supprimé, modifiez le nom du segment restant pour indiquer si la visualisation utilise le segment restant.

+++

+++ **Qu’advient-il des segments Data Warehouse ?**

Tous les segments Data Warehouse existants fonctionnent toujours dans Data Warehouse. La plupart des segments Data Warehouse fonctionnent également dans d’autres composants, tels qu’Analysis Workspace.

Vous pouvez créer ou modifier de nouveaux segments Data Warehouse depuis le Créateur/Gestionnaire de segments. Le mécanisme de compatibilité des produits du créateur de segments détermine automatiquement si un segment est compatible avec Data Warehouse.

+++

+++ **Qu’advient-il des segments préconfigurés ?**

* **Visites de page unique**
* **Visites depuis des appareils mobiles**
* **Visites depuis la recherche naturelle**
* **Visites d’une recherche payante**
* **Visites avec cookie d’identifiant visiteur**

Ces segments sont migrés sous forme de modèles de segment dans le créateur de segments. Tout rapport auquel ces segments sont appliqués continue à fonctionner correctement.

+++

+++ **Qu’advient-il des segments Experience Cloud (Suite) ?**

* Non-acheteurs
* Acheteurs
* Premières visites
* Visites depuis les sites sociaux
* Visites de plus de 10 minutes*
* Visites avec 5+ visites précédentes*
* Visites depuis Facebook*

La plupart de ces segments (à l’exception de ceux signalés par un astérisque) seront migrés sous forme de modèles de segment dans le créateur de segments. En outre, plusieurs nouveaux modèles de segments ont été ajoutés.

Tout rapport auquel ces segments sont appliqués continue à fonctionner correctement.

+++

+++ **Qu’advient-il des segments d’administration (également appelés « segments globaux ») ?**

Les segments **Admin** sont migrés dans la nouvelle interface de segment et s’affichent en tant que segments partagés avec tout le monde.

Le propriétaire de ces segments est défini sur administrateur avec le compte d’utilisateurs administrateurs le plus ancien. Cependant, tous les administrateurs peuvent supprimer, modifier et partager ces segments.

L’interface de gestion des segments d’Admin Console dans laquelle les administrateurs ont créé et géré ces segments globaux n’est plus disponible. Les administrateurs doivent désormais utiliser le nouveau Créateur de segments pour créer des segments et les partager avec les groupes ou individus appropriés ou à l’échelle de l’entreprise.

Les segments existants qui utilisent une logique modifiée comme décrit dans ce document continuent à fonctionner correctement, bien que les segments doivent être mis à jour avant de pouvoir être enregistrés à nouveau. Par exemple, si vous disposez d’un segment existant dans lequel **[!UICONTROL États américains]** **[!UICONTROL contient]** `New York`, ce segment continue à fonctionner correctement. La prochaine fois que vous modifierez le segment, vous devrez le mettre à jour pour utiliser le type énuméré avec une condition **[!UICONTROL égal]**.

+++

+++ **Que dois-je faire des segments en double portant le même nom mais ayant des définitions différentes ?** Maintenant que les segments fonctionnent dans plusieurs suites de rapports, il est possible que vous disposiez de plusieurs segments portant le même nom. notamment :

* renommer les segments portant le même nom mais ayant des définitions différentes, ou
* supprimer les segments qui ne sont plus utiles.

+++

+++ **Que recommande Adobe pour nettoyer les segments ?**

* Marquez tous les segments avec une balise héritée.
* Examinez les segments à votre disposition.
* Ajoutez les segments à la bibliothèque de segments lorsque cela est possible.
* Approuvez les segments canoniques.
* Balisez les segments conformément aux [bonnes pratiques](/help/components/segmentation/segmentation-workflow/seg-workflow.md).

+++

### Conseils de migration

Les conseils suivants vous aident à migrer les dimensions courantes :

* Ville/région/pays géo : recherchez et sélectionnez des villes, des régions ou des pays spécifiques au lieu d’utiliser une correspondance partielle.
* Navigateurs : utilisez la dimension Types de navigateur pour obtenir tous les navigateurs d’un type, par exemple Google Chrome
* Systèmes d’exploitation : utilisez les dimensions Types de système d’exploitation pour obtenir tous les systèmes d’exploitation d’un type, par exemple, Microsoft Windows.
* Voir la section « Dimensions nouvelles et renommées » (ci-dessous).

## Dimensions nouvelles et renommées {#renamed}

Le tableau suivant contient une liste des dimensions renommées dans le créateur de segments.

| Nouveau nom de la dimension | Ancien nom | Remarques |
|--- |--- |--- |
| Types de systèmes d’exploitation | Nouveau | Ajoutée au printemps 2015. |
| Largeur du navigateur - Regroupement | Largeur du navigateur | Cette dimension est compatible avec toutes les interfaces et est fractionnée en une liste énumérée de plages au lieu de valeurs d’entiers spécifiques. Si vous devez segmenter des valeurs spécifiques, utilisez la version granulaire de cette dimension dans un segment Data Warehouse. |
| Hauteur du navigateur - Regroupement | Hauteur du navigateur | Cette dimension est compatible avec toutes les interfaces et est fractionnée en une liste énumérée de plages au lieu de valeurs d’entiers spécifiques. Si vous devez segmenter des valeurs spécifiques, utilisez la version granulaire de cette dimension dans un segment Data Warehouse. |
| Largeur du navigateur - Granulaire | Largeur du navigateur | Cette dimension a été renommée et est désormais compatible avec Data Warehouse uniquement. Lors de la définition de segments qui sont compatibles avec toutes les interfaces, utilisez le type énuméré Largeur du navigateur - Regroupement. |
| Hauteur du navigateur - Granulaire | Hauteur du navigateur | Cette dimension a été renommée et est désormais compatible avec Data Warehouse uniquement. Lors de la définition de segments qui sont compatibles avec toutes les interfaces, utilisez le type énuméré Hauteur du navigateur - Regroupement. |
| Prise en charge des cookies | Cookies | - |
| Profondeur de couleur | Intensité de couleur de l’écran | - |
| - | &quot;App - *&quot; | Les préfixes « App - » ont été supprimés de plusieurs types de dimensions. Les données des applications mobiles étant généralement capturées dans une suite de rapports qui ne contient pas de données Web, ces préfixes n’étaient pas nécessaires. |
| Page d’accès d’origine | Page d’accès originale | - |
| Compatible Java | Java | - |
| Mobile - Longueur max. d’URL de navigateur | Longueur d’URL de navigateur mobile | - |
| Mobile - Décoration de courrier | Prise en charge de Decoration Mail mobile | - |
| Appareil mobile | Nom de l’appareil mobile | - |
| Mobile - Longueur max. du signet | Longueur maxi d’URL en signet pour mobile | - |
| Mobile - Longueur max. d’adresse e-mail | Longueur maxi d’URL de messagerie pour mobile | - |
| Système d’exploitation mobile (obsolète) | SE Mobile | Utilisez la dimension du système d’exploitation et appliquez à la place une visite depuis les segments d’appareils mobiles. |
| Mobile - Presser pour parler | PTT mobile | - |
| Vues d’une enquête | Total des vues d’une enquête | - |
| Réponses de l’enquête | Total des réponses de l’enquête | - |
| Profondeur de visite | Longueur de chemin | - |
| Code postal | Code postal | - |

{style="table-layout:auto"}

## Modifications apportées aux dimensions basées sur des chaînes dont les valeurs sont connues {#string-based-dims}

Les dimensions basées sur des chaînes qui ont un ensemble de valeurs connu ont été remplacées par des types énumérés. Lors de la création d’un segment à l’aide de ces dimensions, la liste est préremplie avec toutes les valeurs connues et le seul opérateur pris en charge est **[!UICONTROL égal à]**. Cette population de valeurs vous permet de segmenter rapidement les valeurs exactes que vous recherchiez sans sélectionner de valeurs inattendues lors de l’utilisation d’une correspondance moins restrictive.

Les dimensions suivantes ont été modifiées en listes énumérées :

| Nom de la dimension | Nom de la dimension | Nom de la dimension |
| --- | --- | --- |
| fabricant du périphérique mobile | longueur d’adresse e-mail du périphérique mobile | profondeur de couleur |
| taille de l’écran du périphérique mobile | numéro de l’appareil mobile | résolution de l’écran |
| hauteur d’écran du périphérique mobile | mobile - presser pour parler | module externe |
| prise en charge des cookies sur le périphérique mobile | mobile - décoration de courrier | système d’exploitation |
| prise en charge des images sur le périphérique mobile | services d’informations mobiles | type de référent |
| intensité de couleur du périphérique mobile | type d’appareil mobile | moteur de recherche |
| prise en charge de l’audio sur le périphérique mobile | type de navigateur | state |
| prise en charge de la vidéo sur le périphérique mobile | navigateur | pays géo |
| DRM mobile | type de connexion | région géo |
| protocoles Net mobile | opérateur de téléphonie mobile | ville géo |
| SE Mobile | cookie | DMA géo |
| java VM de mobile | fidélisation des clients | cookie persistant |
| longueur du signet du périphérique mobile | compatible java | référencement payant |
| longueur de l’URL du périphérique mobile | langue |  |

## Modifications apportées à des dimensions basées sur des entiers dont les valeurs sont connues {#integer-based-dims}

Les dimensions basées sur des entiers (telles que la largeur du navigateur) avec un jeu de valeurs connu sont divisées en plages énumérées afin que vous puissiez rapidement définir des segments pour une plage spécifique. « - Regroupement » est ajouté à ces listes énumérées après le nom de la dimension. L’écran suivant montre comment ces dimensions sont segmentées en utilisant les interfaces du créateur de segments antérieure et nouvelle :

![](assets/seg_browser_dimension.png)

Les opérateurs « inférieur à », « supérieur à » et similaires sont désormais compatibles avec les segments Data Warehouse uniquement. Les segments censés être compatibles avec toutes les interfaces de création de rapports doivent utiliser la version « regroupée » de la mesure avec l’opérateur **[!UICONTROL égal]**.
