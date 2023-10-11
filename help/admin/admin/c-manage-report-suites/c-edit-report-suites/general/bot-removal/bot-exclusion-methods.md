---
title: Comparaison de différentes méthodes d’exclusion des robots
description: Permet de comparer différentes méthodes d’exclusion des robots.
exl-id: c54ba98a-b396-479e-bfe8-dc6211b26f61
feature: Bot Removal
source-git-commit: 266cf18050d60f08f7e170c56453d1e1d805cb7b
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 100%

---

# Comparaison de différentes méthodes d’exclusion des robots

Le tableau suivant montre les différentes méthodes d’exclusion des robots et leur fonctionnement les unes par rapport aux autres.

| Méthode | Règles de robots | Exclure par adresse IP | Attributs du client | Segmentation | Notation tierce + segmentation | Suppression des appels au serveur pour les robots au moment de l’exécution | Règle DB VISTA personnalisée |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **Description de la méthode d’exclusion des données** | Exclusion basée sur l’agent-utilisateur, l’adresse IP ou la plage d’adresses IP | Adresse IP | Indicateur des attributs du client qui identifie l’ECID comme un robot | Critères d’un segment Analytics qui identifie les robots connus en fonction de leur comportement | Un tiers, tel que [Perimeter X](https://www.perimeterx.com) ou [Akamai Bot Manager](https://www.akamai.com/fr/fr/products/security/bot-manager.jsp), attribue à chaque page vue un score relatif à sa probabilité d’être un robot. La note est envoyée dans Analytics et les segments peuvent être utilisés pour filtrer les données en fonction de celle-ci. | La logique côté client empêche l’exécution de l’appel au serveur Analytics pour les robots. | Une règle VISTA déplace le trafic des robots qui répondent à certains critères vers une suite de rapports distincte. |
| **Les noms de robots sont-ils disponibles pour le compte rendu des performances ?** | Oui | Non | Non | Non | Non | Non | Oui |
| **Est-il possible de voir quelles pages sont visitées par des robots ?** | Oui | Non | Non | Non | Oui | Non | Oui |
| **Cela engendre-t-il des frais d’appel au serveur pour les robots ?** | Oui | Oui | Oui | Oui | Oui | Non | Oui |
| **Les données de robots sont-elles disponibles dans les flux de données ?** | Non | Non | Oui | Oui | Oui | Non | Oui |
| **Est-il possible de signaler le trafic des robots comme s’il s’agissait d’appels au serveur ?** | Non | Non | Oui | Oui | Oui | Non | Non |
| **Peut-on supprimer rétroactivement des données d’un jeu de données ?** | Non | Non | Oui, une fois que les ID déclarés sont implémentés | Oui | Oui, une fois que les notes sont implémentées | Non | Non |
| **Les critères font-ils l’objet de limites uniques ?** | Non | Non | Non | Oui | Non | Non | Non |
| **Cela entraîne-t-il des frais supplémentaires ?** | Non | Non | Peut-être, en fonction du SKU d’Analytics | Non | Oui | Non | Oui, les frais d’implémentation et de maintenance d’une règle VISTA |
