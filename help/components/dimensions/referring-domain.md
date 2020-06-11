---
title: Domaine référent
description: Domaine global sur lequel se trouvait un visiteur avant de cliquer pour accéder à votre site.
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 1%

---


# Domaine référent

La dimension &quot;Domaine référent&quot; signale les domaines sur lesquels les visiteurs cliquent pour atteindre votre site. Cette dimension est utile pour identifier les sites tiers qui génèrent le plus de trafic vers le vôtre. Un lien doit exister sur le site externe et un visiteur doit cliquer dessus pour que la valeur de dimension s’affiche.

>[!IMPORTANT] Vous devez configurer les filtres [URL](/help/admin/admin/internal-url-filter-admin.md) internes de votre suite de rapports pour utiliser cette dimension. Si vous ne configurez pas les filtres d’URL internes, vous pouvez inclure des domaines internes ou empêcher l’affichage de domaines externes.

## Renseigner cette dimension avec des données

Cette dimension nécessite une configuration dans l’interface Analytics et des données dans les demandes d’image.

* Dans votre implémentation, cette dimension récupère les données de la chaîne [`r` de](/help/implement/validate/query-parameters.md) requête dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la variable JavaScript `document.referrer` dans le navigateur. Si vous utilisez une bibliothèque AppMeasurement (par exemple via le lancement d’Adobe Experience Platform), cette dimension est prête à l’emploi. Si vous utilisez une méthode de collecte de données en dehors d’AppMeasurement (par exemple via l’API), veillez à inclure le paramètre de chaîne de `r` requête dans les demandes d’image.
* Dans l’interface d’Analytics, vous devez configurer les filtres [d’URL](/help/admin/admin/internal-url-filter-admin.md)internes de votre suite de rapports. Si vous ne configurez pas les filtres d’URL internes, vous pouvez inclure des domaines internes ou empêcher l’affichage de domaines externes.

Adobe persiste le domaine référent pour une visite. Si un visiteur quitte et clique sur un lien d’un autre domaine au cours d’une même visite, la nouvelle valeur est mise à jour et persiste pour le reste de la visite. Si vous souhaitez uniquement afficher la valeur d’origine, voir Domaine [référent](original-referring-domain.md)original.

## Valeurs de dimension

Les valeurs de dimension incluent les domaines sur lesquels les visiteurs cliquent pour accéder à votre site. Si un accès ne contient aucune donnée de parrain (définie ou conservée), il est regroupé sous la valeur de dimension `"Typed/Bookmarked"`. Cette valeur de dimension signifie qu’il n’y avait aucune valeur de parrain, par exemple si le visiteur a saisi manuellement l’adresse du navigateur dans la barre d’adresse ou a cliqué sur un signet.
