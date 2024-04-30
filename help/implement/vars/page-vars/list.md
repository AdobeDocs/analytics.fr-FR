---
title: list
description: Variables personnalisées qui contiennent plusieurs valeurs dans le même accès.
feature: Variables
exl-id: 612f6f10-6b68-402d-abb8-beb6f44ca6ff
role: Admin, Developer
source-git-commit: 7c8ffe8f4ccf0577136e4d7ee96340224897d2a4
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 74%

---

# list

Les variables de liste sont des variables personnalisées que vous pouvez utiliser comme bon vous semble. Elles fonctionnent de la même manière que les eVars, sauf qu’elles peuvent contenir plusieurs valeurs dans le même accès. Les variables de liste n’ont pas de limite de caractères.

Veillez à consigner dans votre [document de conception de solution](../../prepare/solution-design.md) la manière dont vous utilisez chaque variable de liste et sa logique.

>[!NOTE]
>
>Les variables de liste stockent les valeurs les plus récentes par visiteur en fonction de leur [!UICONTROL Valeurs max.] définition dans [Paramètres de la suite de rapports](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md). Jusqu’à 250 valeurs sont prises en charge. S’il existe plus de valeurs uniques que ce que la variable [!UICONTROL Valeurs max.] accepte, les valeurs les plus anciennes ne sont pas attribuées aux mesures.

## Configuration de variables de liste dans les paramètres de la suite de rapports

Veillez à configurer chaque variable de liste dans les paramètres de la suite de rapports avant de l’utiliser dans votre mise en œuvre. Reportez-vous à la section [Variables de conversion](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md) dans le guide Administrateur. Cette étape s’applique à toutes les méthodes de mise en œuvre.

## Variables de liste utilisant le SDK Web

Si vous utilisez la variable [**Objet XDM**](/help/implement/aep-edge/xdm-var-mapping.md), les variables de liste utilisent les champs XDM `xdm._experience.analytics.customDimensions.lists.list1.list[]` to `xdm._experience.analytics.customDimensions.lists.list3.list[]`. Chaque élément de tableau contient un objet `"value"` contenant chaque chaîne. Il n’est pas nécessaire de fournir un délimiteur ; les serveurs de collecte de données d’Adobe détectent et incluent automatiquement le délimiteur correct défini dans . [Paramètres de la suite de rapports](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md).

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

>[!NOTE]
>
>Le schéma XDM Adobe contient des objets `key` en plus des objets `value` dans chaque tableau `list[]`. Adobe n’utilise pas ces objets `key` lors de l’envoi de données à Adobe Analytics.

Si vous utilisez la variable [**objet de données**](/help/implement/aep-edge/data-var-mapping.md), utilisation des variables de liste `data.__adobe.analytics.list1` - `data.adobe.analytics.list3` selon la syntaxe de l’AppMeasurement. Assurez-vous d’utiliser le délimiteur correct défini dans [Paramètres de la suite de rapports](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md).

```json
"data": {
  "__adobe": {
    "analytics": {
      "list1": "Example value 1,Example value 2,Example value 3"
    }
  }
}
```

## Variables de liste utilisant l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.list1 - s.list3 dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

Chaque variable de liste est une chaîne qui contient des valeurs personnalisées propres à votre organisation. Cette variable ne dispose pas d’un nombre maximal d’octets ; toutefois, chaque valeur individuelle est limitée à 255 octets au maximum. Le délimiteur que vous utilisez est déterminé lors de la configuration de la variable dans les [paramètres de la suite de rapports](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md). N’utilisez pas d’espaces lorsque vous délimitez plusieurs éléments.

```js
// A list variable configured with a comma as a delimiter
s.list1 = "Example value 1,Example value 2,Example value 3";
```

>[!TIP]
>
>Si vous définissez des valeurs en double dans le même accès, Adobe déduplique toutes les instances de ces valeurs. Par exemple, si vous définissez `s.list1 = "Brick,Brick";`, une instance est comptabilisée dans les rapports.

## Comparer les props de liste et les variables de liste

Les props de liste et les variables de liste peuvent toutes deux contenir plusieurs valeurs dans le même accès. Cependant, il existe plusieurs différences clés entre ces deux types de variables.

* Toute prop peut devenir une prop de liste. Vous pouvez effectivement avoir jusqu’à 75 props de liste, si chaque prop est une prop de liste. Il n’y a que trois variables de liste disponibles.
* Les props de liste sont limitées à 100 octets pour l’ensemble de la variable. Les variables de liste ont une limite de 255 octets par valeur et aucune limite totale d’octets.
* Les propriétés de liste ne persistent pas au-delà de l’accès qu’elles sont définies. Les variables de liste ont le paramètre d’expiration souhaité. Toutefois, avec le [traitement de l’heure des rapports](/help/components/vrs/vrs-report-time-processing.md), vous pouvez appliquer une attribution personnalisée aux props de liste et aux variables de liste.
