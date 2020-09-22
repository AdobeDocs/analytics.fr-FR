---
title: Comparaison des différentes méthodes d’exclusion des robots
description: Permet de comparer différentes méthodes d’exclusion des robots.
translation-type: tm+mt
source-git-commit: 76ee4a8db49765590e7cca864d6d4b152d7ba112
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 19%

---


# Comparaison des différentes méthodes d’exclusion des robots

Le tableau suivant montre les différentes méthodes d’exclusion des robots et la façon dont ils se empilent les uns contre les autres.

| Méthode | Règles de robots | Exclure par adresse IP | Attributs du client | Segmentation | Évaluation tierce + segmentation | Supprimer les appels au serveur &#x200B; &#x200B; pour les robots à l’exécution | Règle DB VISTA personnalisée |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **Description de la méthode d’exclusion des données** | &#x200B; Exclure en fonction de l’agent utilisateur, de l’adresse IP ou de la plage d’adresses IP | Adresse IP | &#x200B; Indicateur dans les attributs du client qui identifie l&#39;ECID comme bot | &#x200B; critères d’un segment Analytics qui identifie les robots connus en fonction du comportement des robots | &#x200B; tiers, tel que [Perimeter X](https://www.perimeterx.com) ou [Akamai Bot Manager](https://www.akamai.com/us/en/products/security/bot-manager.jsp) , attribue à chaque vue de page un score indiquant la probabilité qu’il s’agisse d’un robot. La note est envoyée dans Analytics et les segments peuvent être utilisés pour filtrer les données en fonction de la note. | &#x200B; logique côté client empêche l’exécution de l’appel au serveur Analytics pour les robots. | &#x200B; une règle VISTA déplacera le trafic des robots qui répondent à certains critères vers une suite de rapports distincte. |
| **&#x200B; noms de robots sont disponibles pour le rapports ?** | Oui | Non | Non | Non | Non | Non | Oui |
| **&#x200B; Est-il possible de voir quelles pages sont visitées par des robots ?** | Oui | Non | Non | Non | Oui | Non | Oui |
| &#x200B;**Incurs le coût d&#39;appel du serveur pour les robots ?** | Oui | Oui | Oui | Oui | Oui | Non | Oui |
| **Données de robots disponibles dans les flux de données ?** | Non | Non | Oui | Oui | Oui | Non | Oui |
| **Capacité à &#x200B; signaler le trafic des robots comme s’il s’agissait d’appels au serveur ?** | Non | Non | Oui | Oui | Oui | Oui | Non |
| **Peut-on supprimer rétroactivement des données d&#39;un jeu de données ?** | Non | Non | &#x200B; Oui, une fois les ID déclarés implémentés | Oui | Oui, une fois les scores mis en oeuvre | Non | Non |
| **Les critères sont-ils soumis à des limites uniques ?** | Non | Non | Non | Oui | Non | Non | Non |
| **Est-&#x200B; sujet à des coûts supplémentaires ?** | Non | Non | &#x200B; peut-être, selon le SKU d’Analytics | Non | Oui | Non | &#x200B; Oui - coût d&#39;implémentation et de maintenance d&#39;une règle VISTA |
