---
title: Comparaison de différentes méthodes d’exclusion des robots
description: Permet de comparer différentes méthodes d’exclusion des robots.
exl-id: c54ba98a-b396-479e-bfe8-dc6211b26f61
role: Admin
feature: Bot Removal
TQID: https://experienceleague.adobe.com/zm3kClXgzo6sKMk20XKWGI66s2kjk4VZ2ohDj41JAes
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d095671a-1355-40aa-8b5f-06c33c68080bid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 327
ht-degree: 46%

---

# Comparaison de différentes méthodes d’exclusion des robots

Le tableau suivant présente les différentes méthodes d’exclusion des robots et leurs différences.

| Méthode | Règles de robots | Exclure par adresse IP | Attributs du client | Segmentation | Notation tierce + segmentation | Suppression des appels au serveur pour les robots au moment de l’exécution | Règle DB VISTA personnalisée |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **Description de la méthode d’exclusion des données** | Exclusion basée sur l’agent-utilisateur, l’adresse IP ou la plage d’adresses IP | Adresse IP | Indicateur dans les attributs du client qui identifie l’ECID comme un robot | Critères d’un segment Analytics qui identifie les robots connus en fonction de leur comportement | Un tiers, tel que [Perimeter X](https://www.perimeterx.com) ou [Akamai Bot Manager](https://www.akamai.com/fr/fr/products/security/bot-manager.jsp) attribue à chaque page vue un score relatif à sa probabilité d’être un robot. La note est envoyée dans Analytics et les segments peuvent être utilisés pour filtrer les données en fonction de celle-ci. | La logique côté client empêche l’exécution de l’appel au serveur Analytics pour les robots. | Une règle VISTA déplace le trafic des robots qui répondent à certains critères vers une suite de rapports distincte. |
| **Les noms de robots sont-ils disponibles pour la création de rapports ?** | Oui | Non | Non | Non | Non | Non | Oui |
| **Est-il possible de voir quelles pages sont visitées par des robots ?** | Oui | Non | Non | Non | Oui | Non | Oui |
| **Cela engendre-t-il des frais d’appel au serveur pour les robots ?** | Oui | Oui | Oui | Oui | Oui | Non | Oui |
| **Les données de robots sont-elles disponibles dans les flux de données ?** | Non | Non | Oui | Non | Oui | Non | Oui |
| **Est-il possible de signaler le trafic des robots comme s’il s’agissait d’appels au serveur ?** | Non | Non | Oui | Oui | Oui | Non | Non |
| **Peut-on supprimer rétroactivement des données d’un jeu de données ?** | Non | Non | Oui, une fois les identifiants déclarés implémentés | Oui | Oui, une fois que les notes sont implémentées | Non | Non |
| **Les critères font-ils l’objet de limites uniques ?** | Non | Non | Non | Oui | Non | Non | Non |
| **Cela entraîne-t-il des frais supplémentaires ?** | Non | Non | Peut-être, en fonction du SKU d’Analytics | Non | Oui | Non | Oui - coût de mise en œuvre et de maintenance d’une règle VISTA |
