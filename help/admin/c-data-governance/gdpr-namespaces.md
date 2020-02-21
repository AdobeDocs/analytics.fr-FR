---
description: Chaque ID que vous voulez pouvoir rechercher se voit attribuer un espace de noms, qui est une chaîne personnalisée qui identifie cet ID dans n’importe quelle variable de l’ensemble de vos suites de rapports.
title: Espaces de noms
uuid: cab61844-3209-4980-b14c-6859de777606
translation-type: ht
source-git-commit: cf910f98a1921b7558a6614a9d0d69f8e4f855b4

---


# Espaces de noms

Chaque ID que vous voulez pouvoir rechercher se voit attribuer un espace de noms, qui est une chaîne personnalisée qui identifie cet ID dans n’importe quelle variable de l’ensemble de vos suites de rapports.

La chaîne d’espace de noms est utilisée pour identifier le(s) champ(s) que vous voulez rechercher lorsque vous fournissez un ID dans le cadre d’une demande relative à la Confidentialité des données. Lorsqu’une demande relative à la Confidentialité des données est soumise, celle-ci inclut une section JSON spécifiant les ID de sujet de données à utiliser pour la demande. Plusieurs ID peuvent être inclus dans le cadre d’une demande unique pour un sujet de données. La configuration JSON comprend :

* Un champ « namespace » contenant la chaîne d’espace de noms.
* Un champ « type » qui, pour la plupart des demandes Adobe Analytics, contient la valeur « analytics ».
* Un champ « value » contenant l’ID qu’Analytics doit rechercher dans les variables d’espace de noms associées de chacune de vos suites de rapports.

Pour plus de détails, voir la [documentation de l’API relative à la Confidentialité des données d’Adobe Experience Cloud](https://www.adobe.io/apis/experienceplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/technical_overview/privacy_service_overview/privacy_service_overview.md).

## ID de cookie

Cookie de suivi Analytics hérité, également connu sous le nom d’ID Adobe Analytics (AAID) :

```
{
   namespace: "AAID",
   type: "standard",
   value: "2CCEEAE88503384F-1188000089CA"
}
```

La valeur doit être spécifiée sous la forme de deux nombres hexadécimaux séparés par un tiret. Tous les caractères hexadécimaux étant des caractères alphabétiques doivent être spécifiés en utilisant des majuscules. Les valeurs hexadécimales ne doivent pas commencer par un zéro (notez la différence entre les mêmes valeurs spécifiées dans le formulaire obsolète, qui nécessitait d’ajouter des zéros).

Vous pouvez également utiliser `"namespaceId": 10` à la place ou en plus de `"namespace": "AAID"` et il est possible que d’autres produits Adobe utilisent ce formulaire.

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

## Cookie du service Identity

```
{
    namespace: "ECID",
    type: "standard",
    value: "00497781304058976192356650736267671594"
}
```

La valeur doit être spécifiée sous forme d’un nombre décimal à 38 chiffres. Si ce nombre est extrait des colonnes mcvisid\_high/low ou post\_msvisid\_high/low provenant d’un rapport de flux de données ou d’Data Warehouse, vous devez compléter les deux nombres par des zéros pour atteindre 19 chiffres, puis les concaténer avec la valeur élevée en premier.

Vous pouvez également utiliser `"namespaceId": 4` à la place ou en plus de `"namespace": "ECID"` et il est possible que d’autres produits Adobe utilisent ce formulaire.

> [!NOTE] L’Experience Cloud ID (ECID) était auparavant connu sous le nom de Marketing Cloud ID (MCID) et est toujours désigné sous ce nom dans la documentation existante.
>
>Ces identifiants sont les seuls pris en charge par Analytics qui utilisent une valeur « type » autre que « analytics ».

Si le format de la portion de valeur de l’un de ces identifiants de cookie ne respecte pas le format décrit pour cet identifiant, la demande relative à la Confidentialité des données échouera en indiquant l’erreur « Format de la valeur incorrect ».

Vous collecterez le plus souvent ces ID de cookie en utilisant le nouveau [code JavaScript sur la confidentialité](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm), qui fournira automatiquement toutes les paires clé/valeur appropriées pour ces ID JSON.

Ce code JavaScript renseigne la configuration JSON avec d’autres paires clé/valeur que celles répertoriées ci-dessus (espace de noms, type, valeur), mais les champs répertoriés ci-dessus sont les plus importants pour le traitement en vertu de la Confidentialité des données d’Analytics et les seuls que vous devez fournir si vous collectez les ID d’une autre manière.

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

Pour les ID dans les variables de trafic ou de conversion personnalisées (props ou eVars), étiquetez la variable avec une étiquette ID-DEVICE ou ID-PERSON, puis attribuez votre propre nom d’espace de noms à ce type d’ID. Voir [Fournir un espace de noms lors de l’étiquetage d’une variable comme ID-DEVICE ou ID-PERSON.](gdpr-labels.md)

Vous pouvez également voir les espaces de noms que vous avez précédemment définis pour d’autres variables ou suites de rapports et réutiliser l’un d’entre eux afin que le même espace de noms puisse facilement être utilisé pour toutes vos suites de rapports stockant ce type d’ID. Il est également possible d’attribuer le même espace de noms à plusieurs variables dans une suite de rapports. Par exemple, certains clients stockent un ID de gestion de la relation client dans une variable de trafic et une variable de conversion (selon la page, c’est parfois dans l’un ou l’autre ou les deux) et peuvent attribuer l’espace de noms « ID de gestion de la relation client » aux deux variables.

> [!TIP] Évitez d’utiliser le nom convivial d’une variable (nom affiché dans l’interface utilisateur de création de rapports) ou le numéro de la variable (par exemple, eVar12) lorsque vous spécifiez l’espace de noms dans l’API relative à la Confidentialité des données, sauf s’il s’agit de l’espace de noms spécifié lorsque vous avez appliqué l’étiquette ID-DEVICE ou ID-PERSON. L’utilisation de l’espace de noms au lieu du nom convivial permet au bloc d’identité du même utilisateur de spécifier la variable correcte pour plusieurs suites de rapports. Par exemple, si l’ID se trouve dans des eVars différentes dans certaines suites de rapports ou si les noms conviviaux ne correspondent pas (comme lorsque le nom convivial a été localisé pour une suite de rapports spécifique).

> [!CAUTION] Les espaces de noms « visitorId » et « customVisitorId » sont réservés à l’identification du cookie de suivi hérité d’Analytics et de l’identifiant visiteur du client Analytics. N’utilisez pas ces espaces de noms pour les variables de trafic ou de conversion personnalisées.

Pour plus d’informations, voir [Fournir un espace de noms lors de l’étiquetage d’une variable comme ID-DEVICE ou ID-PERSON.](/help/admin/c-data-governance/gdpr-labels.md)
