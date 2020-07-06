---
title: Référent
description: URL à laquelle se trouvait un visiteur avant de cliquer pour accéder à votre site.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 0%

---


# Référent

La dimension &quot;Parrain&quot; indique les URL sur lesquelles se trouvaient les visiteurs en cliquant pour atteindre votre site. Cette dimension est utile pour identifier les URL spécifiques qui génèrent le plus de trafic sur votre site. Un lien doit exister sur l’URL externe et un visiteur doit cliquer dessus pour que la valeur de dimension s’affiche.

>[!IMPORTANT]
>
>Vous devez configurer les filtres [URL](/help/admin/admin/internal-url-filter-admin.md) internes de votre suite de rapports pour utiliser cette dimension. Si vous ne configurez pas de filtres d’URL internes, vous pouvez inclure des URL internes ou empêcher l’affichage d’URL externes.

## Renseigner cette dimension avec des données

Cette dimension nécessite une configuration dans l’interface Analytics et des données dans les demandes d’image.

* Dans votre implémentation, cette dimension récupère les données de la chaîne [`r` de](/help/implement/validate/query-parameters.md) requête dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la variable JavaScript `document.referrer` dans le navigateur. Si vous utilisez une bibliothèque AppMeasurement (par exemple par le biais du lancement d’Adobe Experience Platform), cette dimension est prête à l’emploi. Si vous utilisez une méthode de collecte de données en dehors d’AppMeasurement (par exemple via l’API), veillez à inclure le paramètre de chaîne de `r` requête dans les demandes d’image.
* Dans l’interface Analytics, vous devez configurer les filtres [d’URL](/help/admin/admin/internal-url-filter-admin.md)internes de votre suite de rapports. Si vous ne configurez pas de filtres d’URL internes, vous pouvez inclure des URL internes ou empêcher l’affichage d’URL externes.

## Valeurs de dimension

Les valeurs de dimension incluent les URL que les visiteurs cliquent pour accéder à votre site. Si un accès ne contient aucune donnée de parrain, il est regroupé sous la valeur de dimension `"Typed/Bookmarked"`. Cette valeur de dimension signifie qu’il n’y avait aucune valeur de parrain, par exemple si le visiteur a saisi manuellement l’adresse du navigateur dans la barre d’adresse ou a cliqué sur un signet.
