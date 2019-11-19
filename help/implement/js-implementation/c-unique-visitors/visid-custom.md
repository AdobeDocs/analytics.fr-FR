---
description: Vous pouvez implémenter une méthode personnalisée pour identifier les visiteurs en définissant la variable s.visitorID.
keywords: Analytics Implementation
solution: Analytics
title: Identifiant visiteur personnalisé
topic: Developer and implementation
uuid: 49881e27-0418-4ecf-a092-dcc3db923f40
translation-type: tm+mt
source-git-commit: edf88e40cae8b6886b04257f266666c13a37f88d

---


# Identifiant visiteur personnalisé

Vous pouvez implémenter une méthode personnalisée pour identifier les visiteurs en définissant la variable s.visitorID.

Vous pouvez utiliser un identifiant visiteur personnalisé sur des sites pour lesquels vous avez un moyen unique d’identifier les visiteurs. Il s’agit, par exemple, de l’identifiant généré lorsqu’un utilisateur se connecte à un site Web à l’aide de son nom d’utilisateur et de son mot de passe.

Si vous pouvez dériver et gérer les [!UICONTROL identifiants visiteur] de vos utilisateurs, vous pouvez utiliser les méthodes suivantes pour définir l’identifiant :

| Méthode | Description |
|---|---|
| [Variable s.visitorID](/help/implement/js-implementation/page-variables/page-variables.md) | Si JavaScript est utilisé dans le navigateur, ou si vous utilisez toute autre bibliothèque AppMeasurement, vous pouvez définir l’identifiant visiteur dans une variable de collecte de données. |
| Paramètre de chaîne de requête dans la demande d’image | Elle permet de transmettre l’[!UICONTROL identifiant visiteur] à Adobe via le paramètre de [!UICONTROL chaîne de requête vide] dans une demande d’image codée en dur. |
| API d’insertion de données | Sur les périphériques utilisant des protocoles sans fil qui n’acceptent pas JavaScript, vous pouvez envoyer une publication XML contenant l’élément XML `<visitorid/>` aux serveurs de collecte d’Adobe depuis vos serveurs. |
| Réécriture d’URL et VISTA | Certaines architectures de déploiement prennent en charge l’utilisation de la réécriture d’URL pour gérer l’état de session lorsqu’un cookie ne peut pas être défini. Dans de tels cas, les services d’ingénierie d’Adobe peuvent implémenter une règle [!DNL VISTA] qui recherche la valeur de session dans l’URL de la page, puis la formate et la place dans les valeurs [!UICONTROL visid]. |
>[!CAUTION]
>**Les identifiants visiteur personnalisés doivent être suffisamment granulaires/uniques** : une mise en œuvre non valide des identifiants visiteur personnalisés peut donner lieu à des données incorrectes et à de mauvaises performances en matière de création de rapports. Si l’identifiant visiteur personnalisé n’est pas suffisamment unique ou granulaire, ou s’il est incorrectement défini sur une valeur par défaut commune, telle que la chaîne "NULL" ou "0", les accès de nombreux visiteurs différents sont considérés par Adobe Analytics comme un visiteur unique. Cette situation génère des données incorrectes, le nombre de visiteurs étant trop faible et les segments ne fonctionnant pas correctement pour ce visiteur. Un identifiant visiteur personnalisé qui n’est pas suffisamment granulaire empêche également la diffusion correcte des données sur les nœuds de la grappe de rapports Analytics. Dans ce cas, un nœud devient surchargé et ne peut pas traiter les demandes de rapport en temps voulu. Tous les rapports de la suite de rapports vont alors échouer. <br>Les identifiants visiteur personnalisés mal implémentés peuvent ne pas impacter immédiatement les performances de création de rapports, car Analytics peut souvent gérer plusieurs mois de données déséquilibrées ; toutefois, avec le temps, une valeur d’identifiant visiteur personnalisé mal implémentée peut devenir problématique au point d’exiger d’Analytics qu’il désactive le traitement pour les suites de rapports affectées.</br><br>Les implémenteurs doivent suivre la directive selon laquelle une seule valeur d’identifiant visiteur personnalisé ne doit jamais être créditée pour plus de 1 % du trafic de votre suite de rapports. Bien que la recommandation de 1 % soit suffisante pour la plupart des suites de rapports, la limite réelle susceptible d’affecter les performances des rapports peut être inférieure à 1 % pour les suites de rapports très volumineuses.</br>
