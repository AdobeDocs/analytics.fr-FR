---
description: La variable de conversion Aperçu personnalisé (ou eVar) est placée dans le code Adobe sur les pages web sélectionnées de votre site. Son principal objectif est de segmenter les mesures de succès de conversion dans les rapports marketing personnalisés.
keywords: Analytics Implementation;eVar;conversion variable;eVar value;conversion;success event
solution: Analytics
title: Variables de conversion (eVars)
topic: Developer and implementation
uuid: 50071c1c-be00-4b3a-a7ee-5d129acf498b
translation-type: tm+mt
source-git-commit: edf88e40cae8b6886b04257f266666c13a37f88d

---


# Variables de conversion (eVars)

La variable de conversion Aperçu personnalisé (ou eVar) est placée dans le code Adobe sur les pages web sélectionnées de votre site. Son principal objectif est de segmenter les mesures de succès de conversion dans les rapports marketing personnalisés.

Les eVars sont parfaitement adaptées à la mesure des causes et des effets, comme par exemple :

* Quelles sont les campagnes internes qui ont eu une incidence sur les recettes ?
* Quelles bannières publicitaires ont, au final, donné lieu à une inscription ?
* Combien de fois une recherche interne a-t-elle été utilisée avant de passer une commande ?

>[!IMPORTANT]
>
>Lors de la mise en œuvre d’Analytics, il est important de savoir quelles eVars vous utiliserez et combien d’entre elles. Vous devriez également être capable de configurer ces eVars dans Admin Console. Pour des informations détaillées sur les eVars, voir [Variables de conversion (eVar)](https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html) dans la documentation de référence et l’aide d’Analytics.

Une eVar peut être basée sur les visites et fonctionner comme un cookie. Les valeurs transmises dans des variables eVar suivent l’utilisateur pendant une période prédéfinie.

Lorsqu’une eVar est définie sur une valeur pour un visiteur, Adobe la mémorise automatiquement jusqu’à ce qu’elle arrive à expiration. Tout événement de succès auquel est associé un visiteur alors que la valeur eVar est active est comptabilisé dans cette dernière.

> [!NOTE] Une seule valeur peut être stockée dans une eVar dans une demande d’image. Pour stocker plusieurs valeurs dans une eVar, il est recommandé d’utiliser des [variables de liste](/help/implement/js-implementation/page-variables/listvariable.md).

Pour plus d’informations sur les variables, voir :

* [Variables pour la mise en œuvre et le compte rendu des performances Analytics](/help/implement/js-implementation/c-variables/sc-variables.md) dans cette aide
* [Variables - Utilisation dans le cadre de la création de rapports](https://marketing.adobe.com/resources/help/en_US/reference/variable_definitions.html)
* [Variables de page](/help/implement/js-implementation/page-variables/page-variables.md)
* [Variable de campagne](/help/implement/js-implementation/page-variables/campaign.md)
* [Variable products](/help/implement/js-implementation/page-variables/products.md)
* [Variable de produits](https://marketing.adobe.com/resources/help/en_US/mobile/android/products.html) dans la documentation du SDK Mobile

