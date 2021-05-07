---
title: Lissage intelligent des données
description: Découvrez comment le lissage intelligent des données analyse les tendances historiques afin de prédire la valeur d’une mesure au cours d’une période affectée.
feature: Outils AI
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: aa9f0a8f5b7b1780d0b0be729775c573e12caa35
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 1%

---

# Lissage intelligent des données

Dans de rares occasions, certains facteurs peuvent avoir un impact sur la qualité des données. Le trafic des robots, les modifications d’implémentation ou les interruptions de service peuvent tous avoir un impact sur l’intégrité des données collectées. Elles compliquent également l&#39;analyse sur la façon dont le événement peut avoir affecté l&#39;exhaustivité des données.

Le lissage intelligent des données est un prototype dans [Analytics Labs](/help/analyze/tech-previews/overview.md) qui peut aider à compléter cette vue en analysant les tendances historiques afin de prédire la valeur de toute mesure au cours de la période affectée. Le prototype applique des algorithmes d’apprentissage automatique élaborés pour tracer les valeurs attendues pour les mesures au cours de la période analysée.

## Exécution du lissage intelligent des données

1. Accédez à Adobe Analytics Labs :
   ![Labs](assets/labs.png)
1. Lancez le prototype de lissage des données intelligentes.
   ![Lancer le prototype](assets/intelligent-ds.png)
1. Ajoutez la mesure qui doit être analysée dans le tableau Structure libre. Le prototype ne fonctionne qu&#39;avec une granularité quotidienne, assurez-vous donc que la dimension du tableau est Day.
   ![Ajouter une mesure](assets/add-metric.png)
1. Choisissez une plage de dates plus large que la fenêtre du événement, mais assurez-vous qu’elle inclut le événement.
   ![Période](assets/date-range.png)
1. Cliquez sur l’icône d’engrenage de la mesure dans le tableau Structure libre.
   ![Icône d&#39;engrenage](assets/gear-icon.png)
1. Sous [!UICONTROL Paramètres des données], sélectionnez l&#39;option [!UICONTROL lissage des données].
   ![lissage des données](assets/column-setting.png)
1. Sélectionnez la plage de dates/dates correspondant au événement et cliquez sur [!UICONTROL Appliquer].
Assurez-vous que la plage de données pour le lissage des données est un sous-ensemble de la plage de dates sélectionnée pour le panneau. La mesure dans le tableau et le graphique est remplacée par les valeurs prédites.
   ![Valeurs prédites](assets/predictive-values.png)