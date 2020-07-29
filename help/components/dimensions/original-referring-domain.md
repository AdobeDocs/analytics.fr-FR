---
title: Domaine référent original
description: Le premier domaine référent sur lequel se trouvait un visiteur avant de cliquer pour accéder à votre site.
translation-type: tm+mt
source-git-commit: 7c722e361978a3d7517e95c23442b703e7e25270
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 0%

---


# Domaine référent original

La dimension &quot;Domaine référent d’origine&quot; signale le premier domaine référent sur lequel un visiteur a cliqué pour atteindre votre site. Une fois défini, il contient la même valeur pour toute la durée de vie de cet ID de visiteur. Cette dimension est utile pour identifier les sites tiers qui génèrent initialement du trafic sur votre site.

>[!IMPORTANT]
>
>Vous devez configurer les filtres [URL](/help/admin/admin/internal-url-filter-admin.md) internes de votre suite de rapports pour utiliser cette dimension. Si vous ne configurez pas les filtres d’URL internes, vous pouvez inclure des domaines internes ou empêcher l’affichage de domaines externes.

## Renseigner cette dimension avec des données

Cette dimension nécessite une configuration à la fois dans l’interface Analytics et dans votre implémentation.

* Dans votre implémentation, cette dimension récupère les données de la chaîne [`r` de](/help/implement/validate/query-parameters.md) requête dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la variable JavaScript `document.referrer` dans le navigateur. Si vous utilisez une bibliothèque AppMeasurement (par exemple via Adobe Experience Platform Launch), cette dimension est prête à l’emploi. Si vous utilisez une méthode de collecte de données en dehors d’AppMeasurement (par exemple via l’API), veillez à inclure le paramètre de chaîne de `r` requête dans les demandes d’image.
* Dans l’interface Analytics, vous devez configurer les filtres [d’URL](/help/admin/admin/internal-url-filter-admin.md)internes de votre suite de rapports. Si vous ne configurez pas les filtres d’URL internes, vous pouvez inclure des domaines internes ou empêcher l’affichage de domaines externes.

L’Adobe conserve le domaine référent d’origine pour la durée de vie d’un visiteur. Si un visiteur quitte et clique à tout moment sur un lien d’un autre domaine, la nouvelle valeur n’est pas enregistrée. Si vous souhaitez afficher de nouvelles valeurs, voir Domaine [](referring-domain.md)référent.

## Éléments de Dimension

Les éléments de Dimension incluent les domaines sur lesquels les visiteurs cliquent pour accéder à votre site. Si un accès ne contient aucune donnée de parrain (définie ou conservée), il est regroupé sous l’élément de dimension `"None"`. Cet élément de dimension signifie qu’il n’y avait aucune valeur de parrain, par exemple si le visiteur a saisi manuellement l’adresse du navigateur dans la barre d’adresse ou a cliqué sur un signet.

## Comparer le domaine référent au domaine référent d’origine

Le domaine référent peut changer d’une visite à l’autre. Par exemple, un visiteur arrive sur votre site par `google.com`l’intermédiaire de, puis, une semaine plus tard, arrive sur votre site par `twitter.com`l’intermédiaire de. Finalement, ils effectuent un achat sur votre site. Si vous utilisez le domaine référent comme dimension avec attribution Dernière touche, `twitter.com` obtient le crédit de l’achat. Si vous utilisez le domaine référent d’origine comme dimension, `google.com` obtient le crédit de l’achat, quel que soit le modèle d’attribution.

Le domaine référent d’origine ne change jamais pendant toute la durée de vie d’un ID de visiteur donné.
