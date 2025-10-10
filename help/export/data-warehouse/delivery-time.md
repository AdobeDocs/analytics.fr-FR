---
title: Résolution des problèmes liés aux délais de livraison des requêtes Data Warehouse
description: Identifiez les problèmes potentiels liés à une demande de Data Warehouse qui peuvent prolonger les délais de remise.
feature: Data Warehouse
exl-id: eed4d172-fffd-453f-ab5b-0fc2a79d5bd0
source-git-commit: d929e97a9d9623a8255f16729177d812d59cec05
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 59%

---

# Résolution des problèmes liés aux heures de remise des demandes de Data Warehouse

Une demande de Data Warehouse donnée peut prendre entre moins d’une heure et plusieurs jours, voire plus. L’estimation du délai exact de traitement d’une demande est difficile à réaliser en raison des facteurs suivants :

* la période de la demande ;
* le volume de trafic reçu par la suite de rapports au cours de la période demandée ;
* le nombre de règles d’un segment et les variables d’un segment utilisées ;
* la quantité de données incluses dans le segment ;
* le nombre de répartitions utilisées et le nombre de valeurs uniques dans chaque répartition ;
* le nombre de mesures utilisées ;
* le nombre de demandes simultanées en cours de traitement ;
* les règles VISTA, si elles sont configurées pour s’appliquer aux demandes de Data Warehouse.

## Modifier les requêtes pour accélérer la diffusion

Si les requêtes Data Warehouse prennent systématiquement beaucoup de temps, pensez à modifier vos requêtes. La modification d’une requête est le seul moyen d’accélérer la diffusion d’une requête Data Warehouse.

Pour accélérer la diffusion d’une requête Data Warehouse, vous pouvez la modifier de l’une des manières suivantes :

* **Utilisation d’un segment contenant un plus petit échantillon de données** : moins une demande utilise de données, plus le renvoi du rapport est accéléré.
* **Exécuter les requêtes par incréments de 14 jours ou moins** : les requêtes de petite taille sont traitées plus rapidement que les requêtes volumineuses.
* **Utiliser moins de répartitions :** de nombreuses répartitions dans une requête augmentent de manière exponentielle le temps de traitement.

## Utiliser une autre méthode

Si vous devez obtenir ces types de rapports plus rapidement, envisagez les alternatives suivantes :

* **Analysis Workspace** : bien qu’un nombre illimité d’éléments de dimension ne soit pas disponible, presque tous les autres cas d’utilisation fournis par Data Warehouse sont inclus.
* **Flux de données** : prend quotidiennement toutes les données brutes d’une suite de rapports et les envoie vers une destination cloud. Vous pouvez ensuite importer les données dans votre propre base de données et exécuter des requêtes afin d’obtenir les données dont vous avez besoin.
* **Solution de services d’ingénierie personnalisée** : les services d’ingénierie d’Adobe peuvent fournir une solution personnalisée à votre entreprise moyennant des frais supplémentaires. Pour plus d’informations, contactez l’équipe chargée de votre compte Adobe.
