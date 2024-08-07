---
title: Vitesse du contenu
description: La vitesse du contenu mesure l’impact du contenu sur le contenu en aval.
feature: Metrics
exl-id: 8ba54990-ff7d-4693-92de-7f9d9f916b55
source-git-commit: 26e166e065df90cb327fe1106542e17831069141
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 19%

---

# Vitesse du contenu

La mesure calculée &quot;Vitesse du contenu&quot; vous aide à mesurer la contribution d’une dimension (généralement [[!UICONTROL Page]](/help/components/dimensions/page.md)) aux utilisateurs qui passent du temps sur votre site web ou votre application.

Cette mesure utilise l’ [attribution de participation](/help/analyze/analysis-workspace/attribution/models.md) sur la mesure [Pages vues](page-views.md) dans le cadre de son calcul. Avec la participation à la visite, chaque fois qu’une page est atteinte, toutes les pages qui ont été consultées au cours de la même visite reçoivent également du crédit pour la page vue. Cette formule signifie généralement que plus une page est atteinte au cours d’une visite, plus elle reçoit de crédit. (Voir [ Pages vues (Participation) | Visite) ou &quot;Participation des visites&quot;](#page-views-participation--visit-or-visit-participation) pour plus d’informations.)

## Calcul

&#39;Vitesse du contenu&#39; est une [mesure](overview.md) calculée par défaut qui utilise la formule `Page views (Visit participation)` divisée par `Visits`.

![](assets/cont-velo-1.png)

## Utilisations courantes

La [!UICONTROL vitesse du contenu] est généralement utilisée dans l’analyse du contenu parallèlement à d’autres mesures clés telles que [!UICONTROL Pages vues], [!UICONTROL Visites] et [!UICONTROL Taux de rebond].

![](assets/cont-velo-3.png)

## Exemple

L’exemple suivant ventile les deux parties de la vitesse du contenu : &quot;Pages vues (Participation) | Visite)&quot; et &quot;Visites&quot;.

### Pages vues (Participation) | Visite) ou &quot;Participation de visite&quot;

Examinez l’exemple suivant sur la manière dont la participation à la visite affecte l’attribution :

Sur un site web, un utilisateur consulte les pages suivantes dans cet ordre :

* Page A
* Page B
* Page C
* Page D

Dans l’exemple ci-dessus, la page A recevra du crédit pour 4 accès, la page B pour 3 accès, la page C pour 2 accès et la page D pour 1 accès.

L’exemple suivant illustre le même principe, mais certaines pages sont visitées plus d’une fois.

* Page A
* Page B
* Page C
* Page B
* Page D
* Page A

Dans l’exemple ci-dessus, la page A recevra du crédit pour 7 accès, la page B pour 8 accès, la page C pour 4 accès et la page D pour 2 accès.

### Visites

Une fois la participation à la visite calculée, le résultat est divisé par le nombre de visites.
