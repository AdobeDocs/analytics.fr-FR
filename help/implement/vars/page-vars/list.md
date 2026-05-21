---
title: list
description: Variables personnalisées qui contiennent plusieurs valeurs dans le même accès.
feature: Appmeasurement Implementation
exl-id: 612f6f10-6b68-402d-abb8-beb6f44ca6ff
role: Admin, Developer
TQID: https://experienceleague.adobe.com/LpUX55ZGYgm7Z2-P4uAwH-rV88JMbi2661i4f9RYd-Q
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 503
ht-degree: 74%

---

# list

Les variables de liste sont des variables personnalisées que vous pouvez utiliser comme bon vous semble. Elles fonctionnent de la même manière que les eVars, sauf qu’elles peuvent contenir plusieurs valeurs dans le même accès. Les variables de liste n’ont pas de limite de caractères.

Veillez à consigner dans votre [document de conception de solution](../../prepare/solution-design.md) la manière dont vous utilisez chaque variable de liste et sa logique.

>[!NOTE]
>
>Les variables de liste stockent les valeurs les plus récentes par visiteur en fonction de son paramètre [!UICONTROL Valeurs maximales] dans les paramètres de la [suite de rapports](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md). 250 valeurs maximum sont prises en charge. S’il existe plus de valeurs uniques que ce que le paramètre [!UICONTROL Valeurs max] autorise, les valeurs les plus anciennes ne sont pas attribuées aux mesures.

## Configuration de variables de liste dans les paramètres de la suite de rapports

Veillez à configurer chaque variable de liste dans les paramètres de la suite de rapports avant de l’utiliser dans votre mise en œuvre. Reportez-vous à la section [Variables de conversion](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md) dans le guide Administrateur. Cette étape s’applique à toutes les méthodes de mise en œuvre.

## Variables de liste utilisant le SDK Web

Si vous utilisez l’[**objet XDM**](/help/implement/aep-edge/xdm-var-mapping.md), les variables de liste utilisent les champs XDM `xdm._experience.analytics.customDimensions.lists.list1.list[]` à `xdm._experience.analytics.customDimensions.lists.list3.list[]`. Chaque élément de tableau contient un objet `"value"` contenant chaque chaîne. Il n’est pas nécessaire de fournir un délimiteur. Les serveurs de collecte de données d’Adobe détectent et incluent automatiquement le délimiteur correct défini dans [Paramètres de la suite de rapports](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md).

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

Si vous utilisez l’[**objet de données**](/help/implement/aep-edge/data-var-mapping.md), les variables de liste utilisent `data.__adobe.analytics.list1` - `data.adobe.analytics.list3` la syntaxe AppMeasurement suivante. Assurez-vous d’utiliser le délimiteur correct défini dans [Paramètres de la suite de rapports](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md).

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

Chaque variable de liste est une chaîne qui contient des valeurs personnalisées propres à votre organisation. Cette variable n’a pas de nombre d’octets maximal. Cependant, chaque valeur individuelle a une limite maximale de 255 octets. Le délimiteur que vous utilisez est déterminé lors de la configuration de la variable dans les [paramètres de la suite de rapports](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md). N’utilisez pas d’espaces lorsque vous délimitez plusieurs éléments.

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
