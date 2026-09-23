---
title: Profondeur d’accès
description: Numéro du hit lors de la visite.
feature: Dimensions
exl-id: 84c27e3f-4228-4455-95bf-0239928337b5
TQID: https://experienceleague.adobe.com/dH1ItdXZTw9vcqvej3VOQDM-J9FFA38f4bq8HTJbKMo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
    internal-label: Functions
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
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 63%
---
# Profondeur du hit

La [dimension](overview.md) « Profondeur de l’accès » indique la durée d’une visite pour un accès donné. Cette dimension est utile pour comprendre le moment où les visiteurs effectuent des actions sur votre site au cours de leur visite. La profondeur d’accès comptabilise tous les types d’accès, y compris les pages vues ([`t()`](/help/implement/vars/functions/t-method.md)) et les accès de suivi des liens ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Renseignement de cette dimension avec des données

Adobe calcule cette dimension côté serveur à partir de la séquence d’accès de chaque visite. Il n’existe aucune variable à définir ; elle est prête à l’emploi pour toutes les implémentations.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucun (calculé par Adobe) |
| **Champ Web SDK/XDM** | Aucun (calculé par Adobe) |
| **Paramètre de requête** | S.O. |
| **Balise XML** | S.O. |
| **Limite d’octets** | S.O. |
| **Persistance** | S.O. |

## Éléments de dimension

Les éléments de dimension comprennent la chaîne `"Hit Depth"` suivie d’un nombre représentant l’ordre des hits lors de la visite. L’élément de dimension de `"Hit Depth 1"` représente le premier hit de la visite, tandis que l’élément de dimension `"Hit Depth 8"` représente le huitième hit de la visite.

>[!NOTE]
>
>Adobe Analytics enregistre les horodatages avec une précision de second niveau uniquement. Pour les accès qui partagent la même date et la même heure, Adobe ne peut pas garantir que l’ordre reflété dans les rapports est identique à celui dans lequel les accès se sont produits. Si la précision au niveau de la milliseconde est une priorité pour votre organisation, pensez à utiliser Customer Journey Analytics.

## Comparaison avec la profondeur de visite

La profondeur de hit comptabilise tous les types de hits, y compris les vues de page et les hits de suivi des liens. La profondeur de la visite n’augmente que pour les hits de page vue, _et_ uniquement lorsque l’élément de dimension [Page](page.md) est différent de la valeur de la page précédente. La profondeur de visite est également une dimension basée sur la visite, ce qui signifie qu’elle a la même valeur pour tous les hits de la visite. Le tableau suivant illustre un exemple de visite et détaille la profondeur de hit et la profondeur de visite :

| Séquence de page | Profondeur du hit | Compte dans la profondeur de visite ? | Profondeur de visite |
| --- | --- | --- | --- |
| Page d’accueil | 1 | Oui | 4 |
| Page produit | 2 | Oui | 4 |
| Page d’accueil | 3 | Oui | 4 |
| Clic sur lien personnalisé | 4 | Non (lien personnalisé) | 4 |
| Clic sur lien personnalisé | 5 | Non (lien personnalisé) | 4 |
| Page produit | 6 | Oui | 4 |
| Clic sur lien personnalisé | 7 | Non (lien personnalisé) | 4 |
| Page produit | 8 | Non (identique à la page précédente) | 4 |
