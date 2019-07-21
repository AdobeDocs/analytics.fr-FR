---
description: La variable de conversion Aperçu personnalisé (ou eVar) est placée dans le code Adobe sur les pages web sélectionnées de votre site. Son principal objectif est de segmenter les mesures de succès de conversion dans les rapports marketing personnalisés.
keywords: Implémentation d'Analytics ; Evar ; variable de conversion ; Valeur evar ; conversion ; événement de réussite
seo-description: La variable de conversion Aperçu personnalisé (ou eVar) est placée dans le code Adobe sur les pages web sélectionnées de votre site. Son principal objectif est de segmenter les mesures de succès de conversion dans les rapports marketing personnalisés.
seo-title: Variables de conversion (evars)
solution: Analytics
title: Variables de conversion (evars)
topic: Développeur et mise en œuvre
uuid: 50071 c 1 c-be 00-4 b 3 a-a 7 ee -5 d 129 acf 498 b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Variables de conversion (evars)

La variable de conversion Aperçu personnalisé (ou eVar) est placée dans le code Adobe sur les pages web sélectionnées de votre site. Son principal objectif est de segmenter les mesures de succès de conversion dans les rapports marketing personnalisés.

Les eVars sont parfaitement adaptées à la mesure des causes et des effets, comme par exemple :

* Quelles sont les campagnes internes qui ont eu une incidence sur les recettes ?
* Quelles bannières publicitaires ont, au final, donné lieu à une inscription ?
* Combien de fois une recherche interne a-t-elle été utilisée avant de passer une commande ?

>[!IMPORTANT]
>
>Lors de l'implémentation d'Analytics, il est important de connaître les evars que vous utiliserez et le nombre. Vous devriez également être capable de configurer ces eVars dans Admin Console. Pour des informations détaillées sur les eVars, voir [Variables de conversion (eVar)](https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html) dans la documentation de référence et l’aide d’Analytics.

Une eVar peut être basée sur les visites et fonctionner comme un cookie. Les valeurs transmises dans des variables eVar suivent l’utilisateur pendant une période prédéfinie.

Lorsqu’une eVar est définie sur une valeur pour un visiteur, Adobe la mémorise automatiquement jusqu’à ce qu’elle arrive à expiration. Tout événement de succès auquel est associé un visiteur alors que la valeur eVar est active est comptabilisé dans cette dernière.

>[!NOTE]
>
>Une seule valeur peut être stockée dans une evar dans une demande d'image. Pour stocker plusieurs valeurs dans une eVar, il est recommandé d’utiliser des [](/help/implement/js-implementation/c-variables/page-variables.md)variables de liste.

Pour plus d’informations sur les variables, voir :

* [Variables pour la mise en œuvre et la création de rapports d'Analytics](../../implement/js-implementation/c-variables/sc-variables.md#concept_E10E43221A2740FAAF900B79CE1EC5FB) dans cette aide
* [Variables - Utilisation dans le cadre de la création de rapports](https://marketing.adobe.com/resources/help/en_US/reference/variable_definitions.html)
* [Variables de page](/help/implement/js-implementation/c-variables/page-variables.md)
* [Variable campaign](/help/implement/js-implementation/c-variables/page-variables.md)
* [Variable products](/help/implement/js-implementation/c-variables/page-variables.md)
* [Variable de produits](https://marketing.adobe.com/resources/help/en_US/mobile/android/products.html) dans la documentation du SDK Mobile

