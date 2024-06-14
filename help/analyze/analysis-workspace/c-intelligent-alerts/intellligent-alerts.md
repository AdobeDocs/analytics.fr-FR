---
description: Le nouveau système d’alertes intelligentes permet de contrôler plus précisément les alertes et intègre la détection des anomalies au système d’alerte.
title: Alertes intelligentes - Aperçu
feature: Alerts
role: User, Admin
exl-id: 49d47896-bf93-4960-b647-2765c935eb25
source-git-commit: a012aca08740428671f216793dbd12aa15f21448
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 52%

---

# Alertes intelligentes - Aperçu

Les alertes intelligentes (ou simplement les &quot;alertes&quot;) dans Adobe Analytics vous permettent d’être averti immédiatement en cas d’événements anormaux dans vos données.

Vous pouvez définir des alertes à déclencher en fonction de seuils d’anomalie, de pourcentages modifiés ou de points de données spécifiques. Les alertes fournissent des contrôles granulaires qui s’intègrent à [Détection des anomalies](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md), ce qui se déclenche lorsque vous en avez le plus besoin.

Grâce aux alertes intelligentes, vous pouvez :

* créer des alertes d’après les anomalies (seuils de 90 %, 95 %, 99 %, 99,75 % et 99,90 % ; % de changement ; au-dessus/au-dessous) ;
* prévisualiser le nombre de fois où une alerte sera déclenchée ;
* envoyer des alertes par courrier électronique ou par SMS, avec des liens vers des projets Analysis Workspace générés automatiquement ;
* créer des alertes « empilées » qui présentent plusieurs mesures dans une seule alerte

Le tutoriel vidéo suivant présente un aperçu de base des alertes : [Alertes intelligentes](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=fr) (5:34)

## Recherche en amont des alertes par anomalies

Si une alerte utilise la détection des anomalies, la période de formation varie en fonction de la granularité sélectionnée pour l’alerte.

* Granularité mensuelle : 15 mois + même période l’an dernier
* Granularité hebdomadaire : 15 semaines + même période l’an dernier
* Granularité quotidienne : 35 jours + même période l’an dernier
* Granularité horaire : 336 heures

Pour plus d’informations, voir [Techniques statistiques de la détection des anomalies](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).

## Créer des alertes

Pour plus d’informations sur la création d’alertes dans Adobe Analytics, voir [Créer des alertes](/help/analyze/analysis-workspace/c-intelligent-alerts/alert-builder.md).

>[!IMPORTANT]
>
>L’utilisation de données horodatées pour créer des alertes peut entraîner un déclenchement incorrect des alertes. Adobe recommande d’utiliser des données non horodatées pour les alertes intelligentes.

## Gestion des alertes

Vous pouvez gérer les alertes existantes dans le gestionnaire d’alertes. Vous pouvez effectuer diverses tâches de gestion sur les alertes, telles que le balisage, le changement de nom, la suppression, etc.

Pour plus d’informations sur la gestion des alertes existantes dans Adobe Analytics, voir [Gestion des alertes](/help/analyze/analysis-workspace/c-intelligent-alerts/alert-manager.md).
