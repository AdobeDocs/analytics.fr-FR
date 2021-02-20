---
description: valeur nulle
title: Heure de traitement des sources de données
uuid: d7cd679a-f9e3-4740-87cf-6171f3fe5cd9
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 100%

---


# Heure de traitement des sources de données

>[!NOTE]
>Toute période de traitement des données doit être considérée comme approximative et ne constitue pas un accord de niveau de service (SLA).

L’heure de traitement des sources de données varie comme suit :

* Données de la journée en cours : le traitement s’achève environ 2 heures après le chargement des données.
* Données du jour précédent : le traitement s’achève environ 3 heures après le chargement des données.

Le temps de traitement augmente d’environ 1 heure pour chaque journée de chargement supplémentaire, jusqu’à 17 heures au maximum.

Si, par exemple, vous chargez des données du jour précédent, elles seront visibles dans Analytics dans 2 heures environ. Si vous chargez des données du mois précédent, elles seront visibles dans Analytics dans 17 heures environ.
