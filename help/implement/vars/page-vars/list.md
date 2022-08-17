---
title: list
description: Variables personnalisées qui contiennent plusieurs valeurs dans le même accès.
feature: Variables
exl-id: 612f6f10-6b68-402d-abb8-beb6f44ca6ff
source-git-commit: e8a6400895110a14306e2dc9465e5de03d1b5d73
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 62%

---

# list

Les variables de liste sont des variables personnalisées que vous pouvez utiliser comme bon vous semble. Elles fonctionnent de la même manière que les eVars, sauf qu’elles peuvent contenir plusieurs valeurs dans le même accès. Les variables de liste n’ont pas de limite de caractères.

Veillez à consigner dans votre [document de conception de solution](../../prepare/solution-design.md) la manière dont vous utilisez chaque variable de liste et sa logique.

>[!NOTE]
>
>Les variables de liste stockent les 250 valeurs les plus récentes par visiteur. S’il existe plus de 250 valeurs uniques pour un visiteur donné, les valeurs les plus anciennes ne sont pas attribuées aux mesures.

## Configuration de variables de liste dans les paramètres de la suite de rapports

Veillez à configurer chaque variable de liste dans les paramètres de la suite de rapports avant de l’utiliser dans votre mise en œuvre. Reportez-vous à la section [Variables de conversion](/help/admin/admin/conversion-var-admin/list-var-admin.md) dans le guide Administrateur. Cette étape s’applique à toutes les méthodes d’implémentation.

>[!NOTE]
>
>Les variables de liste implémentées à l’aide de champs mappés dans le SDK Web utilisent le délimiteur par défaut d’une virgule (’`,`&quot;).

## Liste des variables à l’aide du SDK Web

Les variables de liste sont [mappé pour Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=fr) sous les champs XDM `_experience.analytics.customDimensions.lists.list1.list[]` to `_experience.analytics.customDimensions.lists.list3.list[]`. Chaque élément de tableau contient une `"value"` contenant chaque chaîne. Par exemple, l’objet XDM suivant renseigne la variable `list1` avec `"Example value 1,Example value 2,Example value 3"`.

```json
"xdm": {
    "_experience": {
        "analytics": {
            "customDimensions": {
                "lists": {
                    "list1": {
                        "list": [
                            {
                                "value": "Example value 1"
                            },
                            {
                                "value": "Example value 2"
                            },
                            {
                                "value": "Example value 3"
                            }
                        ]
                    }
                }
            }
        }
    }
}
```

Si votre organisation a besoin d’un délimiteur différent d’une virgule (&#39;`,`&quot;), vous pouvez transmettre la chaîne de liste entière, y compris les délimiteurs souhaités, dans un champ XDM personnalisé. Assurez-vous que la variable de liste est configurée pour accepter le délimiteur de votre choix dans [Paramètres de la suite de rapports](/help/admin/admin/conversion-var-admin/list-var-admin.md).

```json
"xdm": {
    "custom_object": {
        "custom_path": {
            "custom_listvar": "Example value 1|Example value 2|Example value 3"
        }
    }
}
```

Vous pouvez alors effectuer l’une des opérations suivantes :

* Faites correspondre le champ XDM personnalisé à la variable de liste souhaitée dans Adobe Experience Edge ; ou
* Créez une règle de traitement pour remplacer la variable de liste souhaitée par la variable de données contextuelles. Voir [Mappage d’autres champs XDM aux variables Analytics](../../aep-edge/variable-mapping.md#mapping-other-xdm-fields-to-analytics-variables).

## Variables de liste à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.list1 - s.list3 dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

Chaque variable de liste est une chaîne qui contient des valeurs personnalisées propres à votre organisation. Celles-ci n’ont pas de nombre maximal d’octets ; toutefois, chaque valeur individuelle ne peut pas dépasser 255 octets. Le délimiteur que vous utilisez est déterminé lors de la configuration de la variable dans [Paramètres de la suite de rapports](/help/admin/admin/conversion-var-admin/list-var-admin.md). N’utilisez pas d’espaces lorsque vous délimitez plusieurs éléments.

```js
// A list variable configured with a comma as a delimiter
s.list1 = "Example value 1,Example value 2,Example value 3";
```

>[!TIP]
>
>Si vous définissez des valeurs en double dans le même accès, Adobe déduplique toutes les instances de ces valeurs. Par exemple, si vous définissez `s.list1 = "Brick,Brick";`, une instance est comptabilisée dans les rapports.

## Comparer les props de liste et les variables de liste

Les props de liste et les variables de liste peuvent toutes deux contenir plusieurs valeurs dans le même accès. Cependant, il existe plusieurs différences clés entre ces deux types de variables.

* Toute prop peut devenir une prop de liste. Vous pouvez effectivement avoir jusqu’à 75 props de liste, si chaque prop est une prop de liste. Il n’y a que 3 variables de liste disponibles.
* Les props de liste sont limitées à 100 octets pour l’ensemble de la variable. Les variables de liste ont une limite de 255 octets par valeur et aucune limite totale d’octets.
* Les propriétés de liste ne persistent pas au-delà de l’accès qu’elles sont définies. Les variables de liste ont le paramètre d’expiration souhaité. Toutefois, avec le [traitement de l’heure des rapports](/help/components/vrs/vrs-report-time-processing.md), vous pouvez appliquer une attribution personnalisée aux props de liste et aux variables de liste.
