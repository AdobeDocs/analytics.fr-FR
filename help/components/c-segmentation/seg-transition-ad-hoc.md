---
description: Si vous êtes habitué à travailler avec le Créateur de segments dans les analyses ad hoc, ce forum aux questions (FAQ) explique ce qu’il advient des segments et dossiers existants ainsi que les actions que vous devez entreprendre.
keywords: segmentation;segments
title: Guide de transition relatif aux Ad Hoc Analysis
topic: Segments
uuid: d409d71a-f8d9-42a2-add2-37d426cd40d1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Guide de transition relatif aux Ad Hoc Analysis

Si vous êtes habitué à travailler avec le Créateur de segments dans les analyses ad hoc, ce forum aux questions (FAQ) explique ce qu’il advient des segments et dossiers existants ainsi que les actions que vous devez entreprendre.

## Fonctionnalités {#section_BD58629D1A9346BF879E229FA6BEC7A2}

* Les segments fonctionnent dans toutes les suites de rapports. Auparavant, ils étaient propres à une suite de rapports donnée.
* Les analyses ad hoc comprennent des mises à jour du Créateur de segments ainsi qu’une mise à jour complète du Gestionnaire de segments.
* Vous pouvez désormais marquer les segments pour les organiser et les rechercher ultérieurement au lieu d’utiliser des dossiers.  Par le passé, vous utilisiez des dossiers dans les [!DNL Ad Hoc Analysis] pour organiser vos segments.

## Qu’est-il advenu de mes segments existants ? {#section_76CF47142D1A4FB6A0718AD9073049FE}

Vos segments existants continueront à fonctionner comme auparavant. Tout rapport auquel ces segments sont appliqués continuera à fonctionner correctement.

La plupart des segments prédéfinis et de suite précédents seront migrés sous forme de modèles de segment dans le créateur de segments. Les modèles de segments sont utilisés pour créer rapidement des segments personnalisés avec des audiences courantes. Ils ne peuvent pas être directement appliqués à un rapport, mais peuvent être facilement enregistrés dans un segment personnalisé.

Les modèles de segments sont marqués par une icône spéciale dans le Créateur de segments.

## Qu’est-il advenu de mes dossiers de segments existants ? {#section_FB04DCF775694E69B761DCA53F301C30}

Le gestionnaire de segments utilise des balises à la place de dossiers d’analyses ad hoc. Les noms de dossiers sont automatiquement convertis en balises et ces balises sont appliquées aux segments respectifs.

## Qu’est-il advenu des rapports planifiés auxquels des segments avaient été appliqués ? {#section_81D1B215533C46E99E17BAE7A3376FDF}

Les rapports planifiés continuent de fonctionner correctement avec les segments que vous avez définis.

Lorsque vous supprimez un segment, les rapports planifiés et les tableaux de bord auxquels ce segment est appliqué continuent de fonctionner normalement, c’est-à-dire que le segment ou le tableau de bord continue à utiliser le segment supprimé.

## Qu’est-ce qu’un conteneur d’accès ? Est-ce différent d’un conteneur Page vue ? {#section_65BBE60A836C4001938830DDA15DC256}

Le conteneur de pages vues a été renommé « conteneur d’accès » afin d’indiquer que ce conteneur segmente tous les types de données et pas uniquement les pages vues. Par exemple, les appels de suivi des liens et les appels trackAction provenant des Kits de développement logiciel (SDK) mobiles sont tous inclus ou exclus par le conteneur d’accès.

Notez qu’aucune modification n’a été apportée au fonctionnement de ce conteneur, il a simplement été renommé.

## Quels droits et privilèges dois-je posséder pour utiliser, créer et gérer des segments ? {#section_648DFA3A882146C485A84ED014EEC707}

Tous les utilisateurs sont autorisés à créer et à modifier des segments personnels. Ces segments peuvent être partagés directement avec tout autre utilisateur d’Analytics. Les utilisateurs des analyses ad hoc peuvent voir les segments qu’ils ont créés et ceux qui ont été partagés directement avec eux.

Dans la console Web de segmentation unifiée, les administrateurs peuvent modifier chaque segment et partager les segments avec des groupes et avec chaque membre de l’organisation.

## Puis-je consulter tous les segments de mon entreprise ? {#section_AC2D328C7410419E80C7C17971CD95B3}

Tous les segments d’analyses ad hoc que vous détenez ou qui ont été partagés avec vous s’affichent.

## Puis-je gérer tous les segments Analytics dans le Gestionnaire de segments ? {#section_AF5EDD72C74A4739BD40C4AF125CE489}

Les analyses ad hoc affichent uniquement les segments que vous avez conçus ou ceux qui ont été partagés avec vous. Pour les analyses ad hoc uniquement, vous pouvez utiliser le gestionnaire de segments (Organiser les segments) pour gérer les segments d’analyses ad hoc. Utilisez le gestionnaire de segments dans la console de segmentation unifiée pour gérer tous les segments d’Analytics.

## Que dois-je faire des segments en double portant le même nom mais ayant des définitions différentes ? {#section_E2C3A1B4B4274D1B86CAA9C0359D049C}

Maintenant que les segments fonctionnent dans plusieurs suites de rapports, il est possible que vous disposiez de plusieurs segments portant le même nom. Il est conseillé d’effectuer les opérations suivantes :

* renommer les segments portant le même nom mais ayant des définitions différentes, ou
* supprimer les segments qui ne sont plus utiles.

## Quels sont les conseils d’Adobe pour nettoyer les segments ? {#section_3AC2D265F9084557A24C6FB39DC6EE49}

* Marquez tous les segments avec une balise héritée.
* Examinez les segments à votre disposition.
* Ajoutez les segments à la bibliothèque de segments lorsque cela est possible.
* Approuvez les segments canoniques.

## Pourquoi ne puis-je pas supprimer ce segment ? {#section_0FEB6711031A4ABCA915CDA745ECF38D}

Si le segment a été publié sur Experience Cloud, vous ne pouvez pas le supprimer ni le modifier. Vous pouvez toutefois le copier et modifier la version copiée.

## Informations supplémentaires sur vos segments existants {#section_83ACAB256F394DCD8B424D8920BDD853}

<table id="table_0AE814A64D2A48ABB28402C4303F420E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Catégorie de segment </th> 
   <th colname="col2" class="entry"> Qu’est-il advenu de ces segments ? </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Segments favoris dans les analyses ad hoc </td> 
   <td colname="col2">Ces segments des Ad Hoc Analysis s’affichent sous forme de segments standard dans Adobe Analytics. <p>Ils ne doivent pas être confondus avec la fonctionnalité Favoris du Gestionnaire de segments qui permet de marquer les segments comme favoris. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Segments préconfigurés dans les Ad Hoc Analysis : 
    <ul id="ul_BBF3C3F4D41A40AF98DA9DA6D299AD03"> 
     <li id="li_B65A004BDF8743FDABCD3332AEB8A010">Visites sur une seule page </li> 
     <li id="li_908CF5F964154C9D9EBBAC2A900DCB49">Visites depuis des périphériques mobiles </li> 
     <li id="li_4A715F49AA374463B501D731261A3A4C">Visites depuis la recherche naturelle </li> 
     <li id="li_67CE51237EC34FD4B33942BA14584EBF">Visites d’une recherche payante </li> 
     <li id="li_C3820743178A4E9F9E5E5B5C47401DF2">Visites avec cookie d’identifiant visiteur </li> 
    </ul> </td> 
   <td colname="col2"> <p>Ces segments seront migrés en tant que modèles de segments dans le Créateur de segments. </p> <p>Les rapports existants auxquels sont appliqués ces segments continueront de fonctionner correctement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Segments Experience Cloud (Suite) : 
    <ul id="ul_6968AFF6DEDA4BC8A7885B07CC1F57DF"> 
     <li id="li_073D9496F0C64AEB855855D01E65C1BA">Non-acheteurs </li> 
     <li id="li_8958FD4272A14E16A9AA08216E8BC573">Acheteurs </li> 
     <li id="li_1436D7C9651D4AC38E10662DEDDD2B95">Premières visites </li> 
     <li id="li_69F42B4F6107407792B0014804A8AF7B">Visites depuis les sites sociaux </li> 
     <li id="li_29CA111186BE475C943E9F8450BDE8C8">Visites de plus de 10 minutes* </li> 
     <li id="li_1FEF207959DC4D2E9FC925DD43177AA0">Visites avec 5+ visites précédentes* </li> 
     <li id="li_219AB1D4FD7E469C9076A23D2CCC7C2C">Visites depuis Facebook* </li> 
    </ul> </td> 
   <td colname="col2"> <p> La plupart de ces segments (sauf ceux marqués d’un astérisque *) seront migrés en tant que modèles de segments dans le Créateur de segments. En outre, plusieurs nouveaux modèles de segments ont été ajoutés. </p> <p>Les rapports existants auxquels sont appliqués ces segments continueront de fonctionner correctement. </p> </td> 
  </tr> 
 </tbody> 
</table>

