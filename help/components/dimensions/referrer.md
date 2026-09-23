---
title: Référent
description: L’URL sur laquelle un visiteur se trouvait avant d’effectuer un clic pour accéder à votre site.
feature: Dimensions
exl-id: 146f0327-c73c-40f5-8cc1-584e31d163a2
TQID: https://experienceleague.adobe.com/VE1bJD2ah1N9t-fHKc5GC0-pC4YmXEDkCwhVmI5rHZQ
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
source-wordcount: '418'
ht-degree: 76%
---
# Référent

La [dimension](overview.md) « Référent » indique les URL sur lesquelles les visiteurs ont cliqué pour accéder à votre site. Cette dimension est utile pour identifier les adresses URL spécifiques qui génèrent le plus de trafic sur votre site. Un lien doit exister sur l’URL externe et un visiteur doit cliquer sur celui-ci pour afficher l’élément de dimension.

>[!IMPORTANT]
>
>Vous devez configurer les [filtres d’URL internes](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) de votre suite de rapports pour utiliser cette dimension. Si vous ne configurez pas les filtres d’URL internes, il est possible que des adresses URL internes soient incluses ou que des adresses URL externes ne s’affichent pas.

Le même rapport peut montrer des résultats différents entre Analysis Workspace et Data Warehouse. Analysis Workspace indique le référent de chaque page, à l’exception des valeurs qui correspondent aux filtres d’URL internes. Data Warehouse indique uniquement le premier référent de la visite et ignore les filtres d’URL internes.

## Renseignement de cette dimension avec des données

AppMeasurement collecte automatiquement le référent à partir de la valeur de `document.referrer` du navigateur. Vous pouvez remplacer la valeur collectée à lʼaide de la variable [`referrer`](/help/implement/vars/page-vars/referrer.md). Vous devez également configurer les [filtres d’URL internes](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) de votre suite de rapports. Si vous ne le faites pas, vous pouvez inclure des URL internes ou empêcher l’affichage d’URL externes.

| Propriété | Valeur |
| --- | --- |
| **Variable** | [`referrer`](/help/implement/vars/page-vars/referrer.md) |
| **Champ Web SDK/XDM** | [`web.webReferrer.URL`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-types/web-information) |
| **Paramètre de requête** | [`r`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Balise XML** | [`<referrer>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite d’octets** | 255 octets |
| **Persistance** | S.O. |

## Éléments de dimension

Les éléments de dimension comprennent les adresses URL sur lesquelles les visiteurs cliquent pour accéder à votre site. Si un hit ne contient aucune donnée de référent, il est classé sous l’élément de dimension `"Typed/Bookmarked"`. Cet élément de dimension signifie qu’aucune valeur de référent n’était présente, par exemple si le visiteur a saisi manuellement l’adresse du site dans la barre d’adresse du navigateur ou s’il a cliqué sur un signet. L’élément de dimension `"Typed/Bookmarked"` s’affiche également pour les redirections qui ne sont pas compatibles avec Analytics. Dans le guide d’utilisation des notes techniques, consultez [Redirections et alias](/help/technotes/redirects.md).

### Éléments de dimension contenant `googleusercontent.com`

Les utilisateurs peuvent afficher les éléments de dimension avec le domaine `googleusercontent.com`.

* **Pages mises en cache** : les robots d’indexation de Google parcourent constamment le Web et stockent des copies de pages au cas où elles seraient mises hors ligne. Ces pages mises en cache sont disponibles en regard de la plupart des résultats de la recherche en cliquant sur le lien « Mise en cache ». Lorsqu’un utilisateur clique sur ce lien et consulte le contenu mis en cache par Google, `webcache.googleusercontent.com` est un élément de dimension standard.
* **Pages traduites** : Google offre un service de traduction robuste et pratique. Lorsque vous consultez un site à l’aide de ce service, il provient de `translate.googleusercontent.com`. Cet élément de dimension s’affiche si l’utilisateur clique sur un lien pour revenir au contenu d’origine.
