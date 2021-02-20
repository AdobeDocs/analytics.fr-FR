---
title: Résolution des problèmes liés aux heures de remise des demandes de Data Warehouse
description: Identifiez les problèmes potentiels liés à une demande de Data Warehouse qui peuvent prolonger les délais de remise.
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 100%

---


# Résolution des problèmes liés aux heures de remise des demandes de Data Warehouse

Une demande de Data Warehouse donnée peut prendre entre moins d’une heure et plusieurs jours, voire plus. L’estimation du délai exact de traitement d’une demande est difficile à réaliser en raison des facteurs suivants :

* la période de la demande ;
* le volume de trafic reçu par la suite de rapports au cours de la période demandée ;
* le nombre de règles d’un segment et les variables d’un segment utilisées ;
* la quantité de données incluses dans le segment ;
* le nombre de ventilations utilisées et le nombre de valeurs uniques dans chaque ventilation ;
* le nombre de mesures utilisées ;
* le nombre de demandes simultanées en cours de traitement ;
* les règles VISTA, si elles sont configurées pour s’appliquer aux demandes de Data Warehouse.

Si vous constatez que les demandes de Data Warehouse prennent toujours beaucoup de temps, envisagez de modifier vos demandes pour tenir compte des éléments suivants :

* **Utilisation d’un segment contenant un plus petit échantillon de données** : moins une demande utilise de données, plus le renvoi du rapport est accéléré.
* **Traitement de demandes par incréments de 14 jours ou moins** : les demandes moins volumineuses sont traitées plus rapidement que les demandes plus volumineuses.
* **Utilisation réduite des ventilations :** la présence de nombreuses ventilations dans une demande de Data Warehouse augmente de manière exponentielle le temps nécessaire au traitement.

>[!IMPORTANT]
>
> *Il n’existe aucun moyen d’accélérer la remise d’une demande de Data Warehouse.*

Si vous devez obtenir ces types de rapports plus rapidement, envisagez les alternatives suivantes :

* **Analysis Workspace** : bien qu’un nombre illimité d’éléments de dimension ne soit pas disponible, presque tous les autres cas d’utilisation fournis par Data Warehouse sont inclus.
* **Flux de données** : récupère quotidiennement toutes les données brutes d’une suite de rapports et les envoie à un site FTP. Vous pouvez ensuite importer ces données dans votre propre base de données et exécuter des requêtes pour obtenir les données que vous recherchez.
* **Solution de services d’ingénierie personnalisée** : les services d’ingénierie d’Adobe peuvent fournir une solution personnalisée à votre entreprise moyennant des frais supplémentaires. Pour plus d’informations à ce sujet, contactez le gestionnaire de compte de votre entreprise.
