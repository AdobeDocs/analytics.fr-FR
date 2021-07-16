---
title: eVars de marchandisage et méthodes de recherche de produits
description: Exploration approfondie des concepts sous-jacents aux eVars de marchandisage et de la manière dont elles traitent et allouent les données.
source-git-commit: eb508167930019c51823e652fc16122e9e416d07
workflow-type: tm+mt
source-wordcount: '4949'
ht-degree: 0%

---

# eVars de marchandisage et méthodes de recherche de produits

Ce document détaillé explique les concepts sous-jacents aux eVars de marchandisage, qui traitent et allouent les données différemment des eVars standard. Il explique également comment les eVars de marchandisage se rapportent aux méthodes de recherche de produits.

Bien que la plupart des sites web de vente au détail disposent de plusieurs moyens de rechercher des produits, Adobe considère que les méthodes suivantes sont les méthodes de recherche de produits fondamentales dont chaque client de vente au détail doit effectuer le suivi dans Adobe Analytics :

* Mots-clés de recherche interne
* Codes de suivi de campagne internes
* Catégories de marchandisage/navigation
* Liens de vente croisée

Pour les besoins de ce document, associons quelques eVars aux solutions comme suit :

* eVar2 : Mots-clés de recherche interne
* eVar3 : Codes de suivi de campagne internes
* eVar4 : Catégories de marchandisage/navigation
* eVar5 : Liens de vente croisée

Nous pouvons utiliser un eVar supplémentaire pour mesurer les performances de toutes les méthodes de recherche de produits les unes par rapport aux autres. Outre les méthodes de recherche décrites ci-dessus, l’eVar inclut d’autres méthodes de recherche dans sa comparaison, telles que des liens vers des pages de détails de produit provenant de sites web externes.

* eVar1 : Méthodes de recherche de produits

Au lieu de configurer l’une de ces variables comme eVars standard, configurez-les comme des eVars de marchandisage. L’utilisation d’eVars de marchandisage vous permet d’allouer toute activité réussie aux valeurs capturées par les eVars à un niveau *par produit* au lieu d’un niveau *par visite/par commande*. Ce document clarifie la différence entre l’attribution par produit et l’attribution par commande dans l’ensemble.

Pour démontrer comment définir ces variables, voici un exemple où un visiteur décide d’utiliser la recherche interne par mot-clé &quot;sandales&quot; pour trouver un produit sur le site. Sur la page des résultats de recherche par mot-clé, vous devez capturer des données dans au moins deux eVars :

* `eVar2` est égal au mot-clé utilisé dans la recherche (&quot;sandals&quot;)
* `eVar1` est égal à la méthode de recherche de produit utilisée (&quot;recherche interne de mots-clés&quot;).

Lorsque vous définissez ces deux variables sur ces valeurs spécifiques, vous savez que le visiteur utilise le terme de recherche de mots-clés internes &quot;sandales&quot; pour trouver un produit. En même temps, vous savez que le visiteur n’utilise pas d’autres méthodes de recherche de produits pour rechercher des produits (par exemple, il ne navigue pas dans les catégories de produits exactement au même moment qu’il effectue une recherche de mots-clés). Pour garantir que l’affectation appropriée par produit a lieu, ces méthodes inutilisées ne doivent pas recevoir de crédit pour la recherche d’un produit trouvé par le biais d’une recherche de mots-clés interne. Par conséquent, vous devez insérer une logique dans le code (AppMeasurement, SDK Web AEP, etc.) qui définit automatiquement les eVars associées à ces autres méthodes de recherche sur une valeur &quot;méthode de non-recherche&quot;.

Par exemple, lorsqu’un utilisateur recherche des produits à l’aide du mot-clé &quot;sandales&quot;, la logique du code Analytics doit définir les variables suivantes sur la page de résultats de recherche de mots-clés internes :

* eVar2=&quot;sandals&quot;: le mot-clé &quot;sandals&quot; a été utilisé dans la recherche interne par mot-clé.
* eVar1=&quot;recherche interne de mots-clés&quot; : La méthode de recherche &quot;recherche interne par mot-clé&quot; a été utilisée.
* eVar3=&quot;campagne non interne&quot; : une campagne interne n’a pas été utilisée pour accéder à la page des résultats de recherche.
* eVar4=&quot;non-browse&quot; : une catégorie de navigation n’était pas accessible sur la page des résultats de recherche.
* eVar5=&quot;non-vente croisée&quot;: aucun clic n’a été effectué sur un lien de vente croisée dans la page des résultats de la recherche.

## Paramètres des eVars de marchandisage

Avant de poursuivre l’exemple &quot;sandales&quot;, voici les différents paramètres que vous pouvez utiliser avec vos eVars de marchandisage.  La capture d’écran suivante provient du Gestionnaire de suites de rapports. Pour y accéder, sélectionnez Analytics > Admin > Suites de rapports > Modifier les paramètres > Conversion > Variables de conversion > Ajouter > Activer le marchandisage.

![](assets/merch-evars1.png)

Les sections ci-dessous du tableau contiennent plus de détails sur ces paramètres.

| Paramètre | Description |
|--- | --- |
| Nom | Nom, ou dimension de création de rapports à laquelle la variable doit être associée. Si `eVar1` est destiné à capturer les méthodes de recherche de produits, alors le champ Nom de `eVar1` doit être défini sur &quot;Méthodes de recherche de produits&quot;. |
| Marchandisage | Type de syntaxe à utiliser pour capturer les valeurs de l’eVar de marchandisage. |
| Attribution | Permet de déterminer la valeur de l’eVar de marchandisage qui doit recevoir du crédit lorsqu’un événement réussi se produit. |
| Expire après | Détermine le moment où les liaisons d’eVar de marchandisage et de produit existantes ne doivent plus être en vigueur. |
| Type | Type de données collectées dans l’eVar de marchandisage |
| Événement de liaison de marchandisage | Événements qui déterminent à quel moment un produit doit être associé à une valeur d’eVar de marchandisage |
| Réinitialiser le | Un déclencheur qui réinitialise toutes les données principales de l’eVar à ce stade. |
| Activer le merchandising | Indicateur qui doit être défini sur &quot;Activé&quot; pour transformer l’eVar d’un eVar standard en eVar de marchandisage. |

### Activer le merchandising

Lorsque le paramètre &quot;Activer le marchandisage&quot; est défini sur &quot;Activé&quot;, tous les paramètres décrits ci-dessous apparaissent dans le Gestionnaire de suites de rapports. Lorsque le paramètre &quot;Activer le marchandisage&quot; est défini sur &quot;Désactivé&quot;, seuls les paramètres d’eVar standard sont disponibles.

### Marchandisage

Cette option n’est pas disponible pour les eVars standard. Le paramètre [!UICONTROL Marchandisage] vous permet de choisir [!UICONTROL Syntaxe de la variable de conversion] ou [!UICONTROL Syntaxe du produit] comme méthode de capture de la valeur de l’eVar de marchandisage.

**[!UICONTROL La]** syntaxe de la variable de conversion signifie que vous définissez la valeur de l’eVar dans sa propre variable. Par exemple, avec la syntaxe de la variable de conversion, la valeur `eVar1` de &quot;recherche interne par mot-clé&quot; est définie comme suit dans le code de page (ou le code AppMeasurement, le code du SDK Web AEP, etc.) :

`s.eVar1="internal keyword search";`

Toutefois, avec la **[!UICONTROL syntaxe du produit]**, l’eVar est défini dans la variable products d’Adobe Analytics uniquement. La variable de produits Analytics est divisée en six portions différentes par produit :

`s.products="[category];[productID];[quantity];[revenue];[events];[eVars]"`

*  La catégorie est une fonctionnalité obsolète et n’est plus recommandée comme option viable pour effectuer le suivi des performances des catégories de produits.  Sa simple existence démontre pourquoi, dans la plupart des mises en oeuvre de la variable products, un seul point-virgule précède la partie productID de la valeur de la variable.
*  La quantité et le   revenu sont utiles lorsqu’un achat de produit est suivi.
*  Événements utiles pour enregistrer des valeurs d’événement incrémentiel ou monétaire personnalisées qui ne sont pas censées être comptabilisées comme des recettes (comme les frais d’expédition, les remises, etc.)

Les eVars de marchandisage configurées pour utiliser la syntaxe du produit sont définies dans la dernière partie de la variable products. Supposons, par exemple, qu’un visiteur ait utilisé une recherche interne par mots-clés pour trouver l’ID de produit &quot;12345&quot;. La méthode basée sur la syntaxe du produit pour définir eVar1 dans cet exemple ressemblerait à ceci :

`s.products=";12345;;;;eVar1=internal keyword search";`

Notez que nous disposons toujours d’espaces réservés délimités par des points-virgules pour les portions de quantité, de recettes et d’événement de la variable products.  Sans ces espaces réservés, le paramètre `eVar1` de la recherche interne par mot-clé serait complètement ignoré.

### Attribution

Le terme &quot;attribution&quot; pour les eVars de marchandisage est trompeur, en particulier pour les eVars de marchandisage qui utilisent la syntaxe de la variable de conversion. Toutes les eVars standard peuvent avoir leur propre paramètre d’attribution individuel. Cependant, les eVars de marchandisage avec syntaxe de variable de conversion utilisent uniquement le paramètre d’attribution &quot;Le plus récent (dernier)&quot;, quels que soient les paramètres d’attribution affichés dans le Gestionnaire de suites de rapports.

Comprendre ce paramètre implique de comprendre la différence entre l’attribution de l’eVar et la liaison de l’eVar de marchandisage. Pour les eVars de marchandisage, &quot;Liaison de l’eVar de marchandisage&quot; est un nom plus approprié pour ce paramètre &quot;Affectation&quot;.

**Paramètre d’affectation d’eVar standard**

Chaque fois qu’un eVar avec une syntaxe standard est collecté à partir d’une demande d’image, les serveurs de traitement Adobe Analytics insèrent des données dans une autre colonne de la base de données, appelée colonne `post_evar`. Puisque les eVars sont censées être persistantes (elles expirent à un moment au-delà de l’accès actuel dans la plupart des cas), les serveurs définissent cette colonne `post_evar` à chaque demande d’image suivante. Elle est définie sur la dernière valeur transmise à l’eVar correspondant. Pour les eVars standard, lorsqu’un événement de succès se produit, Adobe Analytics utilise la colonne `post_evar` au lieu de la colonne eVar standard pour déterminer la valeur d’eVar qui doit recevoir le crédit de l’événement.

Pour les eVars standard, le paramètre Affectation détermine si la première ou la dernière valeur d’eVar collectée au cours d’une certaine période sera insérée dans la colonne `post_evar`. Si le paramètre Affectation d’un eVar standard est égal à &quot;Valeur d’origine (première)&quot;, la première valeur d’eVar collectée par le visiteur est insérée dans la colonne `post_evar` pour toutes les demandes d’image suivantes. Cela se poursuit pour toutes les futures demandes envoyées à partir du navigateur de ce visiteur jusqu’à ce que l’eVar expire selon son paramètre &quot;Expire après&quot;.

Si le paramètre d’attribution d’un eVar standard est égal à &quot;Le plus récent (Dernier)&quot;, la valeur d’eVar la plus récente collectée auprès du visiteur est renseignée dans la colonne `post_evar` pour toutes les demandes d’image suivantes. L’attribution &quot;Le plus récent (Dernier)&quot; implique que la valeur `post_evar` change chaque fois que son eVar correspondant est défini sur une nouvelle valeur dans une demande d’image. L’attribution &quot;Valeur d’origine (première)&quot; implique que la colonne `post_evar` ne change pas entre les accès, même si l’eVar correspondant peut être défini sur une valeur différente dans une demande d’image ultérieure.

**Paramètre d’attribution (liaison) de l’eVar de marchandisage**

Comme mentionné précédemment, toutes les eVars de marchandisage avec syntaxe de variable de conversion ont uniquement une attribution &quot;Le plus récent (Dernier)&quot;.  C’est ce que le paramètre &quot;Affectation&quot; signifie réellement pour les eVars de marchandisage : Comme indiqué précédemment, ce paramètre ne détermine pas les valeurs qui sont insérées dans la colonne `post_evar` car un visiteur continue à utiliser le site. Le paramètre d’attribution des eVars de marchandisage détermine plutôt la valeur d’eVar qui est liée à un produit et la manière dont ces produits réallouent leurs événements de succès aux valeurs d’eVar auxquelles ils sont liés.

Examinons ce qui se passe si le paramètre d’attribution d’un eVar de marchandisage (c’est-à-dire de liaison) est défini sur &quot;Valeur d’origine (première)&quot;. Tous les produits définis avec la colonne `post_evar` et qui n’ont pas été précédemment liés à l’eVar &quot;pré-traité&quot; correspondant de la colonne post_evar seront liés à la valeur contenue dans la colonne `post_evar`. Cette liaison entre la valeur de l’eVar et le produit ne changera jamais tant que l’eVar n’expire pas selon les paramètres du paramètre &quot;Expire après&quot; dans les paramètres de la suite de rapports.

Chaque fois qu’une demande d’image répond aux critères qui lieraient sinon un produit déjà lié à la valeur d’eVar la plus récemment définie, le paramètre &quot;Valeur d’origine (première)&quot; force les serveurs de collecte de données Adobe Analytics à ignorer toute autre tentative de ce type. L’inverse se produit avec les eVars de marchandisage dont le paramètre d’affectation (liaison) est égal à &quot;Le plus récent (dernier)&quot;. Chaque fois qu’une demande d’image répond aux critères qui lient un produit à un eVar de marchandisage, le produit se lie (et se rebond) à la valeur la plus récente transmise à l’eVar, ou à la valeur (toujours) contenue dans la colonne `post_evar`.

Comme mentionné précédemment, les eVars de marchandisage vous permettent d’allouer des événements de succès aux valeurs d’eVar par produit plutôt qu’en fonction de la visite/de la commande. Ainsi, chaque fois qu’un produit lié est associé à un événement de succès (un achat ou un ajout au panier, par exemple), l’événement de succès accorde son crédit à la fois au produit et aux valeurs de l’eVar de marchandisage auxquelles le produit est lié à ce moment-là.

### Expire après

Le paramètre d’expiration d’un eVar de marchandisage vous permet de choisir le moment où les liaisons produit/eVar doivent expirer et le moment où la colonne post_evar ne doit plus être remplie automatiquement après qu’un eVar a été transmis dans une demande d’image. L’expiration d’un eVar peut avoir lieu lorsqu’un événement de succès (de votre choix) est enregistré ou qu’une certaine période (encore une fois, de votre choix) est écoulée. Adobe Analytics ne permet qu’un seul paramètre d’expiration à la fois par eVar.

Pour la solution de méthode de recherche de produit, la meilleure pratique pour définir l’expiration d’un eVar de marchandisage doit être de la définir sur la durée pendant laquelle un produit est conservé dans le panier d’un site avant que le site ne le supprime automatiquement du panier OU lorsque l’événement d’achat a lieu. Avec l’un ou l’autre des paramètres d’expiration, le crédit de commande/unité/recette attribué à tous les produits achetés par un visiteur sera attribué aux valeurs de l’eVar de marchandisage auxquelles les produits étaient liés à ce moment-là.

### Type

Le paramètre de type eVar détermine le type de données inséré dans l’eVar. Dans la plupart des cas, voire dans tous les cas, lors de la configuration d’un eVar de marchandisage, cette valeur doit être égale à &quot;Texte&quot;. L’utilisation d’un type de &quot;compteur&quot; pour un eVar de marchandisage est rare, mais, en fonction des besoins de suivi, peut être utilisée de manière efficace pour affecter les valeurs de l’eVar de marchandisage par produit.  La discussion de solutions avec un type de &quot;compteur&quot; n’entre pas dans le cadre de ce document.

### Événement de liaison de marchandisage

Le paramètre Événement de liaison de marchandisage vous permet de spécifier les conditions qui provoqueraient la liaison d’un produit à la valeur d’un eVar de marchandisage. Ces conditions sont limitées au déclenchement d’événements de succès ou d’eVars spécifiques uniquement ; le déclenchement de variables de trafic (par exemple, props) n’a aucun effet sur les liaisons de marchandisage.

L’une des fonctionnalités les plus utiles du paramètre Événement de liaison de marchandisage est la possibilité de lier un produit à une valeur d’eVar par le biais de plusieurs événements. Par exemple, le paramètre peut autoriser la liaison de produits à une valeur d’eVar de marchandisage par l’intermédiaire d’un événement d’affichage de produit, d’un événement d’ajout de panier ou d’un événement d’achat. Le paramètre peut même, et le fait par défaut, lier un produit à une valeur d’eVar de marchandisage chaque fois qu’un autre événement/eVar (le marchandisage ou autre) est contenu dans la même demande d’image que le produit.

### Réinitialiser le

Le paramètre Réinitialiser vous permet d’&quot;expirer&quot; immédiatement toutes les valeurs d’eVar pour tous les visiteurs qui disposent actuellement d’une valeur `post_evar` dans la base de données principale Adobe Analytics. Il élimine également toutes les liaisons produit/eVar actuelles.

>[!IMPORTANT]
>Adobe ne recommande pas d’utiliser le paramètre Réinitialiser , sauf si vous envisagez complètement de laisser l’eVar recommencer avec une &quot;tranche de données propre&quot; à partir du moment où la réinitialisation a lieu.

## Quels paramètres devez-vous utiliser ?

Parmi les nombreuses combinaisons de paramètres disponibles, vous pouvez vous demander quels paramètres sont les &quot;bonnes pratiques&quot;.

Si vous souhaitez lier &quot;recherche de mots-clés internes&quot; à l’ID de produit 12345, la variable products est définie comme suit :

`s.products=";12345;;;;eVar1=internal keyword search";`

Tous les événements de succès (ajouts au panier, achats) capturés en même temps que productID 12345 sont crédités à la fois à l’ID de produit 12345 et à la valeur `eVar1` de &quot;recherche de mot-clé interne&quot;. La seule manière dont une autre valeur `eVar1` a obtenu le crédit pour les événements de succès associés à l’ID de produit 12345 est si `eVar1` a été plus tard défini sur une valeur **différente** dans la variable products (avec l’ID de produit 12345). Exemple :

`s.products=";12345;;;;eVar1=internal campaign";`

Cette configuration modifie la liaison de l’ID de produit 12345 de la valeur `eVar1` de &quot;recherche de mots-clés internes&quot; à la valeur `eVar1` de &quot;campagne interne&quot;. Cette nouvelle liaison a lieu chaque fois que la syntaxe du produit est utilisée et que le paramètre d’allocation (liaison) pour l’eVar est défini sur &quot;Le plus récent (Dernier)&quot;. Que se passe-t-il si le paramètre Affectation (liaison) est à la place défini sur &quot;Valeur d’origine (première)&quot; ? Ensuite, le paramètre eVar1 égal à &quot;campagne interne&quot; avec l’ID de produit 12345 ne renvoie pas l’ID de produit 12345 à la valeur eVar1 de &quot;campagne interne&quot;. La liaison demeure avec la valeur liée à l’origine : &quot;recherche interne par mot-clé&quot;.

### Défis liés à l’utilisation de la syntaxe des produits

Sans planification attentive, l’utilisation de la syntaxe du produit peut poser plusieurs problèmes. Prenons l’exemple de l’utilisation de plusieurs eVars pour effectuer le suivi des méthodes de recherche de produits sur le site web. Ici, chaque eVar de méthode de recherche de produit individuel doit être défini en même temps pour accorder un crédit d’eVar de méthode de recherche spécifique (et l’autre eVars de méthode de recherche sans crédit). La syntaxe du produit peut être utilisée dans de tels scénarios, mais le code résultant du déploiement est plus complexe.

Si nous utilisons notre exemple &quot;sandals&quot; d’origine et l’adaptons pour utiliser la syntaxe du produit (en supposant que le visiteur ait trouvé un produit avec l’ID &quot;sandal123&quot; à l’aide du mot-clé &quot;sandals&quot;), la variable products obtenue doit être définie comme suit :

`s.products=";sandal123;;;;eVar2=sandals|eVar1=internal search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";`

Bien que la syntaxe de la variable products soit longue dans cet exemple, elle lie chacune des valeurs d’eVar affichées à l’ID de produit de &quot;sandal123&quot;. À partir de ce moment, tous les événements de succès (par exemple, ajouts au panier, achats) capturés en même temps que le produit &quot;sandal123&quot; sont crédités aux valeurs d’eVar qui étaient liées pour la dernière fois au produit.  Cet exemple de code indique si un achat d’une unité du produit &quot;sandal123&quot; (pour 79,95 $) a lieu après que les eVars ci-dessus ont été liées au produit &quot;sandal123&quot; :

```
s.products=";sandal123;1;79.95";
s.events="purchase";
```

Les valeurs suivantes auraient toutes une commande, une unité et un chiffre d’affaires de 79,95 $ qui leur seraient attribués :

* Valeur eVar2 de &quot;sandals&quot;
* Valeur eVar1 de &quot;recherche interne par mot-clé&quot;
* Valeur eVar3 de &quot;campagne non interne&quot;
* Valeur eVar4 de &quot;non-browse&quot;

Il s’agit d’une attribution correcte, ce qui n’est pas un problème. Le principal dilemme de cette approche est plutôt de déterminer comment et quand définir les eVars de la méthode de recherche de produit.

Dans la plupart des cas, avec la syntaxe du produit, les eVars de la méthode de recherche de produit doivent être définies sur une page des détails du produit plutôt que sur la page sur laquelle la méthode de recherche a été réellement utilisée (par exemple, sur la page des résultats de la recherche de mots-clés, la page de navigation, la page d’entrée de la campagne interne, etc.). Il est raisonnable de supposer qu’un produit n’a pas été réellement &quot;trouvé&quot; tant qu’un visiteur n’a pas interagi avec un produit dans une certaine mesure. Par conséquent, ces eVars (à l’aide de la syntaxe du produit) ne doivent pas être définies sur la page de la méthode de recherche, car plusieurs produits sont (généralement) affichés sur ces pages. Nous voulons lier la valeur de la méthode de recherche uniquement aux produits avec lesquels le visiteur a interagi.

De plus, lors de l’affichage d’une page de méthode de recherche, les visiteurs peuvent cliquer sur un lien qui les amène à une page détaillée de produit spécifique ou ajouter un produit individuel au panier directement à partir de la page de la méthode de recherche. En utilisant notre exemple de mot-clé de recherche &quot;sandales&quot;, si un visiteur ajoute le produit &quot;sandal123&quot; au panier directement à partir d’une page de résultats de recherche de mots-clés, le code pour capturer l’ajout au panier (via l’événement onClick du bouton Ajouter au panier, etc.). doit être généré dynamiquement au moment de l’ajout du panier ou &quot;codé en dur&quot; directement via le code de page ou un système de gestion des balises.  Quoi qu&#39;il en soit, le code à déclencher dans de tels cas ressemblerait à ceci :

```
s.linkTrackVars="products,events";
s.linkTrackEvents=s.events="scAdd";
s.products=";sandal123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";
s.tl(true,"o","Cart Add")
```

Ce code lie correctement les valeurs d’eVar vues ci-dessus au produit &quot;sandal123&quot;. Toutefois, pour définir correctement ces valeurs lorsque l’événement de clic se produit, le développeur doit :

* Ajoutez une logique côté serveur à la page de résultats de recherche qui détermine les valeurs qui doivent être insérées dans les eVars de la méthode de recherche de produit, et
* Assemblez la variable products entière affichée ci-dessus sans erreur de syntaxe.

En outre, si un visiteur décide de &quot;trouver&quot; le produit en cliquant sur un lien vers sa page des détails du produit, le développeur doit :

* Transmettez les détails de la méthode de recherche de produit (comme illustré ci-dessus) de la page de la méthode de recherche à la page des détails du produit, et * * Assemblez la même valeur de variable de produit des éléments qui viennent d’être transmis à partir de la page précédente.

Cette solution nécessite un niveau élevé de complexité qui peut ne pas être réalisable.

### Lorsque la syntaxe du produit est utile

La syntaxe du produit reste utile lorsque

* Plusieurs produits avec le même ID de produit sont interactifs simultanément et
* Les eVars à lier à ces produits doivent avoir des valeurs différentes par ID de produit.

Par exemple, de nombreux produits vêtements disposent de &quot;SKU enfants&quot;, qui désignent la taille, la couleur, le style et tout autre attribut. Ces attributs séparent un seul produit enfant des autres produits frères appartenant au même produit parent. Disons que vous décidez d&#39;acheter un t-shirt bleu moyen plus un grand t-shirt rouge. Supposons que les deux chemises possèdent l’ID de produit parent &quot;tshirt123&quot; et que eVar10 ait été configuré pour capturer les SKU enfants. Les variables définies sur la page de confirmation d’achat sont définies comme suit :

```
s.events='purchase';
s.products=';tshirt123;1;20;;eVar10=tshirt123-m-blue,;tshirt123;1;20;;eVar10=tshirt123-l-red"
```

Dans ce cas, les valeurs `eVar10` (childSKU) de &quot;tshirt123-m-blue&quot; et &quot;tshirt123-l-red&quot; obtiennent le crédit pour l’achat de leurs instances respectives de l’ID de produit &quot;tshirt123&quot;.

### Les défis de l&#39;attribution &quot;la plus récente&quot;

Vous pourriez rencontrer d’autres problèmes en utilisant le paramètre d’affectation (liaison) de &quot;Le plus récent (dernier)&quot;. Dans de nombreuses expériences de navigation sur le Web, les visiteurs &quot;retrouvent&quot; un produit qu’ils ont déjà consulté et/ou ajouté au panier. Cela se produit généralement lors d’une visite ultérieure ou juste avant qu’ils ne décident de terminer un achat. Supposons que lors de leur première visite sur le site, ils aient trouvé le produit &quot;sandal123&quot; via la recherche par mot-clé de &quot;sandals&quot;. Ils l’ont immédiatement ajouté au panier à partir de la page des résultats de recherche de mots-clés. Le code qui capture l’ajout au panier est défini comme suit :

```
s.linkTrackVars="products,events";
s.linkTrackEvents=s.events="scAdd";
s.products=";sandal123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross
```

Par conséquent, chacune des valeurs d’eVar affichées dans cette demande d’image est liée au produit &quot;sandal123&quot;.

Maintenant, imaginez que le visiteur n’achète pas le produit au cours de cette visite, mais qu’il revienne sur le site trois jours plus tard. Ils savent qu’ils ont déjà ajouté le produit &quot;sandals123&quot; au panier. Mais ils veulent encore en savoir plus avant de faire l&#39;achat. Au lieu d’utiliser une recherche par mot-clé pour trouver le produit, le visiteur navigue sur le site. Ils se retrouvent dans la section de navigation du marchandisage &quot;femmes > chaussures > sandales&quot; juste avant de &quot;retrouver&quot; le produit. Lorsqu’ils finissent par &quot;retrouver&quot; la page des détails du produit pour le produit &quot;sandal123&quot;, les variables sont définies comme suit (au chargement de la page) :

```
s.events="prodView";
s.products=";sandal123;;;;eVar4=womens > shoes > sandals|eVar1=browse|eVar3=non-internal campaign|eVar2=non-search|eVar5=non-cross-sell";
```

Avec un paramètre d’affectation (liaison) de &quot;Le plus récent (dernier)&quot;, le produit &quot;sandal123&quot; se réassocie à des valeurs d’eVar complètement différentes de celles auxquelles il était lié à l’origine. De plus, si le visiteur effectue ensuite l’achat de &quot;sandal123&quot;, tout crédit d’achat est attribué à ces valeurs d’eVar nouvellement liées au lieu des valeurs liées d’origine !

La question est la suivante : Quelles valeurs d&#39;eVar doivent être créditées pour l&#39;achat ?&quot; N’oubliez pas que le visiteur a d’abord trouvé le produit &quot;sandal123&quot; via une recherche interne par mot-clé. Ils l’ont ensuite ajoutée au panier directement à partir de la page des résultats de recherche. Par conséquent, la valeur eVar1 de &quot;recherche interne par mot-clé&quot; (et la valeur eVar2 de &quot;sandales&quot;) doit être créditée pour l’achat. Toutefois, les paramètres d’affectation (liaison) ont été définis sur &quot;Le plus récent (Dernier)&quot;. Par conséquent, la valeur &quot;browse&quot; de l’eVar 1 (et la valeur &quot;womens > chaussures > sandales&quot; de l’eVar 4) obtient le crédit d’achat à la place. En effet, il s’agissait des dernières valeurs liées à &quot;sandal123&quot; avant que le visiteur ne termine l’achat.

Une solution à ce problème consiste à remplacer le paramètre d’affectation (liaison) de l’eVar de marchandisage &quot;Le plus récent (Dernier)&quot; par &quot;Valeur d’origine (Première)&quot;. Ainsi, les valeurs d’eVar d’origine liées au produit &quot;sandal123&quot; reçoivent du crédit lorsque l’achat a lieu, indépendamment du nombre de fois où le visiteur &quot;retrouve&quot; le produit.

Si le visiteur ajoute un produit au panier mais ne l’achète jamais, l’expiration de l’eVar permet à une nouvelle valeur de méthode de recherche d’être liée au produit. L’expiration de l’eVar doit être égale au temps qu’un site web laisse à un produit rester dans le panier avant sa suppression automatique.

### Utilisation de la syntaxe de variable de conversion

Revenons à &quot;Syntaxe du produit&quot; ou Question &quot;Syntaxe de la variable de conversion&quot;. Adobe a découvert une méthode plus simple pour collecter les eVars de marchandisage de la méthode de recherche de produits et lier leurs valeurs aux produits trouvés par les visiteurs : L’utilisation de la syntaxe des variables de conversion réduit le travail de mise en oeuvre dont les développeurs du client sont responsables. Il offre toujours les mêmes informations, ou meilleures, que la méthode Syntaxe du produit. Les développeurs doivent simplement suivre les instructions de déploiement qui leur ont été fournies, et le reste du code peut être placé dans le fichier SDK Web Adobe AppMeasurement/AEP.

Par exemple, examinons la solution recommandée pour le suivi des performances de la recherche interne par mot-clé. Il indique que sur la page des résultats de recherche de mots-clés, le code capture le mot-clé recherché par le biais d’une prop (par exemple, prop4) et d’une autre prop (par exemple, prop5). Ces props effectuent le suivi du nombre de résultats affichés à partir de la recherche. Chaque fois qu’une demande d’image Adobe Analytics est générée sur la page des résultats de recherche, elle utilise les objets de couche de données (ou code de page) déployés par les développeurs pour remplir les variables ci-dessus (les props).

Une logique supplémentaire contenue dans le fichier SDK Web AppMeasurement/AEP peut renseigner le reste des variables (les eVars/dimensions de marchandisage) qui doivent être définies en même temps.\
Par exemple, si un nouveau visiteur doit effectuer une recherche par mot-clé pour &quot;sandales&quot;, qui a renvoyé 25 résultats sur la page des résultats de recherche, le code à déclencher (via le code de page OU la capture de couche de données) ressemblera à ceci :

```
s.prop4="sandals";
s.prop5="25";
```

La logique dans le fichier SDK AppMeasurement/Analytics peut alors transformer automatiquement ce fragment de code en ce qui suit :

```
s.prop4="sandals";
s.prop5="25";
s.eVar2="sandals";
s.eVar1="internal keyword search";
s.eVar3="non-internal campaign";
s.eVar4="non-browse";
s.eVar5="non-cross sell";
```

Il n’est pas nécessaire de vous soucier de transférer des données d’une page à l’autre et de créer une chaîne assez volumineuse et peu maniable à insérer dans la variable products. Au lieu de cela, les développeurs peuvent implémenter leur partie des solutions de suivi (ce qui est inséré dans les props) et laisser le reste de l’implémentation au code personnalisé fourni par Adobe Consulting.

Comme expliqué précédemment, toutes les eVars de marchandisage qui utilisent la syntaxe de la variable de conversion ont le paramètre d’attribution &quot;Le plus récent (Dernier)&quot;. Une fois qu’un eVar est défini sur une valeur quelconque, cette valeur persiste pour tous les accès suivants (via la colonne post_evar). Il persiste jusqu’à ce qu’il soit défini sur une autre valeur ou jusqu’à l’expiration de l’eVar. Ainsi, tous les produits avec lesquels un utilisateur interagit après la définition des eVars, s’ils n’ont pas déjà été liés à ces eVars, sont liés aux valeurs &quot;Le plus récent (Dernier)&quot; transmises à l’eVar.

En reprenant l’exemple ci-dessus, la valeur `eVar2` de &quot;sandals&quot; et la valeur eVar1 de &quot;internal keyword search&quot;, etc. persistez sur toutes les pages affichées après la recherche de mots-clés. Elles persistent jusqu’à ce que les eVars soient remplacées par d’autres valeurs. Supposons qu’un visiteur clique sur un lien vers la page des détails du produit pour l’ID de produit &quot;sandal123&quot; de la page des résultats de recherche de mots-clés.  Ensuite, l’ID de produit &quot;sandal123&quot; (s’il n’a pas encore été lié) est lié à chacune des valeurs contenues dans les colonnes post_evar ou aux valeurs eVar collectées à partir de la page précédente (résultats de recherche).

Il y a une autre chose à reconsidérer avec la syntaxe de la variable de conversion. Les événements de liaison doivent être configurés pour lier une valeur d’eVar à un produit. La simple définition d’un eVar de marchandisage (dans sa propre variable) à côté d’un produit (dans la variable products) dans une demande d’image Adobe Analytics ne lie pas nécessairement la valeur d’eVar au produit.  Au lieu de cela, le paramètre Événement de liaison de marchandisage , défini dans le Gestionnaire de suites de rapports, détermine les critères qui lient une valeur d’eVar à un produit.

Puisque nous voulons lier les valeurs de l’eVar de la méthode de recherche de produit aux produits chaque fois qu’une interaction de produit a lieu (ce qui implique qu’un produit a été &quot;trouvé&quot;), il est sans risque de présumer que les interactions &quot;produit trouvé&quot; les plus courantes qui peuvent avoir lieu sont soit une consultation de produit (lorsque les visiteurs accèdent à une page des détails du produit), soit un ajout au panier (lorsque les visiteurs ajoutent un produit au panier directement à partir d’une page de la méthode de recherche de produit).)  Par conséquent, nous pouvons choisir ces deux événements (prodView, scAdd) comme événements de liaison de marchandisage &quot;fondamentaux&quot;.
Chaque fois que l’un de ces événements de liaison est contenu dans une demande d’image, tout ID de produit contenu dans la même demande (dans la variable products) et qui n’a pas déjà été lié à un eVar de marchandisage est lié aux valeurs les plus récentes transmises à l’eVar de marchandisage (comme contenu dans les colonnes post_evar ). Toute tentative de rebond de ces produits après cette liaison initiale sera ignorée lorsque le paramètre Affectation (liaison) est défini sur &quot;Valeur d’origine (première)&quot;.

### Paramètres des bonnes pratiques

Voici les paramètres des bonnes pratiques. Ils mettent en oeuvre la méthode de recherche de produit aussi facilement que possible avec l’ensemble de résultats le plus puissant. Adobe recommande aux clients de configurer chacune de leurs eVars de marchandisage de méthode de recherche de produit (en général) comme suit :

* Marchandisage activé : Activé
* Marchandisage [syntaxe] : Syntaxe de la variable de conversion
* Affectation [liaison] : Valeur d’origine (première)
* Expire après : La durée pendant laquelle un produit reste dans un panier avant d’être automatiquement supprimé (par exemple, 14 jours, 30 jours, etc.).  S’il n’existe pas de temps de ce type, l’événement &quot;Expire après&quot;
* Type : Texte
* Événements de liaison de marchandisage :  Consultation produit, ajout au panier et achat

## Que font les événements de liaison ?

Lorsqu’un événement de liaison est contenu dans le même appel serveur que la variable products, les valeurs de l’eVar de marchandisage (à l’aide de la syntaxe de la variable de conversion) de leur colonne post sont liées à la variable products . Sur la base de l’exemple précédent , supposons qu’un appel au serveur contient les valeurs d’eVar de marchandisage suivantes :

```
s.eVar2="sandals";
s.eVar1="internal keyword search";
s.eVar3="non-internal campaign";
s.eVar4="non-browse";
s.eVar5="non-cross sell";
```

Comme expliqué précédemment, les eVars ci-dessus persistent au-delà de l’accès actuel via leur colonne post_evar respective. Par conséquent, les serveurs d’Adobe transforment les eVars ci-dessus en ce qui suit :

```
post_eVar2="sandals";
post_eVar1="internal keyword search";
post_eVar3="non-internal campaign";
post_eVar4="non-browse";
post_eVar5="non-cross sell";
```

Ces colonnes de publication sont stockées dans la base de données de l’Adobe et persistent au-delà de l’accès actuel où elles ont été initialement définies. Cela suppose qu’aucune expiration ou réinitialisation de variable n’a lieu.  Les serveurs d’Adobe disposent de ces valeurs post_evar &quot;disponibles&quot; au moment où ils traitent les futurs appels de serveur contenant à la fois l’événement de liaison et la variable products.

La liaison qui a lieu se produit uniquement entre ces valeurs post_evar et le contenu de la variable products. L’événement de liaison ne &quot;lie&quot; pas nécessairement aux eVars ou à la variable products. Il s’agit du &quot;catalyseur&quot; qui indique aux serveurs d’Adobe de lier les valeurs post_evar aux produits.

Supposons que lors d’un accès ultérieur, les variables suivantes soient définies :

```
s.products=";sandals123"
s.events="prodView";
```

Compte tenu des colonnes post_evar, les serveurs de traitement d’Adobe voient cet accès comme suit :

```
s.products=";sandals123"
s.events="prodView";
post_eVar2="sandals";
post_eVar1="internal keyword search";
post_eVar3="non-internal campaign";
post_eVar4="non-browse";
post_eVar5="non-cross sell";
```

Supposons que l’eVar 1, l’eVar 2, l’eVar 3, l’eVar 4 et l’eVar 5 aient été configurés pour utiliser `prodView` comme événement de liaison. Si l’une de ces eVars n’est pas configurée pour utiliser prodView comme événement de liaison, la liaison entre cet eVar (mal configuré) et la variable products n’a pas lieu.

La liaison produit des résultats très intéressants, que l’on peut voir dans la valeur de la colonne post_products. La liaison transforme le code ci-dessus et définit quelques autres colonnes de publication, comme suit :

```
post_events="prodView"
post_products=";sandals123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell"
```

La valeur contenue dans la colonne post_products peut vous être familière. Faites défiler ce document vers le haut et comparez cette valeur post_products à la valeur s.products , comme illustré sous .  Vous remarquerez que la colonne post_products est définie à l’aide de la syntaxe de la variable de produit. Cela signifie que la liaison &quot;copie&quot; les valeurs de l’eVar Syntaxe de la variable de conversion dans la variable products via Syntaxe du produit. Cette action de copie n’a lieu que lorsque la variable products et un événement de liaison (définis via la configuration de l’eVar) sont contenus dans la même requête. À ce stade, la ou les valeurs contenues dans la ou les colonnes post_eVar sont liées au produit. Cette liaison est représentée par l’intermédiaire de la syntaxe du produit, telle qu’elle est stockée dans la colonne post_products .
