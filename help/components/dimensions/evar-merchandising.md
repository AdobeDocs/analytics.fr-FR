---
title: eVar (dimension de marchandisage)
description: Variables personnalisées liées à la dimension des produits.
feature: Dimensions
exl-id: a7e224c4-e8ae-4b53-8051-8b5dd43ff380
TQID: 'https://experienceleague.adobe.com/No-Va3JzN6Qz9hBu73A5ZzKudEB1Tqa4sNPKVKAASGI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: ca917b867cd84b09b899ce7b72586f0b15003106
workflow-type: tm+mt
source-wordcount: '2343'
ht-degree: 6%
---
# eVar (marchandisage)

>[!BEGINSHADEBOX]

*Cette page d’aide décrit le fonctionnement des eVars de marchandisage en tant que [dimension](overview.md). Pour plus d’informations sur l’implémentation des eVars de marchandisage, consultez [eVar (variable de marchandisage)](/help/implement/vars/page-vars/evar-merchandising.md) dans le guide d’utilisation de l’implémentation.*

>[!ENDSHADEBOX]

Une eVar de marchandisage fonctionne comme une eVar standard, sauf que chaque produit en a sa propre copie. La persistance, l’affectation et l’expiration fonctionnent toutes de la même manière, mais séparément pour chaque produit. Une eVar standard contient une valeur persistante par visiteur qui reçoit du crédit pour chaque événement de succès. Une eVar de marchandisage contient une valeur persistante par produit, et cette valeur reçoit un crédit pour les événements de succès de ce produit :

* Produit A → `eVar1` = `value A`
* Produit B → `eVar1` = `value B`

La valeur de chaque produit ne peut être définie ou modifiée que sur les accès qui incluent ce produit. Une fois définie, la valeur persiste jusqu’à son expiration et n’est créditée que pour les événements de succès de ce produit. La modification de la valeur du produit A n’a aucun effet sur le produit B.

Les eVars de marchandisage ne fonctionnent qu’avec la variable [`products`](/help/implement/vars/page-vars/products.md) . Une valeur d’eVar de marchandisage qui n’est pas liée à un produit ne reçoit aucun crédit. Les événements de succès sur les accès sans produits sont attribués à `"None"` pour chaque eVar de marchandisage.

>[!TIP]
>
>Pour lier des valeurs persistantes à une dimension autre que des produits, pensez à utiliser la [[!UICONTROL Liaison de dimensions]](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/persistence#binding-dimension) dans Customer Journey Analytics.

## Pourquoi utiliser des eVars de marchandisage ?

Le fait de conserver une valeur distincte pour chaque produit est important lorsqu’une seule valeur ne doit pas être créditée pour tout ce qu’un visiteur achète. Une eVar standard fonctionne bien pour les campagnes externes ou les termes de recherche externes, où une valeur doit être créditée pour tout événement de succès qui se produit. Par exemple, si un client clique sur un lien d’une campagne par e-mail pour visiter votre site Web, tous les achats effectués par ce biais doivent être crédités à cette campagne.

La recherche interne et la navigation dans les catégories sont différentes, car un visiteur les utilise souvent pour trouver plusieurs produits, chacun d’une manière différente. Supposons qu’un client recherche « `"goggles"` » (lunettes) sur votre site, puis en ajoute une paire dans le panier :

![Exemple de lunettes](assets/merch-example-goggles.png)

Avant le passage en caisse, le client recherche des `"winter coat"`, puis ajoute une veste de duvet à son panier :

![Exemple de manteau](assets/merch-example-coat.png)

Lorsque le visiteur effectue cet achat, le terme de recherche interne `"winter coat"` est crédité pour l’ensemble de la commande, y compris les lunettes, car il s’agit de la valeur la plus récente d’eVar (affectation par défaut de [!UICONTROL &#x200B; Le dernier &#x200B;]). Le terme de recherche `"goggles"` ne reçoit aucun crédit, même s’il a conduit à une partie de l’achat :

| Terme de recherche interne | Recettes |
| --- | --- |
| manteau d’hiver | $157 |

## Comment les eVars de marchandisage résolvent ce problème

Si le marchandisage est activé pour eVar dans l’exemple précédent, le terme de recherche `"goggles"` est lié aux lunettes de neige et le terme de recherche `"winter coat"` est lié à la veste de duvet. Les eVars de marchandisage allouent le chiffre d’affaires au niveau du produit. De ce fait, chaque terme est crédité du montant du chiffre d’affaires du produit auquel il est lié :

| Terme de recherche interne | Recettes |
| --- | --- |
| manteau d’hiver | $119 |
| lunettes de ski | $38 |

## Fonctionnement de la liaison et de l’affectation

Les eVars de marchandisage reposent sur trois concepts :

* **Liaison** : association entre un produit et une valeur eVar. Chaque produit conserve sa propre liaison pour chaque eVar de marchandisage. Comme une valeur eVar standard, une liaison persiste sur les accès ultérieurs jusqu’à son expiration. Par exemple, une valeur liée à un produit sur une page produit reçoit toujours un crédit lorsque ce produit est acheté sur une page ultérieure, sans définir à nouveau la valeur. La façon dont une valeur atteint le produit dépend de la syntaxe d’eVar, décrite ci-dessous.
* **Affectation** : le paramètre [!UICONTROL Affectation] détermine ce qui se produit lorsqu’une nouvelle valeur tente de se lier à un produit **déjà lié**. L’affectation est évaluée séparément pour chaque produit, afin que les valeurs d’eVar de marchandisage liées à différents produits ne soient jamais en concurrence les unes avec les autres.
  * **[!UICONTROL Valeur d’origine (première)]** : la liaison existante est conservée. La nouvelle valeur est ignorée pour ce produit jusqu’à l’expiration de la liaison.
  * **[!UICONTROL Le dernier)]** : le produit se relie à la nouvelle valeur.
* **Expiration** : le paramètre [!UICONTROL Expire après] détermine à quel moment les liaisons se terminent. La liaison de chaque produit a sa propre date d’expiration, à partir de la date de liaison du produit. Par exemple, avec une expiration de type [!UICONTROL Semaine], si le produit A est lié le lundi et que le produit B est lié le mercredi, la liaison du produit A expire le lundi suivant et la liaison du produit B expire le mercredi suivant. Lorsqu’une liaison expire, le produit n’a plus de valeur pour cette eVar, de même qu’une eVar standard n’a plus de valeur après son expiration. Les événements de succès pour ce produit sont attribués à `"None"` jusqu’à ce que le produit soit à nouveau lié.

Chaque eVar de marchandisage utilise l’une des deux syntaxes suivantes, définies dans le paramètre [!UICONTROL Marchandisage] des [paramètres de la suite de rapports](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md). La syntaxe détermine la manière dont une valeur atteint un produit :

* **[Syntaxe du produit](#product-syntax)** : la valeur est définie directement sur chaque produit dans la variable `products` et est liée à ce produit sur cet accès.
* **[Syntaxe de la variable de conversion](#conversion-variable-syntax)** : la valeur est définie dans l’eVar lui-même et persiste comme une valeur eVar standard. Il se lie aux produits du même accès ou d’un accès ultérieur contenant un événement de liaison.

Les deux syntaxes utilisent le même comportement de liaison, d’attribution et d’expiration décrit ci-dessus. Elles diffèrent de plusieurs manières :

| | Syntaxe du produit | Syntaxe de la variable de conversion |
| --- | --- | --- |
| Où la valeur est définie | Sur chaque produit, dans la variable [`products`](/help/implement/vars/page-vars/products.md) | Dans le [`eVar`](/help/implement/vars/page-vars/evar-merchandising.md) lui-même, de la même manière qu’une eVar standard |
| Lorsque la liaison se produit | Sur tout accès où la valeur est définie sur le produit | Sur les accès contenant à la fois des produits et un événement de liaison configuré |
| Valeurs par accès | Chaque produit peut avoir une valeur différente | Chaque produit de l’accès à la liaison reçoit la même valeur |
| Effort de mise en œuvre | Supérieur | Lower |

## Syntaxe du produit

Avec la syntaxe de produit, la valeur eVar est définie sur chaque produit dans la variable `products`. Dans la chaîne de `products`, la valeur qui suit le dernier point-virgule d’un produit est son eVar de marchandisage. Voir [Implémentation à l’aide de la syntaxe de produit](/help/implement/vars/page-vars/evar-merchandising.md#implement-using-product-syntax) pour la syntaxe complète.

La valeur se lie directement à ce produit sur cet accès. Les événements de liaison ne sont pas utilisés. Les accès ultérieurs incluant le produit, tels qu’un ajout au panier ou un achat, n’ont pas besoin de répéter la valeur. Comme chaque produit possède sa propre valeur, la syntaxe du produit est la seule option lorsque les produits d’un **même accès** ont besoin de valeurs **différentes**.

+++Exemple : le même produit reçoit deux valeurs

| Hit | `products` | `events` |
| --- | --- | --- |
| 1 | `;12345;;;;eVar1=internal keyword search` | |
| 2 | `;12345;;;;eVar1=internal campaign` | |
| 3 | `;12345;1;50` | `purchase` |

* **[!UICONTROL Valeur d’origine (première)]** : l’accès 2 est ignoré pour les `12345` de produit. L&#39;achat est crédité à `internal keyword search`.
* **[!UICONTROL Le dernier)]** : l’accès 2 relie les `12345` du produit. L&#39;achat est crédité à `internal campaign`.

+++

+++Exemple : deux produits reçoivent des valeurs différentes

| Hit | `products` | `events` |
| --- | --- | --- |
| 1 | `;productA;;;;eVar1=value A` | |
| 2 | `;productB;;;;eVar1=value B` | |
| 3 | `;productA;1;50,;productB;1;30` | `purchase` |

Chaque produit conserve sa propre liaison. Par conséquent, le paramètre d’affectation n’a aucun effet dans cet exemple. `value A` reçoit un crédit pour le chiffre d’affaires du produit A, et `value B` reçoit un crédit pour le chiffre d’affaires du produit B. Les deux valeurs reçoivent une commande, car la commande contient un produit lié à chaque valeur.

+++

+++Exemple : produits avec le même ID et des valeurs différentes

Un visiteur achète un t-shirt bleu moyen et un t-shirt rouge grand, tous deux avec l’ID de produit parent `tshirt123`, et `eVar10` capture les SKU enfants :

```js
s.events = "purchase";
s.products = ";tshirt123;1;20;;eVar10=tshirt123-m-blue,;tshirt123;1;20;;eVar10=tshirt123-l-red";
```

Chaque SKU enfant est crédité pour sa propre instance de `tshirt123`.

+++

Le compromis est que la syntaxe du produit nécessite la chaîne de valeur complète sur chaque produit chaque fois que la liaison doit se produire. Pour les méthodes de recherche de produit, qui utilisent généralement plusieurs eVars à la fois, la chaîne ressemble à ceci :

```js
s.products = ";sandal123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";
```

Une méthode de recherche ne doit recevoir de crédit qu’après l’interaction du visiteur avec un produit. Cette chaîne est donc généralement définie sur la page des détails du produit ou sur un ajout au panier, et non sur la page des résultats de recherche. Pour ce faire, les développeurs doivent :

* Transférer les détails de la méthode de recherche de la page de la méthode de recherche vers la page des détails du produit ou les rendre disponibles lorsqu’un ajout au panier se déclenche à partir d’une page de résultats.
* Assembler la chaîne `products` complète sans erreurs de syntaxe.

La syntaxe de la variable de conversion évite ces deux exigences.

## Syntaxe de la variable de conversion

Avec la syntaxe de la variable de conversion, la valeur est définie dans l’eVar même :

```js
s.eVar1 = "internal keyword search";
```

EVar agit comme une *zone de transit*. Une valeur définie dans eVar y est conservée jusqu’à ce qu’un événement de liaison la lie aux produits d’un accès. La liaison se fait en deux étapes :

1. **Évaluation** : lorsque l’eVar est défini, sa valeur persiste pour les accès suivants jusqu’à son expiration. Cette valeur persistante est la colonne `post_evar` dans [flux de données](/help/export/analytics-data-feed/data-feed-overview.md). Pour les eVars de marchandisage qui utilisent la syntaxe de la variable de conversion, la valeur échelonnée **reflète toujours la valeur la plus récente envoyée**, quel que soit le paramètre [!UICONTROL Affectation]. Chaque nouvelle valeur remplace la valeur précédemment évaluée.
1. **Liaison** : lorsqu’un accès contient à la fois des produits et un [!UICONTROL Événement de liaison de marchandisage] configuré, la valeur intermédiaire se lie à chaque produit de cet accès. Si un produit est déjà lié, la fonction [!UICONTROL Attribution] détermine si la nouvelle valeur remplace la liaison existante. Les produits déjà liés conservent leur valeur avec [!UICONTROL Valeur d’origine (première)] ou sont liés avec [!UICONTROL La dernière)].

Si l’eVar, la variable `products` et un événement de liaison sont tous définis sur le même accès, l’évaluation et la liaison se produisent simultanément. La nouvelle valeur se lie immédiatement aux produits sur cet accès.

La définition de l’eVar avec un produit sans événement de liaison ne lie pas la valeur à ce produit. Une valeur échelonnée ne reçoit aucun crédit tant qu’elle n’est pas liée à un produit.

### À quoi servent les événements de liaison

Un événement de liaison est le déclencheur qui indique à Adobe de lier la valeur intermédiaire aux produits sur l’accès.

* Les événements de liaison peuvent être des événements de succès standard ou personnalisés, le code de suivi ([!UICONTROL Événement de campagne]) ou des eVars. Les props n’ont aucun effet sur la liaison.
* Vous pouvez configurer plusieurs événements de liaison, tels que [!UICONTROL Événement de consultation de produit], [!UICONTROL Événement d’ajout au panier] et [!UICONTROL Événement d’achat]. Si l’un de ces événements se trouve sur un accès avec des produits, la valeur échelonnée se lie à chaque produit sur cet accès.
* Par défaut ([!UICONTROL All]), la liaison se produit chaque fois qu’un autre événement ou qu’eVar se trouve sur le même accès qu’un produit. [!UICONTROL All] est utilisé si aucun événement de liaison n’est explicitement sélectionné. Avec [!UICONTROL All], la définition d’eVar sur un accès qui inclut des produits déclenche toujours la liaison sur cet accès. Une valeur échelonnée sur un accès précédent se lie à l’accès suivant qui inclut les produits et tout autre événement ou eVar.

+++Exemple : liaison avec un événement de liaison

Tenez compte des accès suivants :

```js
// Hit 1
s.eVar1 = "internal keyword search";
s.eVar2 = "sandals";

// Hit 2
s.products = ";sandal123";
s.events = "prodView";
```

Si `prodView` est un événement de liaison pour les deux eVars, accédez à 2 liaisons `internal keyword search` (`eVar1`) et `sandals` (`eVar2`) à `sandal123`. Si un eVar ne `prodView` répertorie pas comme événement de liaison, aucune liaison ne se produit pour cet eVar.

+++

+++Exemple : l’allocation est évaluée par produit

| Hit | `eVar1` | `products` | `events` |
| --- | --- | --- | --- |
| 1 | `value A` | | |
| 2 | | `;productA,;productB` | Événement de liaison |
| 3 | `value B` | | |
| 4 | | `;productA` | Événement de liaison |
| 5 | | `;productA;1;50,;productB;1;30` | `purchase` |

Après l’accès 3, la valeur échelonnée (`post_evar1`) est `value B` avec l’un ou l’autre des paramètres d’affectation.

* **[!UICONTROL Valeur d’origine (première)]** : l’accès 4 est ignoré pour le produit A, car le produit A est déjà lié. Les deux produits restent liés à `value A`, qui reçoit tout le crédit d’achat.
* **[!UICONTROL Le dernier)]** : l’accès 4 relie le produit A à `value B`. Le produit B n’est pas dans l’accès 4, il reste donc lié à `value A`. Le crédit d’achat du produit A va à `value B`, et le crédit d’achat du produit B va à `value A`.

Avec une seule tentative de liaison, telle que les accès 1, 2 et 5 seuls, les deux paramètres produisent le même résultat. L’affectation n’a d’importance que lorsqu’un produit déjà lié reçoit une autre tentative de liaison.

+++

## Bonne pratique : méthodes de recherche de produit

La plupart des sites de vente au détail bénéficient du suivi des méthodes de recherche de produit suivantes, chacune étant une eVar de marchandisage :

* Mots-clés de recherche interne (par exemple, `eVar2`)
* Codes de suivi de campagne internes (par exemple, `eVar3`)
* Catégories de navigation ou de marchandisage (par exemple, `eVar4`)
* Liens de vente croisée (par exemple, `eVar5`)
* Une méthode de recherche de produit eVar globale qui compare toutes les méthodes, y compris les méthodes telles que les liens externes vers des pages de produit (par exemple, `eVar1`).

Lorsqu’un visiteur utilise une méthode, définissez les autres eVars de méthode de recherche sur une valeur « non ». Dans le cas contraire, la valeur antérieure d’une méthode inutilisée pourrait être créditée pour un produit trouvé par une autre méthode. Par exemple, sur la page des résultats pour une recherche interne sur « sandales » :

```js
s.eVar1 = "internal keyword search";
s.eVar2 = "sandals";
s.eVar3 = "non-internal campaign";
s.eVar4 = "non-browse";
s.eVar5 = "non-cross-sell";
```

Avec la syntaxe des variables de conversion, les développeurs et développeuses ne peuvent définir que des valeurs simples, telles qu’un terme de recherche dans une prop, et la logique de votre implémentation peut renseigner les eVars de marchandisage. Rien ne doit être transmis entre les pages ou intégré à la chaîne `products`. La variable `products` est toujours requise sur les accès où la liaison se produit.

Adobe recommande les paramètres suivants pour les eVars de la méthode de recherche de produit :

| Paramètre | Valeur |
| --- | --- |
| [!UICONTROL Attribution] | [!UICONTROL Valeur d’origine (première)] |
| [!UICONTROL Expire après] | Durée pendant laquelle les produits restent dans le panier avant la suppression automatique, par exemple 14 ou 30 jours à l’aide de l’option [!UICONTROL Personnalisé]. Si le panier n’a pas de limite, utilisez [!UICONTROL Achat]. |
| [!UICONTROL Type] | [!UICONTROL Chaîne de texte] |
| [!UICONTROL Activer le marchandisage] | [!UICONTROL Activé] |
| [!UICONTROL Marchandisage] | [!UICONTROL Syntaxe de la variable de conversion] |
| [!UICONTROL Événement de liaison de marchandisage] | [!UICONTROL Événement d’affichage du produit], [!UICONTROL Événement d’ajout au panier] et [!UICONTROL Événement d’achat] |

Voir [Variables de conversion](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md) dans le guide Administrateur pour une description de chaque paramètre.

+++Pourquoi la valeur d’origine (première) au lieu de la dernière (dernière)

Les visiteurs retrouvent souvent un produit qu’ils ont déjà consulté ou ajouté au panier. Par exemple :

1. Un visiteur recherche des « sandales » et ajoute des `sandal123` au panier à partir de la page de résultats. Le produit se lie à `internal keyword search`.
1. Trois jours plus tard, le visiteur accède à **Femmes > Chaussures > Sandales** (`eVar1` = `browse`), consulte à nouveau le `sandal123` et l’achète.

Avec [!UICONTROL Le dernier)] la vue de produit de l’étape 2 relie de nouveau `sandal123` à `browse`, qui reçoit ensuite le crédit d’achat. La méthode qui a trouvé le produit à l’origine n’en reçoit aucune.

Avec la mention [!UICONTROL Valeur d’origine (première)], la tentative de liaison de l’étape 2 est ignorée et `internal keyword search` conserve le crédit.

Si le visiteur n’achète jamais le produit, l’expiration supprime la liaison. Par conséquent, la méthode de recherche suivante que le visiteur utilise peut lier au produit. C’est pourquoi la mention [!UICONTROL Expire après] doit correspondre à la durée pendant laquelle un produit reste dans le panier.

+++

## Instances sur les eVars de marchandisage

La mesure par défaut [Instances](../metrics/instances.md) n’est pas recommandée pour une utilisation sur des variables de marchandisage.

* Pour les variables de marchandisage utilisant la syntaxe du produit, les instances ne sont jamais incrémentées.
* Pour les variables de marchandisage utilisant la syntaxe de variable de conversion, les instances sont comptabilisées chaque fois que l’eVar est définie. Toutefois, l’instance attribue à l’élément de dimension `"None"` sauf si toutes les actions suivantes se produisent sur le même accès :
  * L’eVar de marchandisage est définie avec une valeur.
  * La variable `products` est définie avec une valeur.
  * Un événement de liaison est défini.

Comme la plupart des cas d’utilisation de la syntaxe de la variable de conversion nécessitent la variable eVar et products pour des accès différents, la mesure Instances par défaut n’est pas réaliste à utiliser.

Pour comptabiliser les instances pour chaque valeur envoyée avec la syntaxe de la variable de conversion, appliquez le **Dernière touche** [modèle d’attribution](/help/analyze/analysis-workspace/attribution/overview.md) à la mesure Instances. Les modèles d’attribution utilisent les valeurs envoyées sur chaque accès, et non des valeurs intermédiaires ou des liaisons de produit. L’intervalle de recherche en amont n’a pas d’importance, car la dernière touche crédite chaque valeur sur l’accès où elle a été envoyée, quel que soit le paramètre d’affectation d’eVar.

![Sélection de l’attribution](assets/attribution-select.png)
