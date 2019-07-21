---
description: À ne pas confondre avec la mesure Visites sur une seule page des Ad Hoc Analysis. Le rapport Visites sur une seule page présente les pages de votre site web sur lesquelles les visiteurs entrent et sortent, sans afficher d’autres pages du site.
seo-description: À ne pas confondre avec la mesure Visites sur une seule page des Ad Hoc Analysis. Le rapport Visites sur une seule page présente les pages de votre site web sur lesquelles les visiteurs entrent et sortent, sans afficher d’autres pages du site.
seo-title: Visite sur une seule page
solution: Analytics
title: Visite sur une seule page
topic: Présentation
uuid: 5 ca 52 be 8-c 7 f 5-464 a -8 a 06-55 e 8271760 b 4
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Visite sur une seule page

À ne pas confondre avec la mesure Visites sur une seule page des Ad Hoc Analysis. Le rapport Visites sur une seule page présente les pages de votre site web sur lesquelles les visiteurs entrent et sortent, sans afficher d’autres pages du site.

Ce rapport est le plus souvent utilisé dans le cadre du rapport [!UICONTROL Pages]. Il peut toutefois être visualisé dans toutes les variables de trafic dont le [!UICONTROL cheminement] est activé. Vous pouvez l’utiliser pour identifier les pages d’entrée les moins susceptibles d’inciter un visiteur à poursuivre l’exploration de votre site ou pour déterminer le nombre de visites ne comprenant qu’une seule page. Ces informations vous permettent d’optimiser le contenu afin de réduire les sorties sur ces pages.

## Propriétés du rapport {#section_2D30F939FE0648EF983DD7C1BAB1181B}

* Il est possible de récupérer un rapport identique en extrayant un rapport [!UICONTROL Pages], en utilisant [!UICONTROL Accès unique] comme mesure.

* Une visite sur une seule page est considérée comme une visite contenant une valeur unique, et non comme une demande d’une seule image.

   * Dans le cadre d’un [rapport Pages](../../../components/c-variables/dimensionslist/reports-pages.md#concept_0219136EA25745B58434D0C7E751D7D5), une seule page peut se déclencher dans la visite.
   * In the context of a [site sections report](../../../components/c-variables/dimensionslist/reports-site-sections.md#concept_39E550D7A9E34C9580E81F5F9E12BDDD), a single unique site section fires within the visit.
   * In the context of a [traffic variable](/help/admin/admin/c-traffic-variables/traffic-var.md), a visit populates this report if a single unique value is fired.

* Les visites sur une seule page peuvent être composées de nombreuses demandes d’image, pour autant que la variable dans le cadre du rapport contienne une seule valeur unique. Dès qu’une seconde valeur unique est renseignée, la visite n’est plus considérée comme une visite sur une seule page.
* On considère qu’il s’agit d’un type de rapport de cheminement. Par défaut, le cheminement est activé sur la variable [!UICONTROL Pages]. Sachez toutefois que toute variable de trafic dispose également de cette fonctionnalité. La possibilité d’activer le cheminement sur d’autres variables de trafic dépend de votre contrat. Pour plus d’informations à ce sujet, contactez le gestionnaire de compte de votre entreprise.
* Ce rapport peut utiliser un filtre de recherche afin de localiser des éléments spécifiques.
* Ce rapport peut être visualisé sous la forme d’un rapport [des formats de tendance](/help/components/c-variables/dimensionslist/reports-types.md) et [classés](/help/components/c-variables/dimensionslist/reports-types.md) .

* Aucune ventilation n’est disponible dans ce rapport.
* La seule mesure disponible est [!UICONTROL Visites].

