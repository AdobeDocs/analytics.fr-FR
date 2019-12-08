---
description: L’importateur vous permet de télécharger en vrac des données de classification dans des rapports d’analyse sous la forme d’un fichier. Pour que les chargements de données s’effectuent correctement, un format de fichier spécifique est requis pour l’importation.
subtopic: Classifications
title: Fichiers de données de classification
topic: Admin tools
uuid: f27bb812-56e0-472a-9993-d869f0fea700
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Fichiers de données de classification

L’importateur vous permet de télécharger en vrac des données de classification dans des rapports d’analyse sous la forme d’un fichier. Pour que les chargements de données s’effectuent correctement, un format de fichier spécifique est requis pour l’importation.

Pour vous aider à créer des fichiers de données valides, vous pouvez télécharger un fichier de modèle qui fournit une structure de fichier dans laquelle vous pouvez coller les données de classification. Pour plus d’informations, reportez-vous à la section [Télécharger le modèle de classifications](/help/components/c-classifications2/c-classifications-importer/c-download-saint-data.md).

Reportez-vous à la section [Structure générale d’un fichier](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md) pour en savoir plus sur les limites de caractères dans les classifications.

Voir [Classifications numériques 2](/help/components/c-classifications2/c-numeric-2/c-numeric-2-classifications.md) pour plus d’informations sur le chargement de données utilisant les classifications numériques 2.

## Structure générale d’un fichier

La figure suivante illustre un exemple de fichier de données :

![](assets/completed-saint-file.png)

Un fichier de données doit respecter les règles de structure suivantes :

* Les classifications ne peuvent pas contenir une valeur nulle (zéro).
* Adobe recommande que vous limitiez à 30 le nombre de colonnes d’importation et d’exportation.
* Les fichiers téléchargés doivent utiliser UTF-8 sans codage des caractères de nomenclature.
* Des caractères spéciaux, tels que des tabulations, des sauts de lignes et des guillemets peuvent être incorporés dans une cellule sous réserve que le format de fichier v2.1 soit indiqué et que la cellule soit correctement [placée dans une séquence d’échappement](/help/components/c-classifications2/c-classifications-importer/t-classifications-escape-data.md). Les caractères spéciaux incluent :

   ```
   \t     tab character 
   \r     form feed character 
   \n    newline character 
   "       double quote
   ```

   La virgule n’est pas un caractère spécial.

* Les classifications ne peuvent pas contenir de caret (^) puisque ce caractère est utilisé pour indiquer une sous-classification.
* Faites attention lorsque vous utilisez un trait d’union. Par exemple, si vous utilisez un trait d’union (-) dans un terme de réseau social, Social le considère comme un opérateur [!DNL Not] (signe moins). Si, par exemple, vous spécifiez le terme *`fragrance-free`* à l’aide de Importer, Social reconnaît le terme comme étant fragrance *`minus`* free et rassemble les messages qui mentionnent *`fragrance`*, mais pas *`free`*.
* Des limites de caractères sont appliquées afin de classer les données de rapport. Par exemple, si vous téléchargez un fichier texte de classification pour des produits ( *`s.products`*) dont les noms comportent plus de 100 caractères (octets), les produits en question ne sont pas affichés dans les rapports. Les codes de suivi et toutes les variables de conversions (eVars) autorisent 255 octets.
* Il doit s’agir d’un fichier délimité par des tabulations (créez le fichier de modèle dans tout tableur ou éditeur de texte).
* Il doit être doté de l’extension de fichier [!DNL .tab] ou [!DNL .txt].
* Le signe dièse (#) identifie la ligne comme commentaire utilisateur. Adobe ignore toutes les lignes commençant par #.
* Deux signes dièse suivis des caractères SC (## SC) identifient la ligne comme commentaire d’en-tête de prétraitement utilisé par la création de rapports. Ne supprimez pas ces lignes.
* Les exportations de classification peuvent comporter des clés en double en raison des caractères de saut de page de la clé. Dans une exportation FTP ou de navigateur, ce problème peut être résolu en activant la création de guillemets pour le compte FTP. Cette activation place des guillemets entourant chaque clé comportant des caractères de saut de page.
* La cellule C1 de la première ligne du fichier d’importation comporte un identifiant de version qui détermine la façon dont les classifications traitent l’utilisation des guillemets dans le reste du fichier.

   * Le format v2.0 ignore les guillemets et présume qu’ils font tous partie des clés et valeurs indiquées. Étudions par exemple cette valeur : "C’est ""une valeur""". Le format v2.0 interprète cette valeur littéralement : "C’est ""une valeur""".
   * Le format v2.1 indique aux classifications de présumer que les guillemets font partie du formatage des fichiers utilisé dans les fichiers Excel. De ce fait, le format v2.1 formate l’exemple ci-dessus ainsi : C’est "une valeur".
   * Des problèmes peuvent survenir lorsque le format v2.1 est indiqué dans le fichier alors que c’est le format v2.0 qui est voulu - à savoir lorsque des guillemets sont utilisés de façon non autorisée au format Excel. Par exemple, si vous avez la valeur : "VP NO REPS" S/l Dress w/ Overlay. Avec le format v2.1, ce formatage est incorrect (la valeur devrait être entourée de guillemets ouvrant et fermant et les guillemets qui font partie de la valeur réelle devraient être codés par échappement par des guillemets) et les classifications ne fonctionneront pas au-delà de ce point.
   * Assurez-vous de procéder à l’une des opérations suivantes : modifiez le format du fichier sur v2.0 en modifiant l’en-tête (cellule C1) dans les fichiers que vous téléchargez OU implémentez correctement les guillemets Excel dans l’ensemble des fichiers.

* La première ligne (qui ne soit pas un commentaire) du fichier de données contient les en-têtes de colonne utilisés pour identifier les données de classification contenues dans cette colonne. L’importateur nécessite un format spécifique pour les en-têtes de colonne. Pour en savoir plus, reportez-vous à la section [Format d’en-tête de colonne](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md).
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
   <td colname="col2"> <p>Ce code demande à Adobe de générer automatiquement un ID unique pour cet élément. </p> <p>Dans le cadre d’une campagne, cette valeur de contrôle demande à Adobe d’attribuer un identificateur à chaque élément créatif. Voir <a href="/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md"  > Clé </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~period~ </p> </td> 
   <td colname="col2"> <p>Ce code indique que la colonne de données représente la période associée à l’élément. Voir <a href="/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md"  > Date </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Champ vide </p> </td> 
   <td colname="col2"> <p>Ce code représente une valeur NULL pour le champ actif. Utilisez-le si une colonne de données spécifique ne s’applique pas à l’enregistrement actif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modificateurs PER </p> </td> 
   <td colname="col2"> <p>Ce code indique que la colonne de données représente des champs de <span class="wintitle">modificateur PER</span>. Reportez-vous à la section <a href="/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md"  >En-têtes de modificateur PER </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Problèmes de téléchargement de courants](https://helpx.adobe.com/analytics/kb/common-saint-upload-issues.html)


## Format d’un en-tête de colonne

> [!NOTE] Adobe recommande que vous limitiez à 30 le nombre de colonnes d’importation et d’exportation.

Les fichiers de classification prennent en charge les en-têtes de colonne suivants :

### Clé

Chaque valeur doit être unique dans l’ensemble du système. La valeur de ce champ correspond à une valeur attribuée à la variable [!DNL Analytics] dans la balise [!DNL JavaScript] du site web. Les données de cette colonne peuvent inclure ~autogen~ ou tout autre code de suivi unique.

### En-tête de colonne de classification

Par exemple, les Reports &amp; Analytics incluent automatiquement deux classifications pour les variables [!UICONTROL Campagne], à savoir : [!UICONTROL Campagnes] et [!UICONTROL Éléments créatifs]. Pour ajouter des données à la classification [!UICONTROL Campagnes], l’en-tête de colonne dans le fichier de données doit être [!UICONTROL Campagnes].

> [!NOTE] Les valeurs de l’en-tête de colonne de [!UICONTROL classification] doivent respecter la convention d’affectation des noms de la classification, sinon l’importation échoue. Par exemple, si l’administrateur remplace [!UICONTROL Campagnes] par [!UICONTROL Noms de campagnes internes] dans le [!UICONTROL Gestionnaire de configuration de campagne], l’en-tête de colonne doit aussi être remplacé.

De plus, le fichier de données prend en charge des conventions d’en-tête supplémentaires pour identifier les sous-classifications et d’autres colonnes de données spécialisées :

### En-tête de sous-classification

Par exemple, [!UICONTROL Campaigns^Owner] est l’en-tête de la colonne contenant les valeurs du [!UICONTROL propriétaire des campagnes]. De même, [!UICONTROL Creative Elements^Size] est l’en-tête de la colonne contenant la sous-classification de [!UICONTROL taille] de la classification des [!UICONTROL éléments créatifs].

### En-têtes de mesure de classification

Par exemple, [!UICONTROL Campaigns^~Cost] fait référence à la mesure de [!UICONTROL coût] de la classification des [!UICONTROL campagnes].

### En-tête de modificateur PER

Les en-têtes *`Per Modifier`* sont signalés en ajoutant *`~per`* à l’en-tête de mesure de classification. Par exemple, si l’en-tête de *`Metric`* est *`Campaigns^~Cost`*, l’en-tête de modificateur PER est *`Campaigns^~Cost~per`*. Adobe prend en charge les mots-clés *`PER Modifier`* suivants :

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

**Exemple** : si Campagne A a un coût de 10 000 euros, la colonne [!UICONTROL Campaigns^~Cost] contient une valeur de 10 000 et la colonne [!UICONTROL Campaigns^~Cost~per] comporte le mot-clé [!UICONTROL FIXED]. Lors de l’affichage du coût de la Campagne A dans les rapports, la somme de 10 000 euros est indiquée comme coût fixe de la Campagne A pour la période.

**Exemple** : si Campagne B a un coût d’environ 2 euros par clic, la colonne [!UICONTROL Campaigns^~Cost] contient 2 et la colonne **[!UICONTROL Campaigns^~Cost~per]** comporte le mot-clé [!UICONTROL CLICK]. Lors de l’affichage du coût de la Campagne B dans les rapports, Adobe calcule (2 * [nombre de clics]) à la volée pour la période du rapport. Vous obtenez alors le coût total en fonction du nombre de clics enregistrés pendant la Campagne B.

### Date

Les dates de campagne sont généralement des périodes (dates de début et de fin) associées à chaque campagne. Elles doivent apparaître au format AAAA/MM/JJ. Par exemple, 2013/06/15-2013/06/30.

Pour plus d’informations, reportez-vous à la section [Classifications des conversions](https://marketing.adobe.com/resources/help/en_US/admin/index.html#Conversion%20Classifications).

> [!NOTE] Dans la version de maintenance du 10 mai 2018 d’[!DNL Analytics], Adobe a commencé à limiter les fonctionnalités des classifications activées par date et numériques. Ces types de classifications ont été supprimés des interfaces Administration et Importateur de classifications. Il n’est plus possible d’ajouter de nouvelles classifications numériques et activées par date. Il sera possible de continuer à gérer les classifications actuelles (les transférer, les supprimer) par l’intermédiaire des processus de classification standard et elles resteront disponibles dans le reporting.

## Utilisation de dates en association avec des [!UICONTROL classifications ] {#section_966A07B228CD4643B258E73FB8BA150A}

Vous pouvez utiliser les [!UICONTROL classifications] pour affecter des périodes à vos campagnes ou autres [!UICONTROL classifications] de conversion ce qui permet une mesure plus précise des campagnes. Une fois la période d’une valeur indiquée, toute valeur correspondante qui se produit en dehors de la période ne sera pas classée. Cela est utile pour la mesure de campagne qui souhaite utiliser les dates exactes auxquelles une campagne était active et non tous les accès correspondant à la campagne elle-même. Afin de classer avec succès une valeur dans une période, les critères suivants doivent être respectés :

* La [!UICONTROL classification] doit être basée sur une variable de conversion.
* La [!UICONTROL classification] utilisée doit être définie en tant que Date d’activation Numérique 2.
* La période impliquée doit contenir une date de début et (facultativement) une date de fin.

Pour classer les campagnes selon une période :

1. Connectez-vous à [!DNL Analytics] et accédez à Admin &gt; Classifications.
1. Cliquez sur l’onglet **[!UICONTROL Exportation navigateur]**, assurez-vous que les paramètres de votre classification Date d’activation sont corrects, puis cliquez sur Exporter un fichier.
1. Ouvrez ce fichier dans Microsoft Excel ou un autre éditeur de feuilles de calcul familier.
1. Une des colonnes se termine par

   ^~period~
, qui est la colonne dans laquelle il convient d’entrer la plage de dates.
1. Sous cette colonne, saisissez la période de chaque valeur au format suivant :

   `YYYY/MM/DD - YYYY/MM/DD`. Veillez à ce qui suit :

   * laissez des espaces sur les deux côtés du tiret ;
   * utilisez un trait d’union (-) pour séparer les périodes et non un tiret demi-cadratin (–) ou cadratin (—) ;
   * si le mois ou le jour ne comporte qu’un seul chiffre, un zéro est ajouté devant ce chiffre ;
   * une date de début est présente ; la date de fin est facultative.

1. Enregistrez le fichier et téléchargez-le dans [!DNL Analytics] en accédant à Admin.| Classifications| Importer un fichier.

> [!NOTE] Une valeur de clé spécifique ne peut pas comporter plusieurs périodes.

## Résolution des problèmes affectant les classifications

* [Problèmes de chargement des courants](https://helpx.adobe.com/analytics/kb/common-saint-upload-issues.html) : article de la base de connaissance décrivant les problèmes provenant de formats de fichiers et de contenus de fichiers incorrects.

