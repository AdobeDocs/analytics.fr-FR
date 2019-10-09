---
description: Chaque ID que vous voulez pouvoir rechercher se voit attribuer un espace de noms, qui est une chaîne personnalisée qui identifie cet ID dans n’importe quelle variable de l’ensemble de vos suites de rapports.
seo-description: Chaque ID que vous voulez pouvoir rechercher se voit attribuer un espace de noms, qui est une chaîne personnalisée qui identifie cet ID dans n’importe quelle variable de l’ensemble de vos suites de rapports.
seo-title: Espaces de noms
title: Espaces de noms
uuid: cab61844-3209-4980-b14c-6859de777606
translation-type: tm+mt
source-git-commit: 21fe6a0ee434e430d77a24d060acd2ffce08e219

---


# Espaces de noms

Chaque ID que vous voulez pouvoir rechercher se voit attribuer un espace de noms, qui est une chaîne personnalisée qui identifie cet ID dans n’importe quelle variable de l’ensemble de vos suites de rapports.

La chaîne d’espace de noms permet d’identifier le ou les champs que vous souhaitez rechercher lors de la fourniture d’un identifiant dans le cadre d’une demande de confidentialité des données. Lorsqu’une demande de confidentialité des données est envoyée, la demande comprend une section JSON spécifiant les ID de personne à utiliser pour la demande. Plusieurs ID peuvent être inclus dans le cadre d’une demande unique pour un sujet de données. La configuration JSON comprend :

* Un champ « namespace » contenant la chaîne d’espace de noms.
* Un champ « type » qui, pour la plupart des demandes Adobe Analytics, contient la valeur « analytics ».
* Un champ « value » contenant l’ID qu’Analytics doit rechercher dans les variables d’espace de noms associées de chacune de vos suites de rapports.

Refer to the [Experience Cloud Data Privacy API documentation](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md) for more details.

<!-- Meike, I converted this table to headings and text to fix a validation error. -Bob -->

## ID de cookie

Cookie de suivi Analytics hérité, également connu sous le nom d’ID Adobe Analytics (AAID) :

```
{
   namespace: "AAID",
   type: "standard",
   value: "2CCEEAE88503384F-1188000089CA"
}
```

La valeur doit être spécifiée sous la forme de deux nombres hexadécimaux séparés par un tiret. Tous les caractères hexadécimaux étant des caractères alphabétiques doivent être spécifiés en utilisant des majuscules. Les valeurs hexadécimales ne doivent pas commencer par un zéro (notez la différence entre les mêmes valeurs spécifiées dans le formulaire obsolète, qui nécessitait d’ajouter des zéros).

Il est également acceptable d’utiliser `“namespaceId”: 10` au lieu ou en plus de `“namespace”: “AAID”` ce formulaire et d’autres produits Adobe peuvent utiliser ce formulaire.

## Cookie de suivi Analytics hérité : formulaire obsolète

```
{
   "namespace": "visitorId",
   "type": "analytics",
   "value": "2cceeae88503384f-00001188000089ca"
}
```

Formulaire obsolète :

La valeur doit être spécifiée sous la forme de deux nombres hexadécimaux à 16 chiffres ou de deux nombres décimaux à 19 chiffres. Les nombres doivent être séparés par un tiret, un tiret bas ou un deux-points. Les zéros en début de chaîne doivent être ajoutés si l’un des nombres de contient pas assez de chiffres.

## Cookie du service d’identité

```
{
    namespace: "ECID",
    type: "standard",
    value: "00497781304058976192356650736267671594"
}
```

La valeur doit être spécifiée sous forme d’un nombre décimal à 38 chiffres. Si vous retirez ce nombre des deux colonnes mcvisid\_high/low ou post\_msvisid\_high/low d’un flux de données ou d’un rapport Entrepôt de données, vous devez décomposer chacun des deux nombres en 19 chiffres, puis les concaténer d’abord avec la valeur élevée.

Il est également acceptable d'utiliser : `“namespaceId”: 4` au lieu de ou en plus `“namespace”: “ECID”` et vous pouvez voir d’autres produits Adobe utiliser ce formulaire.

>[!NOTE]
>
>Le Marketing Cloud ID (ECID) était auparavant connu sous le nom de Marketing Cloud ID (MCID) et est toujours référencé par ce nom dans une documentation existante.
>
>Ces identifiants sont les seuls pris en charge par Analytics qui utilisent une valeur de type autre que Analytics.

Si le format de la partie valeur de l’un de ces identifiants de cookie ne suit pas le format décrit pour cet identifiant, la demande de confidentialité des données échoue, avec l’erreur "Valeur non formatée correctement".

Vous collecterez le plus souvent ces ID de cookie en utilisant le nouveau [code JavaScript sur la confidentialité](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm), qui fournira automatiquement toutes les paires clé/valeur appropriées pour ces ID JSON.

Ce code JavaScript renseigne le fichier JSON avec d’autres paires clé/valeur en plus de celles répertoriées ci-dessus (espace de noms, type, valeur), mais les champs répertoriés ci-dessus sont les plus importants pour le traitement de la confidentialité des données Analytics et les seuls à devoir fournir si vous collectez les identifiants d’une autre manière.

## Identifiant visiteur personnalisé

```
{
     namespace: "customVisitorID",
     type: "analytics",
     value: "<ID>"
}
```

L’espace de noms est également prédéfini pour l’identifiant visiteur personnalisé.

## ID dans les variables personnalisées

```
{
    namespace: "Email Address",
    type: "analytics", 
    value: "john@xyz.com" }, 
{
    namespace: "CRM ID", 
    type: "analytics", 
    value: "123456-ABCD" 
}
```

Pour les ID dans les variables de trafic ou de conversion personnalisées (props ou eVars), attribuez à la variable un libellé ID-DEVICE ou ID-PERSON, puis attribuez votre propre nom d’espace de noms à ce type d’ID. Voir [Fournir un espace de noms lors de l’étiquetage d’une variable comme ID-DEVICE ou ID-PERSON.](gdpr-labels.md)

Vous pouvez également voir les espaces de noms que vous avez précédemment définis pour d’autres variables ou suites de rapports et réutiliser l’un d’entre eux afin que le même espace de noms puisse facilement être utilisé pour toutes vos suites de rapports stockant ce type d’ID. Il est également possible d’attribuer le même espace de noms à plusieurs variables dans une suite de rapports. Par exemple, certains clients stockent un ID de gestion de la relation client dans une variable de trafic et une variable de conversion (selon la page, c’est parfois dans l’un ou l’autre ou les deux) et peuvent attribuer l’espace de noms « ID de gestion de la relation client » aux deux variables.

> [!TIP] Evitez d’utiliser le nom convivial d’une variable (nom affiché dans l’interface utilisateur de création de rapports) ou le numéro de la variable (tel que eVar12) lors de la spécification de l’espace de noms dans l’API de confidentialité des données, sauf s’il s’agit de l’espace de noms spécifié lors de l’application du libellé ID-DEVICE ou ID-PERSON. L’utilisation d’un espace de noms plutôt que d’un nom convivial permet au même bloc d’identité utilisateur de spécifier la variable correcte pour plusieurs suites de rapports. Par exemple, si l’ID se trouve dans des eVars différentes dans certaines suites de rapports ou si les noms conviviaux ne correspondent pas (par exemple, lorsque le nom convivial a été localisé pour une suite de rapports spécifique).

> [!CAUTION] Les espaces de noms "visitorId" et "customVisitorId" sont réservés à l’identification du cookie de suivi hérité Analytics et de l’identifiant visiteur client Analytics. N’utilisez pas ces espaces de noms pour les variables de trafic ou de conversion personnalisées.

Pour plus d’informations, voir [Fournir un espace de noms lors de l’étiquetage d’une variable comme ID-DEVICE ou ID-PERSON.](/help/admin/c-data-governance/gdpr-labels.md#section_F0A47AF8DA384A26BD56032D0ABFD2D7)
