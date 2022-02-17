---
title: Importation de mesures de recherche payante
description: Étapes de configuration d’Adobe Analytics pour effectuer le suivi de vos mesures de recherche payante (par exemple, Google AdWords, MSN, Yahoo, etc.) à l’aide de la fonctionnalité Sources de données.
exl-id: b25a2a26-d277-4a51-9194-973acb425095
source-git-commit: 7c5bfadabe2ea851bb881d067d48b4f4700a53c7
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 8%

---

# Importer [!UICONTROL Recherche payante] mesures utilisant [!UICONTROL Sources de données]

Pour de nombreuses entreprises marketing, le référencement payant est l’un des moyens les plus précieux et les plus fiables à la fois &#x200B; atteindre de nouveaux clients et conserver les clients existants. Le [!UICONTROL Sources de données] La fonctionnalité d’Adobe Analytics facilite l’importation de données de recherche payante avancées à partir de plateformes publicitaires numériques telles que Google AdWords. Vous pouvez l’intégrer au reste de vos données marketing, ainsi qu’aux données comportementales et d’attributs du client sur site, afin de vous permettre d’obtenir de meilleures informations sur les efforts de recherche payante de votre entreprise.

Ces étapes vous montrent comment configurer une intégration avec AdWords pour importer des données de mots-clés, ainsi que des mesures telles que les impressions, les clics, le coût par clic, etc.

Les étapes expliquent comment configurer une importation unique des données de paiement par clic. Cependant, [!UICONTROL Sources de données] permet l’importation continue des données à l’aide du format de fichier décrit ici. Selon votre plateforme de recherche payante, vous pouvez planifier des exportations périodiques (quotidiennes, mensuelles, etc.), configurer des processus automatisés pour transformer ces exportations en format de fichier requis par Adobe Analytics et charger ces fichiers dans Adobe Analytics afin de générer des rapports d’intégration de recherche payante.

## Conditions préalables

* Vous avez mis en oeuvre la détection de référencement payant.
* Vous capturez des données de code de suivi.
* Vous disposez de codes de suivi uniques pour chaque groupe publicitaire.

## Configurer [!UICONTROL Événements de succès]

Notre première étape consiste à préparer Adobe Analytics à recevoir les mesures. Pour ce faire, vous devez configurer certains événements de succès.

[!UICONTROL Les événements de succès sont des actions dont le suivi peut être effectué. ] Vous déterminez ce qu’une [!UICONTROL événement de succès] est . À des fins de suivi [!UICONTROL recherche payante] mesures, nous voulons configurer [!UICONTROL événements de succès] round [!UICONTROL clics], [!UICONTROL impressions], [!UICONTROL coût total] et activez[!UICONTROL codes de suivi].

1. Accédez à **[!UICONTROL Adobe Analytics > Admin > Suites de rapports]**.
1. Sélectionnez une suite de rapports.
1. Cliquez sur **[!UICONTROL Modifier les paramètres > Conversion > Événements de succès]**.

   ![Événements de succès](assets/success-events.png)

1. Sous Événements de succès personnalisés, utilisez **[!UICONTROL Ajouter]** pour créer trois événements de succès personnalisés : [!UICONTROL Clics] (Compteur), [!UICONTROL Impressions] (Compteur) et [!UICONTROL Coût total] (Devise).

   ![Nouvel événement de succès](assets/new-success-events.png)

1. Cliquez sur Enregistrer.
Vous devriez recevoir un message indiquant que vos enregistrements ont été approuvés.
1. Accédez à **[!UICONTROL Admin > Suites de rapports > Modifier les paramètres > Conversion > Variables de conversion]**.
1. Activez les codes de suivi en cochant la case en regard de **[!UICONTROL Code de suivi]** under **[!UICONTROL Campagne > Variable de campagne]**.

   ![Variable de campagne](assets/campaign-variable.png)

## Configuration des sources de données

[!UICONTROL Sources de données] vous permettent de partager des données hors parcours de navigation avec Adobe Analytics. Dans ce cas, nous utilisons Adobe Analytics pour effectuer le suivi des mesures de recherche payante. Nous utilisons le code de suivi comme clé pour lier les deux éléments de données (mesures de recherche payante et mesures Adobe Analytics).

1. Accédez à **[!UICONTROL Adobe Analytics > Admin > Tous les administrateurs > Sources de données]**.
1. Sélectionnez la **[!UICONTROL Créer]** pour commencer à activer de nouvelles sources de données.
1. Sous **[!UICONTROL Sélectionner une catégorie]**, sélectionnez **[!UICONTROL Campagne publicitaire]**.

   ![Sources de données](assets/data-sources.png)

1. Sous **[!UICONTROL Sélectionner un type]**, sélectionnez **[!UICONTROL Service de paiement par clic générique]**.
1. Cliquez sur **[!UICONTROL Activer]**.
Le [!UICONTROL Assistant d’activation de la source de données] affiche :

   ![sources de données](assets/ds-activation-wizard.png)

1. Cliquez sur **[!UICONTROL Suivant]** et attribuez un nom à votre source de données. Ce nom apparaît dans le Gestionnaire des sources de données.
1. Acceptez le contrat de service et cliquez sur **[!UICONTROL Suivant]**.
1. Sélectionnez les trois mesures standard : [!UICONTROL Impressions], [!UICONTROL Clics] et [!UICONTROL Coût total] et cliquez sur **[!UICONTROL Suivant]**.
1. Maintenant, &quot;mappez&quot; cette nouvelle source de données avec les événements personnalisés que nous avons créés dans [Configuration des événements de succès](/help/admin/admin/c-success-events/t-success-events.md).

   ![Mappage](assets/data-source-mapping.png)

1. Choisir les dimensions de données Cochez la case en regard de Codes de suivi et cliquez sur **[!UICONTROL Suivant]**.
1. Mappage des Dimensions de données.
Mappez la dimension (attribut) des données importées à l’attribut Adobe Analytics dans lequel vous souhaitez la stocker. Il peut s’agir d’une dimension standard ou d’un eVar. Après avoir cliqué sur **[!UICONTROL Suivant]**, les mappages résultants sont affichés dans la synthèse :

   ![Résumé](assets/data-source-summary.png)

1. Cliquez sur **[!UICONTROL Enregistrer]**.
1. Cliquez sur **[!UICONTROL Télécharger]** pour télécharger le fichier de modèle pour cette source de données.
Le nom de fichier correspond au type de source de données que vous avez initialement spécifié, à savoir, dans ce cas, &quot;Generic Pay-Per-Click Service template.txt&quot;.
1. Ouvrez le modèle dans votre éditeur de texte préféré.
Le fichier est déjà renseigné avec les mesures et les dimensions et leurs mappages.

## Exportation des données PPC et transfert vers Analytics

Les étapes similaires à celles-ci fonctionnent pour les mots-clés Google, MSN, Yahoo et d’autres comptes PPC.

### Exportation des données

1. Connectez-vous à votre compte PPC et créez un nouveau rapport ou exportez-le.
Assurez-vous que l’exportation comprend les champs suivants : date, URL de destination (landing page), impressions, clics et coût. L&#39;export peut inclure d&#39;autres champs, mais vous allez les supprimer en suivant les étapes ci-dessous.
1. Si possible, enregistrez le rapport en tant que `.csv` ou fichier délimité par des tabulations. Cela facilite l’utilisation dans les étapes suivantes.
1. Ouvrez le fichier dans Microsoft Excel.

### Modifier le fichier dans Microsoft Excel

1. Dans Microsoft Excel, supprimez toutes les colonnes autres que celles mentionnées ci-dessus.
1. Supprimez toutes les rangées supplémentaires du haut.
1. Pour isoler les codes de suivi des URL de destination : a. Copiez et collez les données de toutes les colonnes.
b. Cliquez sur **[!UICONTROL Données > Texte en colonnes]**.
c. À l’étape 1 de l’assistant, assurez-vous que **[!UICONTROL Délimité]** est sélectionné et cliquez sur **[!UICONTROL Suivant]**.
d. À l’étape 2 de l’assistant, spécifiez le délimiteur en fonction de la manière dont vous avez créé vos URL (ou ? ou &amp;) et cliquez sur **[!UICONTROL Suivant]**.
e. À l’étape 3 de l’assistant, prévisualisez vos données et vérifiez que l’une des colonnes est &quot;trackingcodename=trackingcode&quot;. Si vous disposez de variables supplémentaires, répétez ces étapes (en utilisant &amp; comme délimiteur).
f. Supprimez toutes les colonnes, à l&#39;exception des codes de suivi, des impressions, des clics et des coûts. Ajoutez une nouvelle colonne intitulée Date et organisez vos colonnes dans l’ordre suivant : Date : Code de suivi : Impressions : Clics : Coût.
1. Ajoutez ces données au modèle que vous avez téléchargé dans la section &quot;Configuration des sources de données&quot; ci-dessus.
Vous êtes maintenant prêt à charger le fichier.

### Transfert du fichier vers Adobe Analytics par FTP

Revenez à l’assistant de source de données pour obtenir des instructions et chargez le fichier par FTP :

![Télécharger FTP](assets/upload-ftp.png)

## Créer des mesures calculées

L’ajout de mesures calculées s’avère utile lors des décisions de paiement par clic.

Par exemple, vous pouvez ajouter ces [mesures calculées](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=en#calculated-metrics):

| Nom | Formule | Type de mesure | Description |
| --- | --- | --- | --- |
| Pages vues par visite | Pages vues / Visites | Numérique | Lorsqu’elle est appliquée au niveau d’un site, indique le nombre moyen de pages par visite. Lorsqu’elle est appliquée dans le rapport Pages les plus populaires, indique le nombre moyen de fois où une page particulière a été affichée par visite. |
| Valeur de commande moyenne | Recettes / Commandes | Devise | Indique les recettes moyennes par commande. |
| Recettes par visite | Recettes/Visite | Devise | Indique les recettes moyennes par visite. |
| Taux de clics publicitaires (CTR) | Clics/Impressions | Numérique | Mesurez le rapport clics/impressions d’une publicité en ligne ou d’une campagne de marketing par e-mail. |
| Profit | Recettes - Coût | Devise | Affiche les recettes d’une campagne moins le coût. |
| Profit par impression (PPI) | (Recettes - Coût)/Impression | Devise | Indique le montant des recettes générées chaque fois qu’une publicité s’affichait, équilibré par le coût. |
| Retour sur dépenses publicitaires (ROAS) | Montant des ventes/dépenses publicitaires | Devise | (ROI) Représente les dollars gagnés par dollar dépensé dans la publicité correspondante. |

## Configuration et exécution de rapports

La dernière étape consiste à ajouter les mesures de source de données et les mesures calculées au rapport Code de suivi , puis à approfondir l’analyse d’une campagne afin d’obtenir une vue immédiate des performances de chaque groupe publicitaire.

1. Dans **[!UICONTROL Adobe Analytics > Rapports]**, sélectionnez la suite de rapports dans laquelle vous avez importé des sources de données.
1. Accédez à **[!UICONTROL Rapports > Campagnes > Code de suivi > Code de suivi]**.
1. Sélectionnez la période.
1. Cliquez sur **[!UICONTROL Mesures > Ajouter]** et ajoutez vos mesures de source de données (clics, impressions, coût total) dans la liste des mesures standard.
1. Faites de même pour toutes les mesures calculées que vous avez ajoutées. Le rapport est mis à jour à mesure que vous ajoutez des mesures.
