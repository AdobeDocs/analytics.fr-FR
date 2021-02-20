---
description: Dans Analysis Workspace, vous pouvez afficher et analyser les anomalies de données de manière contextuelle.
title: Détection des anomalies - Aperçu
uuid: 991fde08-198c-4410-9606-d5a4f3dd8339
translation-type: tm+mt
source-git-commit: 56ca9fa36db9d7dd126808280ba17f29f4b787d9
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 90%

---


# Détection des anomalies - Aperçu

Dans Analysis Workspace vous pouvez afficher et analyser les anomalies de données de manière contextuelle.

[Didacticiel](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace.html)  vidéo sur la détection des anomalies (4:53)

[Didacticiel](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/data-science/contribution-analysis-workspace.html)  vidéo sur l’Analyse des contributions (3:20)

>[!IMPORTANT]
>
>La détection des anomalies a été supprimée de l’ensemble de fonctionnalités Reports &amp; Analytics et est désormais disponible uniquement via Analysis Workspace. Remarque : les clients Adobe Analytics Select et Adobe Analytics Foundation ne profitent que d’une détection des anomalies « à granularité journalière » dans Workspace. Pour plus d’informations, voir [Autorisations pour la détection des anomalies et l’analyse des contributions](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md#section_9278D58F21A840AA9B1ED1BD07A1EF0A).

La détection des anomalies met à votre disposition une méthode statistique pour déterminer la modification d’une mesure donnée par rapport à des données antérieures.

La détection des anomalies permet de séparer les « signaux réels » du « bruit » et d’identifier ensuite les facteurs qui ont conduit à ces signaux ou anomalies. En d’autres termes, cette fonction permet de distinguer les fluctuations statiques importantes de celles qui ne le sont pas. Vous pouvez alors identifier l’origine d’une anomalie. Vous recevez, en outre, des prévisions de mesures (IPC) fiables.

Voici quelques exemples d’anomalies dont vous pouvez rechercher l’origine :

* Forte chute de la valeur de commande moyenne
* Pic des commandes avec recettes faibles
* Pic ou diminution des inscriptions aux offres d’essai
* Forte diminution des affichages de pages d’entrée
* Pic des événements de mémoire tampon pour la vidéo
* Pic des faibles débits en bits pour la vidéo

La détection des anomalies et l’[analyse des contributions](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html) sont des processus de base d’Analysis Workspace. Vous pouvez exécuter l’analyse des contributions par rapport à n’importe quelle anomalie quotidienne, puis incorporer le résultat dans un projet Analysis Workspace.

L’algorithme de détection des anomalies d’Analysis Workspace inclut

* La prise en charge de la granularité horaire, hebdomadaire et mensuelle, en sus de la granularité quotidienne.
* La reconnaissance du caractère saisonnier et des jours fériés (Noël, par exemple).
