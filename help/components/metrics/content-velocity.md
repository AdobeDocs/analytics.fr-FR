---
title: Vitesse du contenu
description: La vitesse du contenu mesure l’impact du contenu sur le contenu en aval.
feature: Metrics
exl-id: 8ba54990-ff7d-4693-92de-7f9d9f916b55
TQID: https://experienceleague.adobe.com/KEcYF9OWDaxwZX798AETiAIxcffBAwj29Go-oHLOnaU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 299
ht-degree: 12%

---

# Vitesse du contenu

La mesure calculée « Vitesse du contenu » vous permet de mesurer la manière dont une dimension (généralement [[!UICONTROL Page]](/help/components/dimensions/page.md)) contribue à ce que les utilisateurs passent du temps sur votre site web ou votre application.

Cette mesure utilise l’[attribution de participation](/help/analyze/analysis-workspace/attribution/models.md) sur la mesure [Pages vues](page-views.md) dans le cadre de son calcul. Avec la participation aux visites, chaque fois qu’une page est consultée, toutes les pages précédemment consultées au cours de la même visite sont également créditées pour la page vue. Cette formule signifie généralement que plus une page est consultée tôt au cours d’une visite, plus elle reçoit de crédit. (Voir [&#x200B; Pages vues (participation | visite) ou « Participation aux visites »](#page-views-participation--visit-or-visit-participation) pour plus d’informations.)

## Calcul

« Vitesse du contenu » est une [mesure](overview.md) calculée par défaut qui utilise la formule `Page views (Visit participation)` divisée par `Visits`.

![](assets/cont-velo-1.png)

## Utilisations courantes

La [!UICONTROL vitesse du contenu] est généralement utilisée dans l’analyse du contenu parallèlement à d’autres mesures clés telles que [!UICONTROL Pages vues], [!UICONTROL Visites] et [!UICONTROL Taux de rebond].

![](assets/cont-velo-3.png)

## Exemple

L’exemple suivant répartit les 2 parties de Vitesse du contenu : « Pages vues (Participation | Visite) » et « Visites ».

### Pages vues (Participation | Visite) ou « Participation aux visites »

Prenons l’exemple suivant de la manière dont la participation aux visites affecte l’attribution :

Sur un site web, un utilisateur visite les pages suivantes dans cet ordre :

* Page A
* Page B
* Page C
* Page D

Dans l’exemple ci-dessus, la page A est créditée pour 4 accès, la page B pour 3 accès, la page C pour 2 accès et la page D pour 1 accès.

L’exemple suivant illustre le même principe, mais certaines pages étant visitées plus d’une fois.

* Page A
* Page B
* Page C
* Page B
* Page D
* Page A

Dans l’exemple ci-dessus, la page A est créditée pour 7 accès, la page B pour 8 accès, la page C pour 4 accès et la page D pour 2 accès.

### Visites

Une fois la participation aux visites calculée, le résultat est divisé par le nombre de visites.
