---
title: Référent
description: L’URL sur laquelle un visiteur se trouvait avant d’effectuer un clic pour accéder à votre site.
feature: Dimensions
exl-id: 146f0327-c73c-40f5-8cc1-584e31d163a2
TQID: https://experienceleague.adobe.com/VE1bJD2ah1N9t-fHKc5GC0-pC4YmXEDkCwhVmI5rHZQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 449
ht-degree: 96%

---

# Référent

La [dimension](overview.md) « Référent » indique les URL sur lesquelles les visiteurs ont cliqué pour accéder à votre site. Cette dimension est utile pour identifier les adresses URL spécifiques qui génèrent le plus de trafic sur votre site. Un lien doit exister sur l’URL externe et un visiteur doit cliquer sur celui-ci pour afficher l’élément de dimension.

>[!IMPORTANT]
>
>Vous devez configurer les [filtres d’URL internes](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) de votre suite de rapports pour utiliser cette dimension. Si vous ne configurez pas les filtres d’URL internes, il est possible que des adresses URL internes soient incluses ou que des adresses URL externes ne s’affichent pas.

Le même rapport peut montrer des résultats différents entre Analysis Workspace et Data Warehouse. Analysis Workspace indique le référent de chaque page, à l’exception des valeurs qui correspondent aux filtres d’URL internes. Data Warehouse indique uniquement le premier référent de la visite et ignore les filtres d’URL internes.

## Renseignement de cette dimension avec des données

Cette dimension nécessite une configuration dans l’interface d’Analytics et la présence de données dans les demandes d’image.

* Dans votre implémentation, cette dimension récupère les données de la chaîne de requête [`r`](/help/implement/validate/query-parameters.md) dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la variable JavaScript `document.referrer` dans le navigateur. Vous pouvez utiliser la substitution de variable [`referrer`](/help/implement/vars/page-vars/referrer.md) pour la définir manuellement. Si vous utilisez une bibliothèque AppMeasurement (par le biais des balises dans Adobe Experience Platform, par exemple), cette dimension est prête à l’emploi. Si vous utilisez une méthode de collecte de données en dehors d’AppMeasurement (via l’API, par exemple), veillez à inclure le paramètre de chaîne de requête `r` dans les demandes d’image.
* Dans l’interface d’Analytics, vous devez configurer les [filtres d’URL internes](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) de votre suite de rapports. Si vous ne configurez pas les filtres d’URL internes, il est possible que des adresses URL internes soient incluses ou que des adresses URL externes ne s’affichent pas.

## Éléments de dimension

Les éléments de dimension comprennent les adresses URL sur lesquelles les visiteurs cliquent pour accéder à votre site. Si un accès ne contient aucune donnée de référent, il est classé sous l’élément de dimension `"Typed/Bookmarked"`. Cet élément de dimension signifie qu’aucune valeur de référent n’était présente, par exemple si le visiteur a tapé manuellement l’adresse du navigateur dans la barre d’adresse ou s’il a cliqué sur un signet. L’élément de dimension `"Typed/Bookmarked"` s’affiche également pour les redirections qui ne sont pas compatibles avec Analytics. Dans le guide d’utilisation des notes techniques, consultez [Redirections et alias](/help/technotes/redirects.md).

### Éléments de dimension contenant `googleusercontent.com`

Les utilisateurs peuvent afficher les éléments de dimension avec le domaine `googleusercontent.com`.

* **Pages mises en cache** : les robots d’indexation de Google parcourent constamment le Web et stockent des copies de pages au cas où elles seraient mises hors ligne. Ces pages mises en cache sont disponibles en regard de la plupart des résultats de la recherche en cliquant sur le lien « Mise en cache ». Lorsqu’un utilisateur clique sur ce lien et consulte le contenu mis en cache par Google, `webcache.googleusercontent.com` est un élément de dimension standard.
* **Pages traduites** : Google offre un service de traduction robuste et pratique. Lorsque vous consultez un site à l’aide de ce service, il provient de `translate.googleusercontent.com`. Cet élément de dimension s’affiche si l’utilisateur clique sur un lien pour revenir au contenu d’origine.
