---
description: Découvrez comment utiliser les alertes pour un contrôle granulaire des notifications et leur intégration à la détection des anomalies.
title: Vue d’ensemble des alertes
feature: Alerts
exl-id: 1b23211e-7632-4b33-a27d-c58b3bbbbab1
TQID: 'https://experienceleague.adobe.com/FDzJzBjxMc-EkhW0k0NiENt-g53sRnzXQDs1XQWFseI'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b0ca67c6-0a35-482c-ad91-baac1bcb26d6id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 435
ht-degree: 53%

---

# Vue d’ensemble des alertes

Les alertes dans Journey Analytics envoient un avertissement en fonction des modifications de pourcentages ou de points de données spécifiques.

Selon votre package Adobe Analytics, vous pouvez également déclencher des alertes en fonction des seuils d’anomalie. Ces alertes (également appelées *Alertes intelligentes*) fournissent des commandes granulaires qui s’intègrent à la [Détection des anomalies](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) et se déclenchent lorsque vous en avez le plus besoin.

Grâce aux alertes, vous pouvez effectuer ce qui suit :

* Prévisualisez la fréquence de déclenchement d’une alerte.
* Envoyer des alertes par e-mail ou par SMS, avec des liens pour générer automatiquement les projets Analysis Workspace.
* Créez des alertes *empilées* qui capturent plusieurs mesures dans une seule alerte.
* Créer des alertes en fonction de :
   * Anomalies des mesures qui existent, sont supérieures ou inférieures aux valeurs de seuil attendues.

     [Détection des anomalies](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) crée une valeur attendue ainsi qu’une limite supérieure et inférieure à l’aide des données historiques. Si la valeur de la mesure réelle dépasse la limite supérieure ou est inférieure à la limite inférieure définie comme valeur de seuil, cet événement est considéré comme une anomalie au niveau de confiance du seuil et déclenche l’alerte. Un seuil plus élevé (par exemple : 99 % ou 99,9 %) implique une bande plus large, ce qui entraîne moins d’alertes provoquées par des anomalies plus extrêmes. Un seuil inférieur (par exemple : 90 %) implique une bande plus étroite, ce qui entraîne plus d’alertes provoquées par des anomalies moins extrêmes.
   * Modification des mesures selon un pourcentage spécifique.
   * Mesures supérieures, inférieures ou égales à une valeur spécifique. (disponible uniquement pour les clients Adobe Analytics avec un package Select, Prime ou Ultimate)

Ce [tutoriel vidéo](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/data-science/intelligent-alerts) fournit un aperçu de base des alertes.


## Recherche en amont des alertes par anomalies

>[!NOTE]
>
>L’utilisation d’alertes avec détection des anomalies (également appelées _Alertes intelligentes_) n’est disponible que pour les organisations qui disposent d’un package Adobe Analytics Prime ou Ultimate.

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
