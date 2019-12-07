---
description: À ne pas confondre avec la mesure Visites sur une seule page des Ad Hoc Analysis. Le rapport Visites sur une seule page présente les pages de votre site web sur lesquelles les visiteurs entrent et sortent, sans afficher d’autres pages du site.
title: Visite sur une seule page
topic: Reports
uuid: 5ca52be8-c7f5-464a-8a06-55e8271760b4
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Visite sur une seule page

À ne pas confondre avec la mesure Visites sur une seule page des Ad Hoc Analysis. Le rapport Visites sur une seule page présente les pages de votre site web sur lesquelles les visiteurs entrent et sortent, sans afficher d’autres pages du site.

Ce rapport est le plus souvent utilisé dans le cadre du rapport [!UICONTROL Pages]. Il peut toutefois être visualisé dans toutes les variables de trafic dont le [!UICONTROL cheminement] est activé. Vous pouvez l’utiliser pour identifier les pages d’entrée les moins susceptibles d’inciter un visiteur à poursuivre l’exploration de votre site ou pour déterminer le nombre de visites ne comprenant qu’une seule page. Ces informations vous permettent d’optimiser le contenu afin de réduire les sorties sur ces pages.

## Propriétés du rapport {#section_2D30F939FE0648EF983DD7C1BAB1181B}

* Il est possible de récupérer un rapport identique en extrayant un rapport [!UICONTROL Pages], en utilisant [!UICONTROL Accès unique] comme mesure.

* Une visite sur une seule page est considérée comme une visite contenant une valeur unique, et non comme une demande d’une seule image.

   * Dans le cadre d’un [rapport Pages](/help/components/c-variables/dimensionslist/reports-pages.md), une seule page peut se déclencher dans la visite.
   * Dans le cadre d’un [rapport de sections de site](/help/components/c-variables/dimensionslist/reports-site-sections.md), une seule section de site se déclenche au cours de la visite.
   * Dans le cadre d’une [variable de trafic](/help/admin/admin/c-traffic-variables/traffic-var.md), une visite complète ce rapport si une seule valeur est déclenchée.

* Les visites sur une seule page peuvent être composées de nombreuses demandes d’image, pour autant que la variable dans le cadre du rapport contienne une seule valeur unique. Dès qu’une seconde valeur unique est renseignée, la visite n’est plus considérée comme une visite sur une seule page.
* On considère qu’il s’agit d’un type de rapport de cheminement. Par défaut, le cheminement est activé sur la variable [!UICONTROL Pages]. Sachez toutefois que toute variable de trafic dispose également de cette fonctionnalité. La possibilité d’activer le cheminement sur d’autres variables de trafic dépend de votre contrat. Pour plus d’informations à ce sujet, contactez le gestionnaire de compte de votre entreprise.
* Ce rapport peut utiliser un filtre de recherche afin de localiser des éléments spécifiques.
* Ce rapport peut être visualisé sous la forme d’un rapport Formats [Tendance](/help/components/c-variables/dimensionslist/reports-types.md) et [Classement](/help/components/c-variables/dimensionslist/reports-types.md).

* Aucune ventilation n’est disponible dans ce rapport.
* La seule mesure disponible est [!UICONTROL Visites].

