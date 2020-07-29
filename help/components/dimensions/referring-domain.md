---
title: Domaine référent
description: Domaine global sur lequel se trouvait un visiteur avant de cliquer pour accéder à votre site.
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 5%

---


# Domaine référent

La dimension &quot;Domaine référent&quot; signale les domaines sur lesquels les visiteurs cliquent pour atteindre votre site. Cette dimension est utile pour identifier les sites tiers qui génèrent le plus de trafic vers le vôtre. Un lien doit exister sur le site externe et un visiteur doit cliquer dessus pour que l’élément de dimension s’affiche.

>[!IMPORTANT]
>
>Vous devez configurer les filtres [URL](/help/admin/admin/internal-url-filter-admin.md) internes de votre suite de rapports pour utiliser cette dimension. Si vous ne configurez pas les filtres d’URL internes, vous pouvez inclure des domaines internes ou empêcher l’affichage de domaines externes.

Le même rapport peut montrer des résultats différents entre Analysis Workspace et Data warehouse. L’Analysis Workspace signale le domaine référent pour chaque page, à l’exception des valeurs qui correspondent aux filtres d’URL internes. Le Data warehouse ne rapporte que le premier domaine référent de la visite et ignore les filtres d’URL internes.

## Renseigner cette dimension avec des données

Cette dimension nécessite une configuration dans l’interface Analytics et des données dans les demandes d’image.

* Dans votre implémentation, cette dimension récupère les données de la chaîne [`r` de](/help/implement/validate/query-parameters.md) requête dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la variable JavaScript `document.referrer` dans le navigateur. Si vous utilisez une bibliothèque AppMeasurement (par exemple via Adobe Experience Platform Launch), cette dimension est prête à l’emploi. Si vous utilisez une méthode de collecte de données en dehors d’AppMeasurement (par exemple via l’API), veillez à inclure le paramètre de chaîne de `r` requête dans les demandes d’image.
* Dans l’interface Analytics, vous devez configurer les filtres [d’URL](/help/admin/admin/internal-url-filter-admin.md)internes de votre suite de rapports. Si vous ne configurez pas les filtres d’URL internes, vous pouvez inclure des domaines internes ou empêcher l’affichage de domaines externes.

L’Adobe persiste dans le domaine référent pour une visite. Si un visiteur quitte et clique sur un lien d’un autre domaine au cours d’une même visite, la nouvelle valeur est mise à jour et persiste pour le reste de la visite. Si vous souhaitez uniquement afficher la valeur d’origine, voir Domaine [référent](original-referring-domain.md)original.

## Éléments de Dimension

Les éléments de Dimension incluent les domaines sur lesquels les visiteurs cliquent pour accéder à votre site. Si un accès ne contient aucune donnée de parrain (définie ou conservée), il est regroupé sous l’élément de dimension `"Typed/Bookmarked"`. Cet élément de dimension signifie qu’il n’y avait aucune valeur de parrain, par exemple si le visiteur a saisi manuellement l’adresse du navigateur dans la barre d’adresse ou a cliqué sur un signet.

### éléments de Dimension contenant `googleusercontent.com`

Les utilisateurs peuvent afficher les éléments de dimension avec le domaine `googleusercontent.com`.

* **Pages** mises en cache : Les araignées de Google analysent constamment le Web et stockent des copies des pages au cas où elles seraient mises hors ligne. Ces pages mises en cache sont disponibles en regard de la plupart des résultats de la recherche en cliquant sur le lien &quot;Mise en cache&quot;. Lorsqu’un utilisateur clique sur ce lien et vue le contenu mis en cache par Google, `googleusercontent.com` il s’agit de l’élément de dimension.
* **Pages traduites** : Google offre un service de traduction robuste et pratique. Lorsque vous consultez un site à l’aide de ce service, il provient de `googleusercontent.com`. Cet élément de dimension s’affiche si l’utilisateur clique sur un lien pour revenir au contenu d’origine.
