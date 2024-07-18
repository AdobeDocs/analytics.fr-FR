---
title: Résolution des problèmes liés aux heures de remise des demandes de Data Warehouse
description: Identifiez les problèmes potentiels liés à une demande de Data Warehouse qui peuvent prolonger les délais de remise.
feature: Data Warehouse
exl-id: eed4d172-fffd-453f-ab5b-0fc2a79d5bd0
source-git-commit: fc6a2deabaf2012cefebf4864db19aef1825adf2
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 61%

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

## Modifier les demandes pour accélérer la diffusion

Si les demandes de Data Warehouse prennent constamment du temps, envisagez de modifier vos demandes. La modification d’une requête est le seul moyen d’accélérer la remise d’une requête de Data Warehouse.

Pour accélérer la diffusion d&#39;une demande de Data Warehouse, vous pouvez la modifier de l&#39;une des manières suivantes :

* **Utilisation d’un segment contenant un plus petit échantillon de données** : moins une demande utilise de données, plus le renvoi du rapport est accéléré.
* **Exécuter les requêtes par incréments de 14 jours ou moins** : les requêtes plus petites sont traitées plus rapidement que les requêtes plus volumineuses.
* **Utiliser moins de ventilations :** De nombreuses ventilations dans une requête augmentent de manière exponentielle le temps nécessaire au traitement.

## Utilisation d’une autre méthode

Si vous devez obtenir ces types de rapports plus rapidement, envisagez les alternatives suivantes :

* **Analysis Workspace** : bien qu’un nombre illimité d’éléments de dimension ne soit pas disponible, presque tous les autres cas d’utilisation fournis par Data Warehouse sont inclus.
* **Flux de données** : récupère quotidiennement toutes les données brutes d’une suite de rapports et les envoie vers une destination cloud. Vous pouvez ensuite importer les données dans votre propre base de données et exécuter des requêtes afin d&#39;obtenir les données dont vous avez besoin.
* **Solution de services d’ingénierie personnalisée** : les services d’ingénierie d’Adobe peuvent fournir une solution personnalisée à votre entreprise moyennant des frais supplémentaires. Pour plus d’informations, contactez votre équipe de compte d’Adobe.
