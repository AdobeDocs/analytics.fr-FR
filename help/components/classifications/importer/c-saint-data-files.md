---
description: L’importateur vous permet de télécharger en vrac des données de classification dans des rapports d’analyse sous la forme d’un fichier. Pour que les chargements de données s’effectuent correctement, un format de fichier spécifique est requis pour l’importation.
title: Fichiers de données de classification
feature: Classifications
exl-id: aa919a03-d461-4d12-adc1-6441fb467e63
source-git-commit: 04c626b1159be3e61569e462bf9d12957bd2a333
workflow-type: tm+mt
source-wordcount: '1032'
ht-degree: 90%

---

# Fichiers de données de classification (hérités)

L’importateur vous permet de télécharger en vrac des données de classification dans des rapports d’analyse sous la forme d’un fichier. Pour que les chargements de données s’effectuent correctement, un format de fichier spécifique est requis pour l’importation.

Pour vous aider à créer des fichiers de données valides, vous pouvez télécharger un fichier de modèle qui fournit une structure de fichier dans laquelle vous pouvez coller les données de classification. Pour plus d’informations, reportez-vous à la section [Télécharger le modèle de classifications](/help/components/classifications/importer/c-download-saint-data.md).

Reportez-vous à la section [Structure générale d’un fichier](/help/components/classifications/importer/c-saint-data-files.md) pour en savoir plus sur les limites de caractères dans les classifications.

## Structure générale d’un fichier

La figure suivante illustre un exemple de fichier de données :

![](assets/completed-saint-file.png)

Un fichier de données doit respecter les règles de structure suivantes :

* Les classifications ne peuvent pas contenir une valeur nulle (zéro).
* Adobe recommande que vous limitiez à 30 le nombre de colonnes d’importation et d’exportation.
* Les fichiers téléchargés doivent utiliser UTF-8 sans codage des caractères de nomenclature.
* Des caractères spéciaux, tels que des tabulations, des sauts de lignes et des guillemets peuvent être incorporés dans une cellule sous réserve que le format de fichier v2.1 soit indiqué et que la cellule contienne bien un [caractère d’échappement](/help/components/classifications/importer/importer-faq.md). Les caractères spéciaux incluent :

  ```text
  \t     tab character 
  \r     form feed character 
  \n    newline character 
  "       double quote
  ```

  La virgule n’est pas un caractère spécial.

* Les noms de classification ne peuvent pas contenir de signe d’insertion (^), car ce caractère est utilisé pour indiquer une sous-classification.
* Faites attention lorsque vous utilisez un trait d’union. Par exemple, si vous utilisez un trait d’union (-) dans un terme de réseau social, Social le considère comme un opérateur [!DNL Not] (signe moins). Si, par exemple, vous spécifiez le terme *`fragrance-free`* à l’aide de l’importation, Social reconnaît le terme comme étant fragrance *`minus`* free et rassemble les messages qui mentionnent *`fragrance`*, mais pas *`free`*.
* Des limites de caractères sont appliquées afin de classer les données de rapport. Par exemple, si vous téléchargez un fichier texte de classification pour des produits ( *`s.products`*) dont les noms comportent plus de 100 caractères (octets), les produits en question ne sont pas affichés dans les rapports. Les codes de suivi et toutes les variables de conversions (eVars) personnalisées autorisent 255 octets. Cette politique s’étend également aux valeurs des colonnes de classification et de sous-classification, qui sont soumises à la même limite de 255 octets.
* Il doit s’agir d’un fichier délimité par des tabulations (créez le fichier de modèle dans tout tableur ou éditeur de texte).
* Il doit être doté de l’extension de fichier `.tab` ou `.txt`.
* Le signe dièse (#) identifie la ligne comme commentaire utilisateur. Adobe ignore toutes les lignes commençant par #.
* Un signe de deux livres suivi de SC (`## SC`) identifie la ligne en tant que commentaire d’en-tête de prétraitement utilisé par le reporting. Ne supprimez pas ces lignes.
* Les exportations de classification peuvent comporter des clés en double en raison des caractères de saut de page de la clé. Dans une exportation FTP ou de navigateur, ce problème peut être résolu en activant la création de guillemets pour le compte FTP. Cette activation place des guillemets entourant chaque clé comportant des caractères de saut de page.
* La cellule C1 de la première ligne du fichier d’importation comporte un identifiant de version qui détermine la façon dont les classifications traitent l’utilisation des guillemets dans le reste du fichier.

   * Le format v2.0 ignore les guillemets et présume qu’ils font tous partie des clés et valeurs indiquées. Étudions par exemple cette valeur : &quot;C’est &quot;&quot;une valeur&quot;&quot;&quot;. Le format v2.0 interprète cette valeur littéralement : &quot;C’est &quot;&quot;une valeur&quot;&quot;&quot;.
   * Le format v2.1 indique aux classifications de présumer que les guillemets font partie du formatage des fichiers utilisé dans les fichiers Excel. De ce fait, le format v2.1 formate l’exemple ci-dessus ainsi : C’est &quot;une valeur&quot;.
   * Des problèmes peuvent survenir lorsque le format v2.1 est indiqué dans le fichier alors que c’est le format v2.0 qui est voulu - à savoir lorsque des guillemets sont utilisés de façon non autorisée au format Excel. Par exemple, si vous avez la valeur : &quot;VP NO REPS&quot; S/l Dress w/ Overlay. Avec le format v2.1, ce formatage est incorrect (la valeur devrait être entourée de guillemets ouvrant et fermant et les guillemets qui font partie de la valeur réelle devraient être codés par échappement par des guillemets) et les classifications ne fonctionneront pas au-delà de ce point.
   * Assurez-vous de procéder à l’une des opérations suivantes : modifiez le format du fichier sur v2.0 en modifiant l’en-tête (cellule C1) dans les fichiers que vous téléchargez OU implémentez correctement les guillemets Excel dans l’ensemble des fichiers.

* La première ligne (qui ne soit pas un commentaire) du fichier de données contient les en-têtes de colonne utilisés pour identifier les données de classification contenues dans cette colonne. L’importateur nécessite un format spécifique pour les en-têtes de colonne. Pour en savoir plus, reportez-vous à la section [Format d’en-tête de colonne](/help/components/classifications/importer/c-saint-data-files.md).
* Immédiatement sous la ligne d’en-tête d’un fichier de données se trouvent les lignes de données. Chacune d’elles doit contenir un champ de données pour chaque en-tête de colonne.
* Le fichier de données prend en charge les codes de contrôle ci-dessous. Adobe les utilise pour fournir la structure au fichier et importer correctement les données de classification :

<table id="table_0548F2E58B6644208147434EB9B3C21B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> CODE DE CONTRÔLE </th> 
   <th colname="col2" class="entry"> DESCRIPTION </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>&lt;Nouvelle ligne&gt; </p> </td> 
   <td colname="col2"> <p>Un caractère de nouvelle ligne est le seul délimiteur pris en charge entre les lignes de données/enregistrements dans le fichier de données. En règle générale, il suffit d’insérer spécifiquement ces caractères lors de l’écriture d’un programme pour générer automatiquement des fichiers de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~autogen~ </p> </td> 
   <td colname="col2"> <p>Ce code demande à Adobe de générer automatiquement un ID unique pour cet élément. </p> <p>Dans le cadre d’une campagne, cette valeur de contrôle demande à Adobe d’attribuer un identificateur à chaque élément créatif. Voir <a href="/help/components/classifications/importer/c-saint-data-files.md"  >Clé</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~period~ </p> </td> 
   <td colname="col2"> <p>Ce code indique que la colonne de données représente la période associée à l’élément. Voir <a href="/help/components/classifications/importer/c-saint-data-files.md"  >Date</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Champ vide </p> </td> 
   <td colname="col2"> <p>Ce code représente une valeur NULL pour le champ actif. Utilisez-le si une colonne de données spécifique ne s’applique pas à l’enregistrement actif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modificateurs PER </p> </td> 
   <td colname="col2"> <p>Ce code indique que la colonne de données représente des champs de <span class="wintitle">modificateur PER</span>. Reportez-vous à la section <a href="/help/components/classifications/importer/c-saint-data-files.md"  >En-têtes de modificateur PER </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Format d’un en-tête de colonne

>[!NOTE]
>
>Adobe recommande que vous limitiez à 30 le nombre de colonnes d’importation et d’exportation.

Les fichiers de classification prennent en charge les en-têtes de colonne suivants :

### Clé

Chaque valeur doit être unique dans l’ensemble du système. La valeur de ce champ correspond à une valeur attribuée à la variable [!DNL Analytics] dans la balise [!DNL JavaScript] du site web. Les données de cette colonne peuvent inclure ~autogen~ ou tout autre code de suivi unique.

### En-tête de colonne de classification

>[!NOTE]
>
>Les valeurs de l’en-tête de colonne de [!UICONTROL classification] doivent respecter la convention de nommage de la classification, sinon l’import échoue. Par exemple, si l’administrateur ou l’administratrice remplace [!UICONTROL Campagnes] par [!UICONTROL Noms de campagnes internes] dans le [!UICONTROL Gestionnaire de configuration de campagne], l’en-tête de colonne doit aussi être remplacé. « Clé » est une valeur de classification réservée (en-tête). Les nouvelles classifications nommées « Clé » ne sont pas prises en charge.

En outre, le fichier de données prend en charge les conventions d’en-tête supplémentaires suivantes pour identifier les sous-classifications et d’autres colonnes de données spécialisées :

### En-tête de sous-classification

Par exemple, `Campaigns^Owner` est un en-tête de colonne pour la colonne contenant des valeurs `Campaign Owner`. De même, `Creative Elements^Size` est un en-tête de colonne pour la colonne contenant la sous-classification `Size` de la classification `Creative Elements`.

## Résolution des problèmes affectant les classifications

* [Problèmes de chargement des courants](https://helpx.adobe.com/fr/analytics/kb/common-saint-upload-issues.html) : article de la base de connaissance décrivant les problèmes provenant de formats de fichiers et de contenus de fichiers incorrects.
