---
description: Vous pouvez implémenter une méthode personnalisée pour identifier les visiteurs en définissant la variable s.visitorID.
keywords: Mise en œuvre d’Analytics
seo-description: Vous pouvez implémenter une méthode personnalisée pour identifier les visiteurs en définissant la variable s.visitorID.
seo-title: Identifiant visiteur personnalisé
solution: Analytics
title: Identifiant visiteur personnalisé
topic: Développeur et mise en œuvre
uuid: 49881 e 27-0418-4 ecf-a 092-dcc 3 db 923 f 40
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Identifiant visiteur personnalisé

Vous pouvez implémenter une méthode personnalisée pour identifier les visiteurs en définissant la variable s.visitorID.

Vous pouvez utiliser un identifiant visiteur personnalisé sur des sites pour lesquels vous avez un moyen unique d’identifier les visiteurs. Il s’agit, par exemple, de l’identifiant généré lorsqu’un utilisateur se connecte à un site Web à l’aide de son nom d’utilisateur et de son mot de passe.

Si vous pouvez dériver et gérer les [!UICONTROL identifiants visiteur] de vos utilisateurs, vous pouvez utiliser les méthodes suivantes pour définir l’identifiant :

| Méthode | Description |
|---|---|
| [Variable s.visitorID](/help/implement/js-implementation/c-variables/page-variables.md) | Si JavaScript est utilisé dans le navigateur, ou si vous utilisez toute autre bibliothèque AppMeasurement, vous pouvez définir l’identifiant visiteur dans une variable de collecte de données. |
| Paramètre de chaîne de requête dans la demande d’image | Elle permet de transmettre l’[!UICONTROL identifiant visiteur] à Adobe via le paramètre de [!UICONTROL chaîne de requête vide] dans une demande d’image codée en dur. |
| API d’insertion de données | On devices using wireless protocols that don't accept JavaScript, you can send an XML post containing the `<visitorid/>` XML element to Adobe collection servers from your servers. |
| Réécriture d’URL et VISTA | Certaines architectures de déploiement prennent en charge l’utilisation de la réécriture d’URL pour gérer l’état de session lorsqu’un cookie ne peut pas être défini. Dans de tels cas, les services d’ingénierie d’Adobe peuvent implémenter une règle [!DNL VISTA] qui recherche la valeur de session dans l’URL de la page, puis la formate et la place dans les valeurs [!UICONTROL visid]. |
>[!CAUTION]
>**Les identifiants visiteur personnalisés doivent être suffisamment granulaires/uniques**: Une implémentation non valide des identifiants visiteur personnalisés peut entraîner des données incorrectes et des performances de création de rapports médiocres. Si l'identifiant visiteur personnalisé n'est pas unique ou granulaire, ou qu'il est incorrectement défini sur une valeur par défaut commune telle que la chaîne « NULL » ou « 0 », Adobe Analytics affiche les accès de nombreux visiteurs différents en tant que visiteur unique. Cette situation se traduit par des données incorrectes, dont le nombre de visiteurs est trop faible et les segments ne fonctionnent pas correctement pour ce visiteur. Un identifiant visiteur personnalisé insuffisamment granulaire empêche également les données d'être correctement propagées entre les nœuds dans la grappe de rapports Analytics. Dans ce cas, un nœud devient surchargé et ne peut pas traiter les demandes de rapport en temps utile. Tous les rapports pour la suite de rapports échoueront. <br>Les identifiants visiteur personnalisés mal mis en œuvre peuvent ne pas affecter immédiatement les performances des rapports, car Analytics peut souvent gérer plusieurs mois de données déséquilibrées ; Toutefois, dans le temps, une valeur d'identifiant visiteur personnalisé peu implémenté peut poser problème à la nécessité de demander à Analytics de désactiver le traitement pour les suites de rapports affectées.</br><br>Les implémentateurs doivent suivre la directive stipulant qu'une seule valeur d'identifiant visiteur personnalisé ne doit jamais être créditée de plus de 1 % du trafic de votre suite de rapports. Although the 1% guideline is sufficient for most report suites, the actual limit that might cause reporting performance to be impacted may be lower than 1% for very large report suites.</br>
