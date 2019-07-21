---
description: Informations sur le modèle .txt de sources de données.
seo-description: Informations sur le modèle .txt de sources de données.
seo-title: Référence du fichier d'importation
solution: Analytics
subtopic: Sources de données
title: Référence du fichier d'importation
topic: Développeur et mise en œuvre
uuid: cc 58 f 8 d 8-cb 6 e -4908-846 f -0 a 41 c 6 da 805 d
translation-type: tm+mt
source-git-commit: cce2c1c54f21244f856385aeaad811d89f2fda7f

---


# Référence du fichier d'importation

Informations sur le modèle .txt de sources de données.

Générez un modèle d’importation à l’aide de l’Assistant des sources de données. Le fichier d’importation Sources de données comprend les données suivantes :

* Un symbole dièse (#) identifie cette ligne comme un commentaire.
* Si nécessaire, vous pouvez ajouter d’autres commentaires au fichier.
* Un commentaire qui répertorie le titre du fichier du modèle.
* Un commentaire qui répertorie les noms de portée des données et de mesure externe spécifiés dans l’[!UICONTROL Assistant d’activation de la source de données].

Les titres de colonnes permettent d’identifier les données dans chaque colonne du fichier de source de données. Il existe trois types de titres de colonne :

**Date** : (requise) horodatage pour chaque ligne de données du fichier.

**Variables** : nom des variables de rapports associées aux portées de données de la source de données.

**Événements** : nom des événements associés aux mesures de la source de données.

Utilisez le modèle de source de données pour créer un fichier qui contient les données que vous souhaitez transférer. Lors de la création d’un fichier de source de données, pensez à ce qui suit :

* En fait, chaque ligne du fichier de source de données contient un enregistrement de données, où chaque enregistrement est composé d’une série de champs séparés par des tabulations. Les titres de colonne du modèle de source de données définissent l’ordre de ces champs. Par exemple :

   ```
     #Sample data file for mycorp_report_suite 
     #Imported data for ad impressions applied to Event 6
     Date     Tracking Code      Event 6 
     1/1/2009     NYT8453A      8754
     1/1/2009     WSJ4453B      9492
     1/1/2009     BHG44563      10553
     1/2/2009     NYT8453A      6452
     1/2/2009     WSJ4453B      7237
     1/2/2009     BHG44563      9031
   ```

* Si vous transférez plusieurs fichiers de données, la fonctionnalité Sources de données les charge dans l’ordre alphabétique. Les fichiers qui doivent être traités chronologiquement doivent être nommés de sorte que leur ordre alphabétique corresponde à leur ordre chronologique. Par exemple :

   ```
   log_2009-01-01_13:00.txt
   log_2009-01-01_13:15.txt
   log_2009-01-01_13:30.txt
   ```

* Pour accélérer le traitement de votre fichier de source de données, Adobe recommande l’agrégation des données d’événement (mesures) sur une seule ligne par date.

   Si, par exemple, votre fichier associe les données d’impression de publicité à l’événement 6, créez une seule ligne de données qui comprend le nombre total d’impressions de publicité pour chaque jour, plutôt que de créer une entrée de ligne distincte pour chaque impression de publicité survenue ce jour donné.
* Si vous devez transférer des données issues de dates antérieures à la date de création de votre suite de rapports, contactez le gestionnaire de votre compte afin de modifier la date la plus ancienne à laquelle vous pouvez exécuter des rapports.

**Fichier .FIN**

Une fois votre fichier de source de données renseigné, vous pouvez le transférer par FTP dans Analytics. Toutefois, un fichier supplémentaire est nécessaire pour que les données soient traitées : You will need to upload an empty text file with the same name of your data file, but with a [!DNL .fin] extension.

For example, if you upload a (tab-delimited) data file called [!DNL myproductdata.txt], you would also need to upload an empty text file called [!DNL myproductdata.fin]. Without the [!DNL .fin] file, data would never be processed.
