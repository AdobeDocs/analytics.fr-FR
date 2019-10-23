---
description: Dans Analysis Workspace, vous pouvez afficher et analyser les anomalies de données de manière contextuelle.
seo-description: Dans Analysis Workspace, vous pouvez afficher et analyser les anomalies de données de manière contextuelle.
seo-title: Détection des anomalies - Aperçu
title: Détection des anomalies - Aperçu
uuid: 991fde08-198c-4410-9606-d5a4f3dd8339
translation-type: tm+mt
source-git-commit: ca9f1ed00295b556250894ae4e7fa377ef8a593d

---


# Détection des anomalies - Aperçu

Vous pouvez afficher et analyser les anomalies de données de manière contextuelle dans Analysis Workspace.

[Détection des anomalies sur YouTube](https://www.youtube.com/watch?v=krXyQCjXoeU&index=63&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (4:53)

[Analyse des contributions sur YouTube](https://www.youtube.com/watch?v=MbpeJIADtGk&index=64&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (3:20)

> [!IMPORTANT] La détection des anomalies n’est disponible que dans Analysis Workspace. Les clients Adobe Analytics Select et Foundation n’ont accès qu’à la détection des anomalies quotidienne de granularité dans Workspace. Pour plus d’informations, voir [Autorisations pour la détection des anomalies et l’analyse des contributions](../contribution-analysis/ca-tokens.md).

La détection des anomalies met à votre disposition une méthode statistique pour déterminer la modification d’une mesure donnée par rapport à des données antérieures.

La détection des anomalies permet de séparer les « signaux réels » du « bruit » et d’identifier ensuite les facteurs qui ont conduit à ces signaux ou anomalies. En d’autres termes, cette fonction permet de distinguer les fluctuations statiques importantes de celles qui ne le sont pas. Vous pouvez alors identifier l’origine d’une anomalie. Vous recevez, en outre, des prévisions de mesures (IPC) fiables.

Voici quelques exemples d’anomalies dont vous pouvez rechercher l’origine :

* Forte chute de la valeur de commande moyenne
* Pic des commandes avec recettes faibles
* Pic ou diminution des inscriptions aux offres d’essai
* Forte diminution des affichages de pages d’entrée
* Pic des événements de mémoire tampon pour la vidéo
* Pic des faibles débits en bits pour la vidéo

La détection des anomalies et l’[analyse des contributions](https://marketing.adobe.com/resources/help/en_US/analytics/contribution/ca_main.html) sont des processus de base d’Analysis Workspace. Vous pouvez exécuter l’analyse des contributions par rapport à n’importe quelle anomalie quotidienne, puis incorporer le résultat dans un projet Analysis Workspace.

L’algorithme de détection des anomalies d’Analysis Workspace inclut

* La prise en charge de la granularité horaire, hebdomadaire et mensuelle, en sus de la granularité quotidienne.
* La reconnaissance du caractère saisonnier et des jours fériés (Noël, par exemple).
