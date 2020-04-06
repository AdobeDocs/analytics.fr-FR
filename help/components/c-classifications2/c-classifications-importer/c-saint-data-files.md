---
description: L’importateur vous permet de télécharger en masse des données de classification vers le d’analyses dans un fichier. L’importation nécessite un format de fichier spécifique pour que les téléchargements de données soient réussis.
subtopic: Classifications
title: Fichiers de données de classification
topic: Admin tools
uuid: f27bb812-56e0-472a-9993-d869f0fea700
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Fichiers de données de classification

L’importateur vous permet de télécharger en masse des données de classification vers le d’analyses dans un fichier. L’importation nécessite un format de fichier spécifique pour que les téléchargements de données soient réussis.

Pour vous aider à créer des fichiers de données valides, vous pouvez télécharger un fichier de modèle qui fournit une structure de fichiers dans laquelle vous pouvez coller les données de classification. Pour plus d’informations, reportez-vous à la section [Télécharger le modèle de classifications](/help/components/c-classifications2/c-classifications-importer/c-download-saint-data.md).

Reportez-vous à la section [Structure générale d’un fichier](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md) pour en savoir plus sur les limites de caractères dans les classifications.

Voir [Classifications numériques 2](/help/components/c-classifications2/c-numeric-2/c-numeric-2-classifications.md) pour plus d’informations sur le chargement de données utilisant les classifications numériques 2.

## Structure générale d’un fichier

L’illustration suivante représente un exemple de fichier de données :

![](assets/completed-saint-file.png)

Un fichier de données doit respecter les règles de structure suivantes :

* Les classifications ne peuvent pas avoir la valeur 0 (zéro).
* Adobe recommande que vous limitiez à 30 le nombre de colonnes d’importation et d’exportation.
* Les fichiers téléchargés doivent utiliser UTF-8 sans codage de caractères de nomenclature.
* Des caractères spéciaux, tels que des tabulations, des sauts de lignes et des guillemets peuvent être incorporés dans une cellule sous réserve que le format de fichier v2.1 soit indiqué et que la cellule soit correctement  [placée dans une séquence d’échappement](/help/components/c-classifications2/c-classifications-importer/t-classifications-escape-data.md). Les caractères spéciaux sont les suivants :

   ```
   \t     tab character 
   \r     form feed character 
   \n    newline character 
   "       double quote
   ```

   La virgule n’est pas un caractère spécial.

* Les classifications ne peuvent pas contenir de caret (^), car ce caractère est utilisé pour désigner une sous-classification.
* Soyez prudent lorsque vous utilisez un trait d’union. Par exemple, si vous utilisez un trait d’union (-) dans un terme de réseau social, Social le considère comme un opérateur [!DNL Not] (signe moins). Si, par exemple, vous spécifiez le terme *`fragrance-free`* à l’aide de l’importation, Social reconnaît le terme comme étant fragrance *`minus`* free et rassemble les messages qui mentionnent *`fragrance`*, mais pas *`free`*.
* Des limites de caractères sont appliquées afin de classer les données de rapport. Par exemple, si vous téléchargez un fichier texte de classification pour des produits ( *`s.products`*) dont les noms comportent plus de 100 caractères (octets), les produits en question ne sont pas affichés dans les rapports. Les codes de suivi et toutes les variables de conversions (eVars) autorisent 255 octets.
* Il doit s’agir d’un fichier délimité par des tabulations (créez le fichier de modèle dans tout tableur ou éditeur de texte).
* Il doit être doté de l’extension de fichier [!DNL .tab] ou [!DNL .txt].
* Un signe dièse (#) identifie la ligne comme un commentaire utilisateur. Adobe ignore toute ligne commençant par #.
* Un signe -livre suivi du symbole SC (## SC) identifie la ligne comme un commentaire d’en-tête de prétraitement utilisé par les . Ne supprimez pas ces lignes.
* Les exportations de classifications peuvent comporter des clés  en raison des caractères de nouvelle ligne de la clé. Dans une exportation FTP ou de navigateur, vous pouvez résoudre ce problème en activant les guillemets pour le compte FTP. Les guillemets entourant chaque clé seront alors placés avec des caractères de nouvelle ligne.
* La cellule C1 de la première ligne du fichier d’importation contient un identifiant de version qui détermine comment les classifications gèrent l’utilisation des guillemets dans le reste du fichier.

   * v2.0 ignore les guillemets et suppose qu’ils font tous partie des clés et des valeurs spécifiées. Prenons l’exemple de cette valeur : &quot;C&#39;est &quot;une valeur&quot;&quot;. v2.0 interprète cela littéralement comme suit : &quot;C&#39;est &quot;une valeur&quot;&quot;.
   * La version 2.1 indique aux classifications de présumer que les guillemets font partie du formatage de fichier utilisé dans les fichiers Excel. La version 2.1 formate donc l’exemple ci-dessus comme suit : C&#39;est &quot;une valeur&quot;.
   * Des problèmes peuvent survenir lorsque la version 2.1 est spécifiée dans le fichier, mais ce qui est recherché est en fait la version 2.0, c’est-à-dire lorsque des guillemets sont utilisés de manière illégale sous la mise en forme Excel. Par exemple, si vous avez une valeur : &quot;VP NO REPS&quot; S/l Dress avec superposition. Avec v2.1, la mise en forme est incorrecte (la valeur doit être entourée de guillemets d’ouverture et de fermeture et les guillemets qui font partie de la valeur réelle doivent être précédés de guillemets) et les classifications ne fonctionneront pas au-delà de ce point.
   * Veillez à effectuer l’une des opérations suivantes : modifiez le format de votre fichier en v2.0 en modifiant l’en-tête (cellule C1) dans les fichiers que vous téléchargez OU en implémentant correctement les guillemets Excel dans tous vos fichiers.

* La première ligne (sans commentaire) du fichier de données contient les en-têtes de colonne utilisés pour identifier les données de classification dans cette colonne. L’importateur requiert un format spécifique pour les en-têtes de colonne. Pour en savoir plus, reportez-vous à la section [Format d’en-tête de colonne](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md).
* Immédiatement après la rangée d’en-tête d’un fichier de données se trouvent les rangées de données. Chaque ligne de données doit contenir un champ de données pour chaque en-tête de colonne.
* Le fichier de données prend en charge les codes de contrôle suivants, utilisés par Adobe pour fournir la structure au fichier, et importer correctement les données de classification :

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
   <td colname="col2"> <p>Un nouveau caractère de ligne est le seul délimiteur pris en charge entre les lignes de données/enregistrements dans le fichier de données. En règle générale, il suffit d’insérer spécifiquement ces caractères lors de l’écriture d’un  pour générer automatiquement des fichiers de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~autogen~ </p> </td> 
   <td colname="col2"> <p>Demande à Adobe de générer automatiquement un ID unique pour cet élément. </p> <p>Dans le contexte de la campagne, cette valeur de contrôle indique à Adobe d’affecter un identifiant à chaque élément créatif. Voir <a href="/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md"  > Clé </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~period~ </p> </td> 
   <td colname="col2"> <p>Indique que la colonne de données représente la plage de dates associée à l’élément. Voir <a href="/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md"  > Date </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Champ vide </p> </td> 
   <td colname="col2"> <p>Représente une valeur NULL pour le champ actif. Utilisez cette option si une colonne de données particulière ne s’applique pas à l’enregistrement actif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modificateurs PER </p> </td> 
   <td colname="col2"> <p>Ce code indique que la colonne de données représente des champs de <span class="wintitle">modificateur PER</span>. Reportez-vous à la section <a href="/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md"  >En-têtes de modificateur PER </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Problèmes de téléchargement de courants](https://helpx.adobe.com/fr/analytics/kb/common-saint-upload-issues.html)


## Format d’un en-tête de colonne

>[!NOTE] Adobe recommande que vous limitiez à 30 le nombre de colonnes d’importation et d’exportation.

Les fichiers de classification prennent en charge les en-têtes de colonne suivants :

### Clé

Chaque valeur doit être unique dans l’ensemble du système. La valeur de ce champ correspond à une valeur attribuée à la variable [!DNL Analytics] dans la balise [!DNL JavaScript] du site web. Les données de cette colonne peuvent inclure ~autogen~ ou tout autre code de suivi unique.

### En-tête de colonne de classification

Par exemple, les rapports et analyses incluent automatiquement deux classifications pour [!UICONTROL Campaign] les variables : [!UICONTROL Campaigns] et [!UICONTROL Creative Elements]. Pour ajouter des données à la [!UICONTROL Campaigns] classification, l’en-tête de colonne dans le fichier de données de classification serait [!UICONTROL Campaigns].

>[!NOTE] Les valeurs de l’en-tête de [!UICONTROL Classifications] colonne doivent correspondre exactement à la convention d’affectation des noms de la classification, sinon l’importation échoue. Par exemple, si l’administrateur passe [!UICONTROL Campaigns] à [!UICONTROL Internal Campaign Names] dans le [!UICONTROL Campaign Set-up Manager], l’en-tête de colonne du fichier doit changer pour correspondre.

En outre, le fichier de données prend en charge les conventions d’en-tête supplémentaires suivantes pour identifier les sous-classifications et les autres colonnes de données spécialisées :

### En-tête de sous-classification

Par exemple, [!UICONTROL Campaigns^Owner] est un en-tête de colonne pour la colonne contenant [!UICONTROL Campaign Owner] des valeurs. De même, [!UICONTROL Creative Elements^Size] est un en-tête de colonne pour la colonne contenant la [!UICONTROL Size] sous-classification de la [!UICONTROL Creative Elements] classification.

### En-têtes de mesure de classification

For example, [!UICONTROL Campaigns^~Cost] refers to the [!UICONTROL Cost] metric in the [!UICONTROL Campaigns] classification.

### En-tête de modificateur PER

Les en-têtes *`Per Modifier`* sont signalés en ajoutant *`~per`* à l’en-tête de mesure de classification. Par exemple, si l’en-tête de *`Metric`* est *`Campaigns^~Cost`*, l’en-tête de modificateur PER est *`Campaigns^~Cost~per`*. Adobe prend en charge les mots-clés *`PER Modifier`* suivants :

Ces caractères ont une signification spéciale dans un fichier de données. Dans la mesure du possible, évitez d’utiliser ces mots dans les noms d’attribut et les données.

**CORRECTION :** Valeur fixe. N’effectuez aucune mise à l’échelle.

**JOUR :** Multiplier la valeur par le nombre de jours dans le rapport.

**ORDRE :** Multiplier la valeur par le nombre de commandes de l&#39;article dans le rapport.

**CHECKOUT :** Multiplier la valeur par le nombre de passages en caisse pour l&#39;article dans le rapport.

**UNITE :** Multiplier la valeur par le nombre d&#39;unités de l&#39;élément de ligne dans le rapport.

**RECETTES :** Multiplier la valeur par le montant des recettes de l&#39;article dans le rapport.

**SCADD :** Multiplier la valeur par le nombre de fois où le [!UICONTROL Shopping Cart Add] a été appelé par élément de ligne dans le rapport.

**SCREMOVE :** Multiplier la valeur par le nombre de fois où le [!UICONTROL Shopping Cart Remove] a été appelé par élément de ligne dans le rapport.

**INSTANCE :** Multiplier la valeur par le nombre d’instances de l’élément de ligne dans le rapport.

**CLIQUEZ SUR :** Multiplier la valeur par le nombre de clics pour l’élément de ligne dans le rapport.

**:** Multiplier la valeur par le nombre de fois où le personnalisé spécifié s’est produit par élément de ligne du rapport.

**Exemple :** Si Campaign A coûte 10 000 euros, la [!UICONTROL Campaigns^~Cost] colonne contient une valeur de 10 000 et la colonne [!UICONTROL Campaigns^~~Coût] contient [!UICONTROL FIXED]. Lors de l’affichage du coût de la Campagne A dans les rapports, la somme de 10 000 euros est indiquée comme coût fixe de la Campagne A pour la période.

**Exemple :** Si Campaign B coûte environ 2 euros par clic, la [!UICONTROL Campaigns^~Cost] colonne contient 2 et la colonne **[!UICONTROL Campaigns^~~Coût]** contient [!UICONTROL CLICK]. Lors de l’affichage du coût de la Campagne B dans les rapports, Adobe calcule (2 * [nombre de clics]) à la volée pour la période du rapport. Vous obtenez alors le coût total en fonction du nombre de clics enregistrés pendant la Campagne B.

### Date

Les dates de campagne sont généralement des plages (dates de  et de fin) associées à des campagnes individuelles. Les dates doivent apparaître au format AAAA/MM/JJ. Par exemple, 2013/06/15-2013/06/30.

Pour plus d’informations, voir Classifications des [conversions](https://marketing.adobe.com/resources/help/en_US/admin/index.html#Conversion%20Classifications).

>[!NOTE] Dans la version de maintenance du 10 mai 2018 d’[!DNL Analytics], Adobe a commencé à limiter les fonctionnalités des classifications activées par date et numériques. Ces types de classifications ont été supprimés des interfaces Administration et Importateur de classifications. Aucune nouvelle classification numérique et à date d’activation ne peut être ajoutée. Il sera possible de continuer à gérer les classifications actuelles (les transférer, les supprimer) par l’intermédiaire des processus de classification standard et elles resteront disponibles dans le reporting.

## Utilisation de dates en association avec des [!UICONTROL classifications] {#section_966A07B228CD4643B258E73FB8BA150A}

Vous pouvez utiliser les [!UICONTROL Classifications] pour affecter des périodes à vos campagnes ou autres [!UICONTROL classifications] de conversion ce qui permet une mesure plus précise des campagnes. Après avoir spécifié la plage de dates d’une valeur, toute valeur correspondante qui se produit en dehors de la plage de dates ne sera pas classée. Cela est utile pour la mesure de campagne qui souhaite utiliser les dates exactes auxquelles une campagne était active et non tous les accès correspondant à la campagne elle-même. Pour classer correctement une valeur avec une plage de dates, les conditions suivantes doivent être remplies :

* La [!UICONTROL classification] doit être basée sur une variable de conversion.
* La [!UICONTROL classification] utilisée doit être définie en tant que Date d’activation Numérique 2.
* La période concernée doit contenir une date de  et (éventuellement) une date de fin.

Pour classer les campagnes en fonction de la période :

1. Connectez-vous à [!DNL Analytics] et accédez à Admin > Classifications.
1. Click the **[!UICONTROL Browser Export]** tab, ensure the settings to your date-enabled classification are correct, then click Export File.
1. Ouvrez ce fichier dans Microsoft Excel ou un autre éditeur de feuilles de calcul familier.
1. Une des colonnes se termine par

   ^~period~
, qui est la colonne dans laquelle il convient d’entrer la plage de dates.
1. Sous cette colonne, saisissez la période de chaque valeur au format suivant :

   `YYYY/MM/DD - YYYY/MM/DD`. Veuillez vous assurer que :

   * Laissez des espaces des deux côtés du tiret.
   * Utilisez un trait d’union (-) pour séparer les plages, et non un tiret demi-cadratin ou cadratin.
   * Si le mois ou le jour est un seul chiffre, il y a un zéro de début.
   * Il existe une plage de dates  ; la plage de dates de fin est facultative.

1. Enregistrez le fichier et téléchargez-le dans [!DNL Analytics] en accédant à Admin.| Classifications| Importer un fichier.

>[!NOTE] Une valeur de clé spécifique ne peut pas comporter plusieurs périodes.

## Résolution des problèmes affectant les classifications

* [Problèmes de chargement des courants](https://helpx.adobe.com/fr/analytics/kb/common-saint-upload-issues.html) : article de la base de connaissance décrivant les problèmes provenant de formats de fichiers et de contenus de fichiers incorrects.

