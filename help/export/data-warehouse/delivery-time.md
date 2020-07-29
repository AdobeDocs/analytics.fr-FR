---
title: Résolution des problèmes liés aux diffusions des demandes de Data warehouse
description: Déterminer les problèmes potentiels avec une demande de Data warehouse qui peut prolonger les diffusions.
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 0%

---


# Résolution des problèmes liés aux diffusions des demandes de Data warehouse

Une demande de Data warehouse donnée peut prendre de moins d&#39;une heure à plusieurs jours ou plus. Il est difficile d&#39;estimer le temps exact nécessaire au traitement d&#39;une demande en raison des facteurs suivants :

* Plage de dates de la demande
* Le volume de trafic reçu par votre suite de rapports au cours de la période demandée
* Nombre de règles d’un segment et les variables d’un segment utilisées
* Quantité de données incluses dans le segment
* Nombre de ventilations utilisées et nombre de valeurs uniques dans chaque ventilation
* Nombre de mesures utilisées
* Nombre de demandes simultanées en cours de traitement
* Règles VISTA, si elles sont configurées pour s’appliquer aux demandes de DataWarehouse

Si les demandes de data warehouse prennent régulièrement du temps, pensez à modifier vos demandes pour tenir compte des éléments suivants :

* **Utilisez un segment contenant un échantillon de données** plus petit : Moins une requête utilise de données, plus elle renvoie rapidement un rapport.
* **Exécutez les requêtes par incréments de 14 jours ou moins**: Les requêtes plus petites sont traitées plus rapidement que les requêtes plus volumineuses.
* **Utilisez moins de ventilations :** De nombreuses ventilations dans une demande de Data warehouse augmentent de manière exponentielle le temps nécessaire au traitement.

>[!IMPORTANT]
>
> *Il n&#39;existe aucun moyen d&#39;accélérer la diffusion d&#39;une demande de Data warehouse.*

Si vous avez besoin de ces types de rapports en temps opportun, envisagez les alternatives suivantes :

* **Analysis Workspace**: Bien qu’un nombre illimité d’éléments de dimension ne soit pas disponible, il inclut presque tous les autres cas d’utilisation fournis par le Data warehouse.
* **Flux** de données : Récupère quotidiennement toutes les données brutes d’une suite de rapports et les envoie à un site FTP. Vous pouvez ensuite importer ces données dans votre propre base de données et exécuter des requêtes pour obtenir les données que vous recherchez.
* **Solution** Custom Engineering Services : Les services d’ingénierie d’Adobe peuvent fournir une solution personnalisée à votre entreprise moyennant des frais supplémentaires. Pour plus d’informations, contactez le gestionnaire de compte de votre entreprise.
