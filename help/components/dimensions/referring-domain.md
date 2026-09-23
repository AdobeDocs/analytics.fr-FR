---
title: Domaine référent
description: Le domaine global sur lequel se trouvait un visiteur avant d’effectuer un clic pour accéder à votre site.
feature: Dimensions
exl-id: 9e04cb62-6526-4d84-aff7-c962c0ce42b5
TQID: https://experienceleague.adobe.com/iLpQGPuxOFmhb-WCU0EEfhmGgHgeQaPgBmOETdCczGQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 81%
---
# Domaine référent

La [dimension](overview.md) « Domaine référent » indique les domaines sur lesquels les visiteurs cliquent pour accéder à votre site. Cette dimension est utile pour identifier les sites tiers qui génèrent le plus de trafic sur le vôtre. Un lien doit exister sur le site externe et un visiteur doit cliquer sur celui-ci pour afficher l’élément de dimension.

>[!IMPORTANT]
>
>Vous devez configurer les [filtres d’URL internes](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) de votre suite de rapports pour utiliser cette dimension. Si vous ne configurez pas les filtres d’URL internes, il est possible que des domaines internes soient inclus ou que des domaines externes ne s’affichent pas.

Le même rapport peut montrer des résultats différents entre Analysis Workspace et Data Warehouse. Analysis Workspace indique le domaine référent pour chaque page individuelle, à l’exception des valeurs qui correspondent aux filtres d’URL internes. Data Warehouse indique uniquement le premier domaine référent de la visite et ignore les filtres d’URL internes.

## Renseignement de cette dimension avec des données

Adobe dérive cette dimension du [référent](referrer.md) de chaque accès, en utilisant la partie domaine de l’URL du référent. Aucune variable à définir. Vous devez configurer les [filtres d’URL internes](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) de votre suite de rapports. Si vous ne le faites pas, vous pouvez inclure des domaines internes ou empêcher l’affichage de domaines externes.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucune (dérivée du référent) |
| **Champ Web SDK/XDM** | Aucune (dérivée du référent) |
| **Paramètre de requête** | S.O. |
| **Balise XML** | S.O. |
| **Limite d’octets** | S.O. |
| **Persistance** | Visite |

Adobe conserve le domaine référent pour une visite. Si un visiteur quitte le site et clique sur le lien d’un autre domaine au cours d’une même visite, la nouvelle valeur est mise à jour et persiste pour le reste de la visite. Si vous souhaitez uniquement afficher la valeur d’origine, consultez [Domaine référent initial](original-referring-domain.md).

## Éléments de dimension

Les éléments de dimension comprennent les domaines sur lesquels les visiteurs cliquent pour accéder à votre site. Si un hit ne contient aucune donnée de référent (définie ou conservée), il est classé sous l’élément de dimension `"Typed/Bookmarked"`. Cet élément de dimension signifie qu’aucune valeur de référent n’était présente, par exemple si le visiteur a tapé manuellement l’adresse du navigateur dans la barre d’adresse ou s’il a cliqué sur un signet. L’élément de dimension `"Typed/Bookmarked"` s’affiche également pour les redirections qui ne sont pas compatibles avec Analytics. Dans le guide d’utilisation des notes techniques, consultez [Redirections et alias](/help/technotes/redirects.md).

### Éléments de dimension contenant `googleusercontent.com`

Les utilisateurs peuvent afficher les éléments de dimension avec le domaine `googleusercontent.com`.

* **Pages mises en cache** : les robots d’indexation de Google parcourent constamment le Web et stockent des copies de pages au cas où elles seraient mises hors ligne. Ces pages mises en cache sont disponibles en regard de la plupart des résultats de la recherche en cliquant sur le lien « Mise en cache ». Lorsqu’un utilisateur clique sur ce lien et consulte le contenu mis en cache par Google, `googleusercontent.com` est un élément de dimension.
* **Pages traduites** : Google offre un service de traduction robuste et pratique. Lorsque vous consultez un site à l’aide de ce service, il provient de `googleusercontent.com`. Cet élément de dimension s’affiche si l’utilisateur clique sur un lien pour revenir au contenu d’origine.
