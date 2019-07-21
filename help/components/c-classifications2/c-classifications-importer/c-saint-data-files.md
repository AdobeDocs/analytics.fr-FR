---
description: L’importateur vous permet de télécharger en vrac des données de classification dans des rapports d’analyse sous la forme d’un fichier. Pour que les chargements de données s’effectuent correctement, un format de fichier spécifique est requis pour l’importation.
seo-description: L’importateur vous permet de télécharger en vrac des données de classification dans des rapports d’analyse sous la forme d’un fichier. Pour que les chargements de données s’effectuent correctement, un format de fichier spécifique est requis pour l’importation.
seo-title: Fichiers de données de classification
solution: Analytics
subtopic: Gestionnaire
title: Fichiers de données de classification
topic: Outils d’administration
uuid: f 27 bb 812-56 e 0-472 a -9993-d 869 f 0 fea 700
translation-type: tm+mt
source-git-commit: c0c4a3f42a7236c6f9e5001f5ca0ef9173dbaa66

---


# Fichiers de données de classification

L’importateur vous permet de télécharger en vrac des données de classification dans des rapports d’analyse sous la forme d’un fichier. Pour que les chargements de données s’effectuent correctement, un format de fichier spécifique est requis pour l’importation.

Pour vous aider à créer des fichiers de données valides, vous pouvez télécharger un fichier de modèle qui fournit une structure de fichier dans laquelle vous pouvez coller les données de classification. For more information, see [Download Classifications Template](../../../components/c-classifications2/c-classifications-importer/c-download-saint-data.md#concept_0F06847AD8D042F5BA818AE3C37E2417).

See [General File Structure](../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_9EFF968DF5D244A887DE94075431C1BE) for more information about character limits in classifications.

See [Numeric 2 Classifications](../../../components/c-classifications2/c-numeric-2/c-numeric-2-classifications.md#concept_71024B7B91DF4E909076062AB1380D8B) for information about uploading data using numeric 2 classifications.

## Structure générale des fichiers

La figure suivante illustre un exemple de fichier de données :

![](assets/completed-saint-file.png)

Un fichier de données doit respecter les règles de structure suivantes :

* Les classifications ne peuvent pas contenir une valeur nulle (zéro).
* Adobe recommande que vous limitiez à 30 le nombre de colonnes d’importation et d’exportation.
* Les fichiers téléchargés doivent utiliser UTF-8 sans codage des caractères de nomenclature.
* Des caractères spéciaux, tels que des tabulations, des sauts de lignes et des guillemets peuvent être incorporés dans une cellule sous réserve que le format de fichier v2.1 soit indiqué et que la cellule soit correctement [placée dans une séquence d’échappement](../../../components/c-classifications2/c-classifications-importer/t-classifications-escape-data.md#task_EB47E80063F14F9CB2D186C0CAA9CBAD). Les caractères spéciaux incluent :

   ```
   \t     tab character 
   \r     form feed character 
   \n    newline character 
   "       double quote
   ```

   La virgule n’est pas un caractère spécial.

* Les classifications ne peuvent pas contenir de caret (^) puisque ce caractère est utilisé pour indiquer une sous-classification.
* Faites attention lorsque vous utilisez un trait d’union. For example, if you use a hyphen (-) in a Social term, Social recognizes the hyphen as a [!DNL Not] operator (the minus sign). For example, if you specify *`fragrance-free`* as a term using the import, Social recognizes the term as fragrance *`minus`* free and collects posts that mention *`fragrance`*, but not *`free`*.
* Des limites de caractères sont appliquées afin de classer les données de rapport. For example, if you upload a classifications text file for products ( *`s.products`*) with product names longer than 100 characters (bytes), the products will not display in reporting. Les codes de suivi et toutes les variables de conversions (eVars) autorisent 255 octets.
* Il doit s’agir d’un fichier délimité par des tabulations (créez le fichier de modèle dans tout tableur ou éditeur de texte).
* Either a [!DNL .tab] or [!DNL .txt] file extension.
* Le signe dièse (#) identifie la ligne comme commentaire utilisateur. Adobe ignore toutes les lignes commençant par #.
* Deux signes dièse suivis des caractères SC (## SC) identifient la ligne comme commentaire d’en-tête de prétraitement utilisé par la création de rapports. Ne supprimez pas ces lignes.
* Les exportations de classification peuvent comporter des clés en double en raison des caractères de saut de page de la clé. Dans une exportation FTP ou de navigateur, ce problème peut être résolu en activant la création de guillemets pour le compte FTP. Cette activation place des guillemets entourant chaque clé comportant des caractères de saut de page.
* La cellule C1 de la première ligne du fichier d’importation comporte un identifiant de version qui détermine la façon dont les classifications traitent l’utilisation des guillemets dans le reste du fichier.

   * Le format v2.0 ignore les guillemets et présume qu’ils font tous partie des clés et valeurs indiquées. Étudions par exemple cette valeur : "C’est ""une valeur""". Le format v2.0 interprète cette valeur littéralement : "C’est ""une valeur""".
   * Le format v2.1 indique aux classifications de présumer que les guillemets font partie du formatage des fichiers utilisé dans les fichiers Excel. De ce fait, le format v2.1 formate l’exemple ci-dessus ainsi : C’est "une valeur".
   * Des problèmes peuvent survenir lorsque le format v2.1 est indiqué dans le fichier alors que c’est le format v2.0 qui est voulu - à savoir lorsque des guillemets sont utilisés de façon non autorisée au format Excel. Par exemple, si vous avez la valeur : "VP NO REPS" S/l Dress w/ Overlay. Avec le format v2.1, ce formatage est incorrect (la valeur devrait être entourée de guillemets ouvrant et fermant et les guillemets qui font partie de la valeur réelle devraient être codés par échappement par des guillemets) et les classifications ne fonctionneront pas au-delà de ce point.
   * Assurez-vous de procéder à l’une des opérations suivantes : modifiez le format du fichier sur v2.0 en modifiant l’en-tête (cellule C1) dans les fichiers que vous téléchargez OU implémentez correctement les guillemets Excel dans l’ensemble des fichiers.

* La première ligne (qui ne soit pas un commentaire) du fichier de données contient les en-têtes de colonne utilisés pour identifier les données de classification contenues dans cette colonne. L’importateur nécessite un format spécifique pour les en-têtes de colonne. Pour plus d’informations, reportez-vous à la section [Format d’un en-tête de colonne](../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_ADC08C783477451B959782CEA23AF5EF).
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
   <td colname="col2"> <p>Ce code demande à Adobe de générer automatiquement un ID unique pour cet élément. </p> <p>Dans le cadre d’une campagne, cette valeur de contrôle demande à Adobe d’attribuer un identificateur à chaque élément créatif. Voir <a href="../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_0B77B3079B5C414F9956058688990443" format="dita" scope="local"> Clé </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~period~ </p> </td> 
   <td colname="col2"> <p>Ce code indique que la colonne de données représente la période associée à l’élément. Voir <a href="../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_9ECCD5ED97764CDC90C0B7B0F9461825" format="dita" scope="local"> Date </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Champ vide </p> </td> 
   <td colname="col2"> <p>Ce code représente une valeur NULL pour le champ actif. Utilisez-le si une colonne de données spécifique ne s’applique pas à l’enregistrement actif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modificateurs PER </p> </td> 
   <td colname="col2"> <p>Ce code indique que la colonne de données représente des champs de <span class="wintitle">modificateur PER</span>. See <a href="../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_7E199A26E3274B31B07CCAF8DFE3B274" format="dita" scope="local"> PER Modifier Headings </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [Problèmes de téléchargement courants](https://helpx.adobe.com/analytics/kb/common-saint-upload-issues.html)


## Format d'en-tête de colonne

>[!NOTE]
>
>Adobe recommande que vous limitiez à 30 le nombre de colonnes d’importation et d’exportation.

Les fichiers de classification prennent en charge les en-têtes de colonne suivants :

### Clé

Chaque valeur doit être unique dans l’ensemble du système. The value in this field corresponds to a value assigned to the [!DNL Analytics] variable in your Web site’s [!DNL JavaScript] beacon. Data in this column might include ~autogen~ or any other unique tracking code.

### En-tête de colonne de classification

Par exemple, les Reports &amp; Analytics incluent automatiquement deux classifications pour les variables [!UICONTROL Campagne], à savoir : [!UICONTROL Campagnes] et [!UICONTROL Éléments créatifs]. Pour ajouter des données à la classification [!UICONTROL Campagnes], l’en-tête de colonne dans le fichier de données doit être [!UICONTROL Campagnes].

>[!NOTE]
>
>The values in the [!UICONTROL Classifications] column heading must exactly match the classification’s naming convention, or the import fails. Par exemple, si l’administrateur remplace [!UICONTROL Campagnes] par [!UICONTROL Noms de campagnes internes] dans le [!UICONTROL Gestionnaire de configuration de campagne], l’en-tête de colonne doit aussi être remplacé.

De plus, le fichier de données prend en charge des conventions d’en-tête supplémentaires pour identifier les sous-classifications et d’autres colonnes de données spécialisées :

### En-tête de sous-classification

Par exemple, [!UICONTROL Campaigns^Owner] est l’en-tête de la colonne contenant les valeurs du [!UICONTROL propriétaire des campagnes]. De même, [!UICONTROL Creative Elements^Size] est l’en-tête de la colonne contenant la sous-classification de [!UICONTROL taille] de la classification des [!UICONTROL éléments créatifs].

### En-têtes de mesure de classification

Par exemple, [!UICONTROL Campaigns^~Cost] fait référence à la mesure de [!UICONTROL coût] de la classification des [!UICONTROL campagnes].

### En-tête de modificateur PER

*`Per Modifier`* sont identifiés en ajoutant *`~per`* à l'en-tête de mesure de classification. For example, if the *`Metric`* heading is *`Campaigns^~Cost`*, the PER modifier heading is *`Campaigns^~Cost~per`*. Adobe supports the following *`PER Modifier`* keywords:

Ces caractères ont une signification spéciale dans un fichier de données. Lorsque cela est possible, évitez d’utiliser ces termes dans des données et des noms d’attributs.

**FIXED :** valeur fixe. N’effectuez aucune mise à l’échelle.

**DAY :** multiplier la valeur par le nombre de jours dans le rapport.

**ORDER :** multiplier la valeur par le nombre de commandes de l’article dans le rapport.

**CHECKOUT :** multiplier la valeur par le nombre de passages en caisse pour l’article dans le rapport.

**UNIT :** multiplier la valeur par le nombre d’unités de l’article dans le rapport.

**REVENUE :** multiplier la valeur par le montant des recettes de l’article dans le rapport.

**SCADD :** multiplier la valeur par le nombre de fois que l’événement d’[!UICONTROL ajout au panier d’achat] a été appelé par article dans le rapport.

**SCREMOVE :** multiplier la valeur par le nombre de fois que l’événement de [!UICONTROL retrait du panier] a été appelé par article dans le rapport.

**INSTANCE :** multiplier la valeur par le nombre d’instances de l’article dans le rapport.

**CLICK :** multiplier la valeur par le nombre de clics sur l’article dans le rapport.

**EVENT :** multiplier la valeur par le nombre de fois que l’événement personnalisé spécifié s’est produit par article dans le rapport.

**Exemple :** Si la campagne A coûte 10 000 $, la colonne [!UICONTROL Campaigns ^ ~ Cost] contient une valeur de 10000 et [!UICONTROL la colonne Campaigns ^~Costper~] contient [!UICONTROL FIXED]. Lors de l’affichage du coût de la Campagne A dans les rapports, la somme de 10 000 euros est indiquée comme coût fixe de la Campagne A pour la période.

**Exemple :** Si la campagne B qui coûte environ 2 euros par clic, la colonne [!UICONTROL Campaigns ^ ~ Cost] contient 2 et **[!UICONTROL la colonne Campaigns ^~Costper~]** contient [!UICONTROL CLICK]. When displaying the Cost for Campaign B in the reports, Adobe calculates (2 * [number of clicks]) on the fly for the date range of the report. Vous obtenez alors le coût total en fonction du nombre de clics enregistrés pendant la Campagne B.

### Date

Les dates de campagne sont généralement des périodes (dates de début et de fin) associées à chaque campagne. Elles doivent apparaître au format AAAA/MM/JJ. Par exemple, 2013/06/15-2013/06/30.

Pour plus d’informations, reportez-vous à la section [Classifications des conversions](https://marketing.adobe.com/resources/help/en_US/admin/index.html#Conversion%20Classifications).

>[!NOTE]
>
>In the May 10, 2018, [!DNL Analytics] Maintenance release, Adobe started to limit the functionality of date-enabled and numeric classifications. Ces types de classifications ont été supprimés des interfaces Administration et Importateur de classifications. Il n’est plus possible d’ajouter de nouvelles classifications numériques et activées par date. Il sera possible de continuer à gérer les classifications actuelles (les transférer, les supprimer) par l’intermédiaire des processus de classification standard et elles resteront disponibles dans le reporting.

## Using dates in conjunction with [!UICONTROL classifications] {#section_966A07B228CD4643B258E73FB8BA150A}

[!UICONTROL Les classifications] permettent d'affecter des plages de dates à vos campagnes ou à d'autres [!UICONTROL classifications]de conversion, ce qui permet une mesure de campagne plus précise. Une fois la période d’une valeur indiquée, toute valeur correspondante qui se produit en dehors de la période ne sera pas classée. Cela est utile pour la mesure de campagne qui souhaite utiliser les dates exactes à laquelle une campagne était active et non tous les accès correspondant à la campagne elle-même. Afin de classer avec succès une valeur dans une période, les critères suivants doivent être respectés :

* [!UICONTROL La classification] doit être basée sur une variable de conversion.
* [!UICONTROL La classification] utilisée doit être définie en tant que Date-Activé ou Numérique 2.
* La période impliquée doit contenir une date de début et (facultativement) une date de fin.

Pour classer les campagnes selon une période :

1. Log in to [!DNL Analytics] and go to Admin &gt; Classifications.
1. Cliquez sur l’onglet **[!UICONTROL Exportation navigateur], assurez-vous que les paramètres de votre classification Date d’activation sont corrects, puis cliquez sur Exporter un fichier.**
1. Ouvrez ce fichier dans Microsoft Excel ou un autre éditeur de feuilles de calcul familier.
1. Une des colonnes se termine par

   ^~period~
which is the column to enter the date range in.
1. Sous cette colonne, saisissez la période de chaque valeur au format suivant :

   `YYYY/MM/DD - YYYY/MM/DD`. Veillez à ce qui suit :

   * laissez des espaces sur les deux côtés du tiret ;
   * utilisez un trait d’union (-) pour séparer les périodes et non un tiret demi-cadratin (–) ou cadratin (—) ;
   * si le mois ou le jour ne comporte qu’un seul chiffre, un zéro est ajouté devant ce chiffre ;
   * une date de début est présente ; la date de fin est facultative.

1. Save the file, and upload it to [!DNL Analytics] by going to Admin | Classifications | Import File.

>[!NOTE]
>
>Une valeur clé spécifique ne peut pas comporter plus d'une plage de dates.

## Résolution des problèmes des classifications

* [Problèmes de chargement des courants](https://helpx.adobe.com/analytics/kb/common-saint-upload-issues.html) : article de la base de connaissance décrivant les problèmes provenant de formats de fichiers et de contenus de fichiers incorrects.

