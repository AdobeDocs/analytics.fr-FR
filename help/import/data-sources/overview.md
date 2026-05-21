---
title: Présentation des sources de données
description: Importez des données dans Adobe Analytics à l’aide de fichiers externes.
exl-id: 5ec8bc51-dfd2-497c-aebc-a32d87efc97e
feature: Data Sources
role: Admin
TQID: https://experienceleague.adobe.com/AOl1PUYf4TL0FrYB8eHL-JLiWvz6ixJYKUPpIZEFqj8
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 327
ht-degree: 4%

---

# Présentation des sources de données

Les sources de données Adobe Analytics permettent d’importer des données en ligne et hors ligne supplémentaires pour la création de rapports. Ils sont précieux pour aider à comprendre les aspects de votre entreprise en dehors de votre site web et la manière dont ils interagissent avec votre site. Le workflow général d’utilisation des sources de données comprend les étapes suivantes :

1. Votre entreprise collecte des données à partir d’autres sources. Il s’agit par exemple des données de pré-clic, des données du centre d’appels ou des informations sur les transactions effectuées en dehors de votre site.
1. Les données sont formatées de manière à ce qu’Adobe Analytics puisse les comprendre à l’aide d’un fichier texte délimité par des tabulations.
1. Vous téléchargez le fichier texte sur un site FTP fourni par Adobe, ainsi qu’un fichier `.fin` associé.
1. Adobe ingère le fichier texte et affiche ces données avec les dimensions et les mesures collectées sur votre site.

Adobe propose deux types généraux de sources de données. Tous les modèles de source de données sont basés sur l’un de ces deux types :

* **Source de données de résumé** : permet d’importer facilement des données de haut niveau dans Adobe Analytics. Vous spécifiez la date et l’heure, la valeur de la variable et les mesures associées. Ces mesures pour chaque élément de dimension sont ensuite augmentées en conséquence. Il s’avère utile si vous souhaitez afficher côte à côte des données hors ligne et en ligne. Cependant, il ne lie pas les données en ligne et hors ligne.
* **Source de données ID de transaction** : si un accès envoyé par AppMeasurement et une ligne de sources de données contiennent des ID de transaction correspondants, les valeurs de dimension et de mesure de la source de données s’ajoutent à cet accès.

**Les sources de données à traitement complet** ne sont plus proposées en tant que type de source de données à compter du 25 mars 2021. Consultez l’[annonce de fin de vie](full-processing-eol.md) pour plus d’informations.

Adobe propose également l’[API Data sources](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/), qui vous permet de créer des sources de données et de charger des données sans utiliser l’interface utilisateur du produit ou un emplacement FTP.

## Étapes suivantes

[Prise en main des sources de données](getting-started.md) : chargez une source de données simple vers une suite de rapports de développement.
