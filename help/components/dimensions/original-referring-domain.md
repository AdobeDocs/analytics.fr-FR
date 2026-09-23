---
title: Domaine référent initial
description: Le premier domaine référent sur lequel se trouvait un visiteur avant d’effectuer un clic pour accéder à votre site.
feature: Dimensions
exl-id: 6b9ac662-a79a-477b-8612-7980da7cfadd
TQID: https://experienceleague.adobe.com/G-se6LH33gMTt8ttrP5RBzL85m335ujtbiSm6EjLGuU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
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
source-wordcount: '365'
ht-degree: 72%
---
# Domaine référent initial

La dimension [Domaine référent d’origine](overview.md) indique le premier domaine référent sur lequel un visiteur a cliqué pour accéder à votre site. Une fois définie, elle contient la même valeur pour toute la durée de vie de cet identifiant visiteur. Cette dimension est utile pour identifier les sites tiers qui génèrent initialement du trafic sur votre site.

>[!IMPORTANT]
>
>Vous devez configurer les [filtres d’URL internes](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) de votre suite de rapports pour utiliser cette dimension. Si vous ne configurez pas les filtres d’URL internes, il est possible que des domaines internes soient inclus ou que des domaines externes ne s’affichent pas.

## Renseignement de cette dimension avec des données

Adobe dérive cette dimension du premier [référent](referrer.md) du visiteur en utilisant la partie domaine de cette URL de référent. Aucune variable à définir. Vous devez configurer les [filtres d’URL internes](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) de votre suite de rapports. Si vous ne le faites pas, vous pouvez inclure des domaines internes ou empêcher l’affichage de domaines externes.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucun (dérivé du premier référent du visiteur) |
| **Champ Web SDK/XDM** | Aucun (dérivé du premier référent du visiteur) |
| **Paramètre de requête** | S.O. |
| **Balise XML** | S.O. |
| **Limite d’octets** | S.O. |
| **Persistance** | Visiteur |

Si un visiteur quitte le site et clique à tout moment sur un lien d’un autre domaine, la nouvelle valeur n’est pas enregistrée. Pour afficher les nouvelles valeurs, voir [Domaine référent](referring-domain.md).

## Éléments de dimension

Les éléments de dimension comprennent les domaines sur lesquels les visiteurs cliquent pour accéder à votre site. Si un accès ne contient aucune donnée de référent (définie ou conservée), il est classé sous l’élément de dimension `"None"`. Cet élément de dimension signifie qu’aucune valeur de référent n’était présente, par exemple si le visiteur a tapé manuellement l’adresse du navigateur dans la barre d’adresse ou s’il a cliqué sur un signet.

## Comparaison entre le domaine référent et le domaine référent initial

Le domaine référent peut changer d’une visite à l’autre. Par exemple, un visiteur arrive sur votre site par le biais de `google.com`, puis, une semaine plus tard, il arrive sur votre site par le biais de `twitter.com`. Finalement, ils effectuent un achat sur votre site. Si vous utilisez le domaine référent comme dimension avec l’attribution Dernière touche, `twitter.com` obtient le crédit pour l’achat. Si vous utilisez le domaine référent initial comme dimension, `google.com` obtient le crédit pour l’achat, quel que soit le modèle d’attribution.

Le domaine référent initial ne change jamais pendant toute la durée de vie d’un identifiant visiteur donné.
