---
title: Lissage des données intelligent
description: Découvrez comment le lissage intelligent des données analyse les tendances historiques afin de prédire la valeur d’une mesure au cours d’une période affectée.
feature: Outils d’IA
role: User, Admin
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 5%

---

# Lissage des données intelligent

Dans de rares occasions, certains facteurs peuvent avoir une incidence sur la qualité des données. Le trafic des robots, les modifications de mise en oeuvre ou les interruptions de service peuvent tous avoir un impact sur l’intégrité des données collectées. Elles compliquent également l’analyse de la manière dont l’événement peut avoir affecté l’exhaustivité des données.

Le lissage intelligent des données est un prototype d’[Analytics Labs](/help/analyze/tech-previews/overview.md) qui peut vous aider à compléter cette vue en analysant les tendances historiques afin de prédire la valeur de n’importe quelle mesure au cours de la période affectée. Le prototype applique des algorithmes avancés d’apprentissage automatique pour tracer les valeurs attendues pour les mesures au cours de la période en cours d’analyse.

## Exécution du lissage intelligent des données

1. Accédez à Adobe Analytics Labs :
   ![Labs](assets/labs.png)
1. Lancez le prototype de lissage des données intelligent.
   ![prototype de lancement](assets/intelligent-ds.png)
1. Ajoutez la mesure qui doit être analysée au tableau à structure libre. Le prototype ne fonctionne qu’avec une granularité quotidienne. Assurez-vous donc que la dimension du tableau est Jour.
   ![Ajouter une mesure](assets/add-metric.png)
1. Choisissez une période plus large que la fenêtre de l’événement, mais assurez-vous qu’elle inclut l’événement.
   ![Période](assets/date-range.png)
1. Cliquez sur l’icône d’engrenage de la mesure dans le tableau à structure libre.
   ![Icône représentant un engrenage](assets/gear-icon.png)
1. Sous [!UICONTROL Paramètres des données], sélectionnez l’option [!UICONTROL lissage des données].
   ![lissage des données](assets/column-setting.png)
1. Sélectionnez la plage de dates/dates correspondant à l’événement et cliquez sur [!UICONTROL Appliquer].
Assurez-vous que la période de lissage des données est un sous-ensemble de la période sélectionnée pour le panneau. Les mesures du tableau et du graphique sont remplacées par les valeurs prédites.
   ![Valeurs prédites](assets/predictive-values.png)