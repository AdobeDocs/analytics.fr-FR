---
description: Découvrez comment utiliser les alertes pour un contrôle granulaire des notifications et leur intégration à la détection des anomalies.
title: Vue d’ensemble des alertes
feature: Alerts
exl-id: 1b23211e-7632-4b33-a27d-c58b3bbbbab1
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 96%

---

# Vue d’ensemble des alertes

Les alertes dans Journey Analytics envoient un avertissement en fonction des modifications de pourcentages ou de points de données spécifiques.

Selon votre package Adobe Analytics, vous pouvez également déclencher des alertes en fonction des seuils d’anomalie. Ces alertes, également appelées « alertes intelligentes », fournissent des contrôles granulaires qui s’intègrent à la [Détection des anomalies](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) et se déclenchent lorsque vous en avez le plus besoin.

Grâce aux alertes, vous pouvez effectuer ce qui suit :

* prévisualiser le nombre de fois où une alerte sera déclenchée ;
* envoyer des alertes par courrier électronique ou par SMS, avec des liens vers des projets Analysis Workspace générés automatiquement ;
* créer des alertes « empilées » qui présentent plusieurs mesures dans une seule alerte
* Créer des alertes en fonction des anomalies (seuils de 90 %, 95 %, 99 %, 99,75 % et 99,9 % ; pourcentage de modification ; supérieur/inférieur) (disponible uniquement pour les clientes et clients Adobe Analytics avec un forfait Select, Prime ou Ultimate)

Le tutoriel vidéo suivant présente un aperçu de base des alertes : [Alertes](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=fr) (5:34)

## Recherche en amont des alertes par anomalies

>[!NOTE]
>
>L’utilisation d’alertes avec détection des anomalies (également appelées _Alertes intelligentes_) n’est disponible que pour les organisations qui disposent d’un forfait Adobe Analytics Prime ou Ultimate.

Si une alerte utilise la détection des anomalies, la période de formation varie en fonction de la granularité sélectionnée pour l’alerte.

* Granularité mensuelle : 15 mois + même période l’an dernier
* Granularité hebdomadaire : 15 semaines + même période l’an dernier
* Granularité quotidienne : 35 jours + même période l’an dernier
* Granularité horaire : 336 heures

Pour en savoir plus, consultez [Techniques statistiques utilisées dans la détection des anomalies](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).

## Créer des alertes

Pour plus d’informations sur la création d’alertes dans Adobe Analytics, voir [Créer des alertes](/help/components/alerts/alert-builder.md).

>[!IMPORTANT]
>
>L’utilisation de données horodatées pour créer des alertes peut entraîner un déclenchement incorrect des alertes. Adobe recommande d’utiliser des données non horodatées pour les alertes.

## Gérer les alertes

Vous pouvez gérer les alertes existantes dans le gestionnaire d’alertes. Vous pouvez effectuer différentes tâches de gestion sur les alertes, telles que le balisage, le changement de nom, la suppression, etc.

Pour plus d’informations sur la gestion des alertes existantes dans Adobe Analytics, voir [Gérer les alertes](/help/components/alerts/alert-manager.md).
