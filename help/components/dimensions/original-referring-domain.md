---
title: Domaine référent initial
description: Le premier domaine référent sur lequel se trouvait un visiteur avant d’effectuer un clic pour accéder à votre site.
translation-type: ht
source-git-commit: 7c722e361978a3d7517e95c23442b703e7e25270
workflow-type: ht
source-wordcount: '407'
ht-degree: 100%

---


# Domaine référent initial

La dimension « Domaine référent initial » indique le premier domaine référent sur lequel un visiteur a cliqué pour atteindre votre site. Une fois définie, elle contient la même valeur pour toute la durée de vie de cet identifiant visiteur. Cette dimension est utile pour identifier les sites tiers qui génèrent initialement du trafic sur votre site.

>[!IMPORTANT]
>
>Vous devez configurer les [filtres d’URL internes](/help/admin/admin/internal-url-filter-admin.md) de votre suite de rapports pour utiliser cette dimension. Si vous ne configurez pas les filtres d’URL internes, il est possible que des domaines internes soient inclus ou que des domaines externes ne s’affichent pas.

## Renseignement de cette dimension avec des données

Cette dimension nécessite une configuration à la fois dans l’interface Analytics et dans l’implémentation.

* Dans votre implémentation, cette dimension récupère les données de la [`r`chaîne de requête](/help/implement/validate/query-parameters.md) dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la variable JavaScript `document.referrer` dans le navigateur. Si vous utilisez une bibliothèque AppMeasurement (par le biais d’Adobe Experience Platform Launch, par exemple), cette dimension est prête à l’emploi. Si vous utilisez une méthode de collecte de données en dehors d’AppMeasurement (via l’API, par exemple), veillez à inclure le paramètre de chaîne de requête `r` dans les demandes d’image.
* Dans l’interface d’Analytics, vous devez configurer les [filtres d’URL internes](/help/admin/admin/internal-url-filter-admin.md) de votre suite de rapports. Si vous ne configurez pas les filtres d’URL internes, il est possible que des domaines internes soient inclus ou que des domaines externes ne s’affichent pas.

Adobe conserve le domaine référent initial pour la durée de vie d’un visiteur. Si un visiteur quitte le site et clique à tout moment sur un lien d’un autre domaine, la nouvelle valeur n’est pas enregistrée. Si vous souhaitez consulter de nouvelles valeurs, reportez-vous à [Domaine référent](referring-domain.md).

## Éléments de dimension

Les éléments de dimension comprennent les domaines sur lesquels les visiteurs cliquent pour accéder à votre site. Si un accès ne contient aucune donnée de référent (définie ou conservée), il est classé sous l’élément de dimension `"None"`. Cet élément de dimension signifie qu’aucune valeur de référent n’était présente, par exemple si le visiteur a tapé manuellement l’adresse du navigateur dans la barre d’adresse ou s’il a cliqué sur un signet.

## Comparaison entre le domaine référent et le domaine référent initial

Le domaine référent peut changer d’une visite à l’autre. Par exemple, un visiteur arrive sur votre site par le biais de `google.com`, puis, une semaine plus tard, il arrive sur votre site par le biais de `twitter.com`. Finalement, il effectue un achat sur votre site. Si vous utilisez le domaine référent comme dimension avec l’attribution Dernière touche, `twitter.com` obtient le crédit pour l’achat. Si vous utilisez le domaine référent initial comme dimension, `google.com` obtient le crédit pour l’achat, quel que soit le modèle d’attribution.

Le domaine référent initial ne change jamais pendant toute la durée de vie d’un identifiant visiteur donné.
