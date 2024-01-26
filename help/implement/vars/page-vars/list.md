---
title: list
description: Variables personnalisées qui contiennent plusieurs valeurs dans le même accès.
feature: Variables
exl-id: 612f6f10-6b68-402d-abb8-beb6f44ca6ff
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 100%

---

# list

Les variables de liste sont des variables personnalisées que vous pouvez utiliser comme bon vous semble. Elles fonctionnent de la même manière que les eVars, sauf qu’elles peuvent contenir plusieurs valeurs dans le même accès. Les variables de liste n’ont pas de limite de caractères.

Veillez à consigner dans votre [document de conception de solution](../../prepare/solution-design.md) la manière dont vous utilisez chaque variable de liste et sa logique.

>[!NOTE]
>
>Les variables de liste stockent les 250 valeurs les plus récentes par visiteur. S’il existe plus de 250 valeurs uniques pour un visiteur donné, les valeurs les plus anciennes ne sont pas attribuées aux mesures.

## Configuration de variables de liste dans les paramètres de la suite de rapports

Veillez à configurer chaque variable de liste dans les paramètres de la suite de rapports avant de l’utiliser dans votre mise en œuvre. Reportez-vous à la section [Variables de conversion](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md) dans le guide Administrateur. Cette étape s’applique à toutes les méthodes de mise en œuvre.

## Variables de liste utilisant le SDK Web

Les variables de liste sont [mappées pour Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=fr) sous les champs XDM `_experience.analytics.customDimensions.lists.list1.list[]` à `_experience.analytics.customDimensions.lists.list3.list[]`. Chaque élément de tableau contient un objet `"value"` contenant chaque chaîne. Il n’est pas nécessaire de fournir un délimiteur. Il est automatiquement inclus en utilisant la valeur spécifiée dans [Paramètres de la suite de rapports](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md). Par exemple, si une virgule (« `,` ») est configurée comme délimiteur pour la variable de liste 1, l’objet XDM suivant renseigne la variable `list1` avec `"Example value 1,Example value 2,Example value 3"`.

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

## Variables de liste utilisant l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.list1 - s.list3 dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

Chaque variable de liste est une chaîne qui contient des valeurs personnalisées propres à votre organisation. Celles-ci n’ont pas de nombre maximal d’octets ; toutefois, chaque valeur individuelle ne peut pas dépasser 255 octets. Le délimiteur que vous utilisez est déterminé lors de la configuration de la variable dans les [paramètres de la suite de rapports](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md). N’utilisez pas d’espaces lorsque vous délimitez plusieurs éléments.

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
