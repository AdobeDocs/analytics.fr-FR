---
title: Présentation des sources de données
description: Importez des données dans Adobe Analytics à l’aide de fichiers externes.
exl-id: 5ec8bc51-dfd2-497c-aebc-a32d87efc97e
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 0%

---

# Présentation des sources de données

Les sources de données Adobe Analytics vous permettent d’importer des données en ligne ou hors ligne supplémentaires pour la création de rapports. Elles s’avèrent utiles pour comprendre les facettes de votre entreprise en dehors de votre site web et la manière dont elles interagissent avec votre site. Le workflow général d’utilisation des sources de données comprend les étapes suivantes :

1. Votre entreprise collecte des données à partir d’autres sources. Par exemple, les données de pré-clic, les données du centre d’appel ou les informations sur les transactions qui se sont produites en dehors de votre site.
1. Les données sont formatées de manière à ce qu’Adobe Analytics comprenne l’utilisation d’un fichier texte délimité par des tabulations.
1. Vous téléchargez le fichier texte sur un Adobe de site FTP fourni, ainsi qu’un fichier `.fin` associé.
1. Adobe ingère le fichier texte et affiche ces données avec les dimensions et les mesures collectées sur votre site.

Il existe deux types généraux de sources de données qui Adobe les offres. Tous les modèles de source de données sont basés sur l’un de ces deux types :

* **Source de données récapitulatives** : permet d’importer facilement des données de haut niveau dans Adobe Analytics. Vous spécifiez l’horodatage, la valeur de variable et les mesures associées. Ces mesures pour chaque élément de dimension sont alors augmentées en conséquence. Il est utile si vous souhaitez voir les données hors ligne et en ligne côte à côte. Cependant, il ne lie pas les données en ligne et hors ligne.
* **Source de données ID de transaction** : si un accès envoyé par AppMeasurement et une ligne de sources de données contiennent des ID de transaction correspondants, la dimension et les valeurs de mesure de la source de données sont ajoutées à cet accès.

**Les sources de données à traitement complet** ne sont plus proposées en tant que type de source de données à compter du 25 mars 2021. Pour plus d’informations, consultez l’ [annonce de fin de vie](full-processing-eol.md) .

Adobe propose également l’ [API Sources de données](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/), qui vous permet de créer des sources de données et de transférer des données sans utiliser l’interface utilisateur du produit ou un emplacement FTP.

## Étapes suivantes

[Prise en main des sources de données](getting-started.md) : téléchargez une source de données simple vers une suite de rapports de développement.
