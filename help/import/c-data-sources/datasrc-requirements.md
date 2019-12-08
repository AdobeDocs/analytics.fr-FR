---
description: Informations sur les conditions requises pour votre suite de rapports avant d’utiliser les sources de données.
subtopic: Data sources
title: Conditions requises et limites de transfert
topic: Developer and implementation
uuid: d79fca77-fa0e-4171-b978-cdee5c67d9df
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Conditions requises et limites de transfert

Informations sur les conditions requises pour votre suite de rapports avant d’utiliser les sources de données.

Les sections suivantes répertorient les contraintes qui s’appliquent aux sources de données et aux données importées dans les rapports et analyses marketing.

* [Limites de taille](/help/import/c-data-sources/datasrc-requirements.md#section_77B06D82CB374FFABD39F7D9A49D8E18)
* [Dates](/help/import/c-data-sources/datasrc-requirements.md#section_2B8E69BA1E0B4DEAB4E2034C2B9E16C2)
* [Général](/help/import/c-data-sources/datasrc-requirements.md#section_1CD337F660484ABDB7D8CAE96FF46ACF)
* [Prise en charge multioctet](/help/import/c-data-sources/datasrc-requirements.md#section_96C8D26B21184C3E839865DB6F23EA22)
* [Transfert de fichiers journaux Web](/help/import/c-data-sources/datasrc-requirements.md#section_DD736FC971FE45C89AB310BEDC1FE707)

## Limites de taille {#section_77B06D82CB374FFABD39F7D9A49D8E18}

* Chaque compte FTP est limité à un total de 50 Mo de données pour tous les fichiers. Le traitement s’interrompt au-delà de 50 Mo et ne reprend qu’une fois que le total est inférieur à 50 Mo.

## Dates {#section_2B8E69BA1E0B4DEAB4E2034C2B9E16C2}

* Chaque jour calendaire, vous pouvez transférer des données pour 90 dates uniques. Au-delà de cette limite, le chargement échoue et un message d’erreur s’affiche, indiquant que le nombre maximum de jours uniques a été dépassé.
* Seules les données avec des dates en cours ou passées peuvent être importées. Ne tentez pas d’utiliser des dates futures dans vos données de sources de données.
* Pour chaque ligne, une date doit être spécifiée afin d’avoir accès aux fonctionnalités de représentation des rapports. Si une ligne ne comprend pas de date, la fonctionnalité Sources de données génère une erreur et rejette le fichier. Le format de date et d’heure varie en fonction du type de source de données :

   * **Sources** de données à traitement complet :Utilisez le format de date ISO 8601 de `YYYY-MM-DDThh:mm:ss±UTC_offset` (par exemple, `2013-09-01T12:00:00-07:00`) ou le format de temps Unix (nombre de secondes écoulées depuis le 1er janvier 1970).

   * **Sources** de données standard et d’intégration : Utilisez le format de date suivant : `MM/DD/YYYY/HH/mm/SS` (par exemple, `01/01/2013/06/00/00`)

## Général {#section_1CD337F660484ABDB7D8CAE96FF46ACF}

* Lorsque vous transférez un fichier de source de données, la fonctionnalité Sources de données exécute une validation de données de base afin de s’assurer que le fichier ne contient aucune erreur de mise en forme. En cas d’erreur, un message d’avertissement est envoyé et le traitement s’arrête.
* Les champs de données ne peuvent pas contenir de points-virgules. La fonctionnalité Sources de données ignore les enregistrements qui contiennent un point-virgule.
* Les données issues du journal Web, du trafic et de certains regroupements de sources de données génériques ne sont pas disponibles dans entrepôt de données ni dans Discover. Pour plus d’informations, voir Types [de données et Catégories](/help/import/c-data-sources/c-datasrc-types/datasrc-categories.md).
* Les sources de données ne prennent pas en charge les événements sérialisés.

## Prise en charge multioctet {#section_96C8D26B21184C3E839865DB6F23EA22}

La fonctionnalité Sources de données prend en charge le codage multioctet. Elle tente de détecter le format du fichier de source de données entrant, puis, si nécessaire, le convertit dans un format pris en charge. Le tableau suivant répertorie les formats de caractères courants et leur statut de prise en charge.

<table id="table_F9E685D7EEAB49A9ABAD622AE630EC21"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Format de caractère </th> 
   <th colname="col2" class="entry"> Support technique </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> UTF-8 </td> 
   <td colname="col2"> <p>Pris en charge. La suite de rapports utilisée avec la fonctionnalité Sources de données doit prendre en charge les caractères multioctets. </p> <p>Voir <a href="https://marketing.adobe.com/resources/help/en_US/reference/new_report_suite.html"  >Nouvelle suite de rapports</a> dans l’Aide. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-8 avec marque d’ordre d’octet (EF BB BF) </td> 
   <td colname="col2"> <p>Pris en charge. Même si de nombreuses applications Windows utilisent ce format, il ne s’agit pas d’un format standard. </p> <p>Par exemple, WordPad enregistre dans ce format lorsque vous sélectionnez « UTF-8 ». </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ISO-8859-1 (ou Latin-1 ou Windows-1252) </td> 
   <td colname="col2"> Pris en charge. Microsoft Excel enregistre dans ce format lorsque vous sélectionnez une exportation séparée par tabulations. La suite de rapports doit utiliser le paramètre régional ISO-8859-1. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-16 Little-endian, avec marque d’ordre d’octet (FF FE) </td> 
   <td colname="col2"> Converti en ISO-8859-1 ou UTF-8, comme déterminé par votre configuration de suite de rapports. Microsoft Excel enregistre dans ce format lorsque vous sélectionnez une exportation unicode. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-16 Big-endian, avec marque d’ordre d’octet (EF FF) </td> 
   <td colname="col2"> Converti en ISO-8859-1 ou UTF-8, comme déterminé par votre configuration de suite de rapports. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-16 sans marque d’ordre d’octet </td> 
   <td colname="col2"> Non pris en charge. </td> 
  </tr> 
 </tbody> 
</table>

Si vous envoyez un fichier UTF-8 ou ISO-8859-1 et que votre suite de rapports n’est pas configurée pour le prendre en charge, l’un des événements suivants se produit :

* L’erreur est détectée durant la conversion, auquel cas vous recevez un message du type « Caractère incorrect détecté dans le fichier à la position 18 lors de la conversion d’UTF-8 à ISO-8859-1 ».
* Le fichier est traité sans erreur, mais des données altérées s’affichent dans le rapport.

## Transfert de fichiers journaux Web {#section_DD736FC971FE45C89AB310BEDC1FE707}

* Les rapports de trafic, tels que les pages vues, constituent les rapports les plus utiles pour l’affichage de données de journaux Web.
* Les noms de page s’affichent sous forme d’URL complète, incluant la chaîne de requête.
* Chaque requête de fichier s’affiche sous forme d’une page distincte, comprenant les feuilles de style et les fichiers image.
* Si vous annexez des informations à l’URL, les fichiers peuvent être enregistrés sous forme de pages distinctes. Par exemple, les rapports marketing enregistrent les URL suivantes comme deux pages distinctes :

[!DNL /jokes/misc/snail_joke.html?userid=12345]

[!DNL /jokes/misc/snail_joke.html?userid=98765]
