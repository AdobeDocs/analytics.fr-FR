---
description: Le nouveau système d’alertes intelligentes permet de contrôler plus précisément les alertes et intègre la détection des anomalies au système d’alerte.
title: Alertes intelligentes - Aperçu
feature: Alerts
role: User, Admin
exl-id: 49d47896-bf93-4960-b647-2765c935eb25
source-git-commit: 10ae8213b8745439ab5968853f655a1176b8c38a
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 84%

---

# Alertes intelligentes - Aperçu

La fonction Alertes intelligentes permet de contrôler plus précisément les alertes et intègre la détection des anomalies au système d’alerte.

Voici un tutoriel vidéo sur les [Alertes intelligentes](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=fr) (5:34)

## Aperçu

Les nouveaux Générateur d’alertes et Gestionnaire d’alertes d’Analysis Workspace remplacent la fonction des alertes des Reports &amp; Analytics. Grâce aux alertes intelligentes, vous pouvez :

* créer des alertes d’après les anomalies (seuils de 90 %, 95 %, 99 %, 99,75 % et 99,90 % ; % de changement ; au-dessus/au-dessous) ;
* prévisualiser le nombre de fois où une alerte sera déclenchée ;
* envoyer des alertes par courrier électronique ou par SMS, avec des liens vers des projets Analysis Workspace générés automatiquement ;
* créer des alertes « empilées » qui présentent plusieurs mesures dans une seule alerte

Vous pouvez accéder au Générateur d’alertes de quatre façons :

| Méthode | Détails |
| --- | --- |
| Accédez directement au Générateur d’alertes | **[!UICONTROL Composants]** > **[!UICONTROL Alertes]** |
| Utilisation du raccourci clavier dans Workspace | `Ctrl + Shift + A` (Windows) ou `Cmd + Shift + A` (Mac) |
| Sélectionnez une ou plusieurs lignes de tableau à structure libre | Cliquez avec le bouton droit et sélectionnez **[!UICONTROL Créer une alerte d’après la sélection]**. Cela ouvre la fenêtre [!UICONTROL Générateur d’alertes] et préremplit les mesures et filtres appropriés appliqués à partir du tableau. Vous pouvez modifier l’alerte si nécessaire. ![Création d’une alerte d’après la sélection](assets/create-alert-from-selection.png) |
| Dans un rapport Reports &amp; Analytics | Accédez à  **[!UICONTROL Plus]** > **[!UICONTROL Ajouter une alerte]** . Le Générateur d’alertes s’ouvre, puis les mesures et filtres appropriés sont préremplis à partir du rapport. Vous pouvez modifier l’alerte si nécessaire. ![Ajouter une alerte](assets/add-alert.png) |

Les seuils (exprimé en pour cent) sont des écarts types. Par exemple, 95 % = 2 écarts types et 99 % = 3 écarts types. Selon la granularité temporelle choisie,   [différents modèles](../virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md) sont utilisés pour calculer à quel point chaque donnée s’écarte de la norme (le nombre d’écarts types). Si vous définissez un seuil inférieur (90 %, par exemple), vous obtenez davantage d’anomalies qu’avec un seuil plus élevé (99,75 %).

>[!IMPORTANT]
>
>L’utilisation de données horodatées pour créer des alertes peut entraîner un déclenchement incorrect des alertes. Adobe recommande d’utiliser des données non horodatées pour les alertes intelligentes.

## Recherche en amont des alertes par anomalies

Si une alerte utilise la détection des anomalies, la période de formation varie en fonction de la granularité sélectionnée pour l’alerte.

* Granularité mensuelle : 15 mois + même période l’an dernier
* Granularité hebdomadaire : 15 semaines + même période l’an dernier
* Granularité quotidienne : 35 jours + même période l’an dernier
* Granularité horaire : 336 heures

Pour en savoir plus, voir [Techniques statistiques de la détection des anomalies](../virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md).
