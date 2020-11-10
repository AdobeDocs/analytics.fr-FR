---
title: Importer les mesures de recherche payante
description: Procédure de configuration d’Adobe Analytics pour effectuer le suivi de vos mesures de recherche payante (par exemple, Google AdWords, MSN, Yahoo, etc.) à l’aide de la fonctionnalité Sources de données.
translation-type: tm+mt
source-git-commit: 81592ab80942b802fff3df62d2cd44b1e376aff8
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 8%

---


# Importer des mesures de recherche  payante à l’aide de [!UICONTROL sources de données]

Pour de nombreuses entreprises de marketing, la recherche payante est l&#39;un des moyens les plus précieux et les plus fiables à la fois &#x200B; atteindre de nouveaux clients et de conserver les clients existants. La fonctionnalité Sources [!UICONTROL de] données en Adobe Analytics facilite l’importation de données de recherche payante avancées à partir de plateformes de publicité numérique telles que Google AdWords. Vous pouvez l’intégrer au reste de vos données marketing, ainsi qu’aux données d’attributs comportementaux et clients sur site, afin de vous permettre de mieux comprendre les efforts de recherche payante de votre entreprise.

Ces étapes vous montrent comment configurer une intégration avec AdWords pour importer des données de mots-clés ainsi que des mesures telles que les impressions, les clics, le coût par clic, etc.

Les étapes expliquent comment configurer une importation unique des données de paiement par clic. Cependant, la fonctionnalité Sources [!UICONTROL de] données permet l’importation continue de données en utilisant le format de fichier décrit ici. En fonction de votre plateforme de recherche payée, vous pouvez planifier des exportations périodiques (quotidiennes, mensuelles, etc.), configurer des processus automatisés pour transformer ces exportations en format de fichier requis par Adobe Analytics et télécharger ces fichiers dans Adobe Analytics pour un rapports d&#39;intégration de la recherche payante.

## Conditions préalables

* Vous avez mis en oeuvre la détection des recherches payantes.
* Vous capturez des données de code de suivi.
* Vous disposez de codes de suivi uniques pour chaque groupe publicitaire.

## Configure [!UICONTROL Success Events]

Notre première étape est de préparer l&#39;Adobe Analytics à recevoir les mesures. Pour ce faire, vous devez configurer certains événements de réussite.

[!UICONTROL Les événements de succès sont des actions dont le suivi peut être effectué. ] You determine what a [!UICONTROL success event] is. Pour le suivi des mesures de recherche  payée, nous voulons configurer des événements [!UICONTROL de] réussite autour des [!UICONTROL clics], des [!UICONTROL impressions, du coût total et des codes de suivi .]

1. Go to **[!UICONTROL Adobe Analytics > Admin > Report Suites]**.
1. Sélectionnez une suite de rapports.
1. Cliquez sur **[!UICONTROL Modifier les paramètres > Conversion > Événements de succès]**.

   ![Événements de succès](assets/success-events.png)

1. Sous Événements de réussite personnalisés, utilisez **[!UICONTROL Ajouter nouveau]** pour créer 3 événements de réussite personnalisés : [!UICONTROL Clics] (Compteur), [!UICONTROL Impressions] (Compteur) et Coût  total (Devise).

   ![Nouveau événement de réussite](assets/new-success-events.png)

1. Cliquez sur Enregistrer.
Vous devriez recevoir un message indiquant que vos enregistrements ont été approuvés.
1. Accédez à **[!UICONTROL Admin > Report Suites > Modifier les paramètres > Conversion > Variables]** de conversion.
1. Activez les codes de suivi en cochant la case en regard de Code **[!UICONTROL de]** suivi sous **[!UICONTROL Campaign > Variable]** Campaign.

   ![Variable de campagne](assets/campaign-variable.png)

## Configuration des sources de données

[!UICONTROL Les sources] de données vous permettent de partager des données hors parcours de navigation avec Adobe Analytics. Dans ce cas, nous utilisons Adobe Analytics pour effectuer le suivi des mesures de recherche payante. Nous utilisons le code de suivi comme clé pour relier les deux éléments de données - les mesures de recherche payée et les mesures Adobe Analytics -.

1. Accédez à **[!UICONTROL Adobe Analytics > Admin > Sources]** de données.
1. Sélectionnez l’onglet **[!UICONTROL Créer]** pour début d’activation de nouvelles sources de données.
1. Sous **[!UICONTROL Sélectionner une Catégorie]**, sélectionnez **[!UICONTROL Publicité Campaign]**.

   ![Sources de données](assets/data-sources.png)

1. Sous **[!UICONTROL Sélectionner un type]**, sélectionnez Service **[!UICONTROL de paiement par clic]** générique.
1. Cliquez sur **[!UICONTROL Activer]**.
The [!UICONTROL Data Source Activation Wizard] displays:

   ![sources de données](assets/ds-activation-wizard.png)

1. Cliquez sur **[!UICONTROL Suivant]** et nommez votre source de données. Ce nom apparaît dans le Gestionnaire des sources de données.
1. Acceptez le contrat de service et cliquez sur **[!UICONTROL Suivant]**.
1. Sélectionnez les trois mesures standard : [!UICONTROL Impressions], [!UICONTROL Clics] et Coût  total, puis cliquez sur **[!UICONTROL Suivant]**.
1. Faites maintenant correspondre cette nouvelle source de données aux événements personnalisés que nous avons créés dans [Configurer les Événements](/help/admin/admin/c-success-events/t-success-events.md)de réussite.

   ![Mappage](assets/data-source-mapping.png)

1. Sélectionnez les dimensions de donnéesCochez la case en regard de Codes de suivi et cliquez sur **[!UICONTROL Suivant]**.
1. Faites correspondre les Dimensions de données.
Faites correspondre la dimension (attribut) de données importées à l’attribut Adobe Analytics dans lequel vous souhaitez la stocker. Il peut s&#39;agir d&#39;une dimension standard ou d&#39;un eVar. Une fois que vous avez cliqué sur **[!UICONTROL Suivant]**, les mappages résultants s’affichent dans le résumé :

   ![Résumé](assets/data-source-summary.png)

1. Cliquez sur **[!UICONTROL Enregistrer]**.
1. Cliquez sur **[!UICONTROL Télécharger]** pour télécharger le fichier de modèle pour cette source de données.
Le nom de fichier correspond au type de source de données que vous avez initialement spécifié, à savoir, dans ce cas, &quot;Modèle de service générique de paiement par clic.txt&quot;.
1. Ouvrez le modèle dans votre éditeur de texte favori.
Le fichier est déjà renseigné avec les mesures et les dimensions et leurs correspondances.

## Exportation de données PPC et téléchargement vers Analytics

Les étapes similaires à celles-ci fonctionnent pour les mots-clés Google, MSN, Yahoo et d’autres comptes PPC.

### Exportation des données

1. Connectez-vous à votre compte PPC et créez un rapport ou exportez-le.
Assurez-vous que l’exportation comprend les champs suivants : date, URL de destination (landing page), impressions, clics et coût. L’exportation peut inclure d’autres champs, mais vous allez les supprimer en suivant les étapes ci-dessous.
1. Si possible, enregistrez le rapport dans un fichier `.csv` délimité par des tabulations. Il sera ainsi plus facile de travailler dans les étapes suivantes.
1. Ouvrez le fichier dans Microsoft Excel.

### Modifier le fichier dans Microsoft Excel

1. Dans Microsoft Excel, supprimez toutes les colonnes autres que celles mentionnées ci-dessus.
1. Supprimez toutes les lignes supplémentaires au-dessus.
1. Pour isoler les codes de suivi des URL de destination :
a. Copiez et collez les données de toutes les colonnes.
b. Cliquez sur **[!UICONTROL Données > Texte en colonnes]**.
c. À l’étape 1 de l’assistant, assurez-vous que **[!UICONTROL Délimité]** est sélectionné et cliquez sur **[!UICONTROL Suivant]**.
d. A l’étape 2 de l’assistant, spécifiez le délimiteur en fonction de la manière dont vous avez créé vos URL (ou ? ou &amp;) et cliquez sur **[!UICONTROL Suivant]**.
e. À l’étape 3 de l’assistant, prévisualisation vos données et vérifiez que l’une des colonnes est &quot;trackingcodename=trackingcode&quot;. Si vous disposez de variables supplémentaires, répétez ces étapes (en utilisant &amp; comme délimiteur).
f. Supprimez toutes les colonnes, à l’exception des codes de suivi, des impressions, des clics et des coûts. Ajoutez une nouvelle colonne appelée Date et organisez vos colonnes dans l’ordre suivant : Date : Code de suivi :: Impressions : Clics :: Coût.
1. Ajoutez ces données au modèle que vous avez téléchargé dans la section &quot;Configurer les sources de données&quot; ci-dessus.
Vous êtes maintenant prêt à télécharger le fichier.

### Télécharger le fichier vers Adobe Analytics par FTP

Revenez à l’Assistant Source de données pour obtenir des instructions et téléchargez le fichier par FTP :

![Télécharger FTP](assets/upload-ftp.png)

## Créer des mesures calculées

Il sera utile d&#39;Ajouter les mesures calculées lors des décisions de paiement par clic.

Par exemple, vous pouvez ajouter ces mesures [](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=en#calculated-metrics)calculées :

| Nom | Formule | Type de mesure | Description |
| --- | --- | --- | --- |
| Pages vues par visite | Pages vues / Visites | Numérique | Lorsqu’elle est appliquée au niveau d’un site, indique le nombre moyen de pages par visite. Lorsqu’elle est appliquée dans le rapport Pages les plus populaires, indique le nombre moyen de fois où une page particulière a été affichée par visite. |
| Valeur de commande moyenne | Recettes / Commandes | Devise | Indique les recettes moyennes par commande. |
| Recettes par visite | Recettes / Visite | Devise | Affiche les recettes moyennes par visite. |
| Taux de clics publicitaires (CTR) | Clics/impressions | Numérique | Mesurez le ratio de clics par rapport aux impressions d’une campagne de marketing en ligne ou par courriel. |
| Profit | Recettes - Coût | Devise | Affiche les recettes d’une campagne moins le coût. |
| Bénéfice par impression (ppp) | (Recettes - Coût)/Impression | Devise | Indique le montant des recettes générées chaque fois qu&#39;une publicité s&#39;affichait, équilibré par le coût. |
| Retour sur dépenses publicitaires (RSDP) | Montant des ventes/dépenses publicitaires | Devise | (RSI) Représente les dollars gagnés par dollar dépensé pour la publicité correspondante. |

## Configuration et exécution des rapports

L’étape finale consiste à ajouter les mesures de source de données et les mesures calculées au rapport Code de suivi et à approfondir l’analyse d’une campagne afin d’obtenir une vue immédiate des performances de chaque groupe publicitaire.

1. Dans **[!UICONTROL Adobe Analytics > Rapports]**, sélectionnez la suite de rapports dans laquelle vous avez importé des sources de données.
1. Accédez à **[!UICONTROL Rapports > Campagnes > Code de suivi > Code]** de suivi.
1. Sélectionnez la plage de dates.
1. Cliquez sur **[!UICONTROL Mesures > Ajouter]** et ajoutez vos mesures de source de données (Clics, Impressions, Coût total) à partir de la liste des mesures standard.
1. Faites de même pour les mesures calculées que vous avez ajoutées. Le rapport sera mis à jour à mesure que vous ajouterez des mesures.
