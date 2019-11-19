---
description: Les variables de page renseignent directement un rapport (pageName, props de liste, variables de liste, etc.).
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variables de page
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: e9820869d16b8656ebebe11e397a3d7d8123fbcf

---


# products

La variable sert à effectuer le suivi des produits et des catégories de produits (ainsi que de la quantité achetée et du prix d’achat). Les produits sont généralement définis en association avec un événement de panier ou un événement.

<!-- 

products.xml

 -->

>[!IMPORTANT]
>
>En janvier 2016, nous avons réalisé une mise à jour de la logique qui déclenche automatiquement l’événement *`prodView`* lorsqu’il y a une variable *`product`*, mais pas de variable *`event`*. Cette mise à jour peut augmenter le nombre des événements *`prodView`*. *`prodViews`* augmentera uniquement dans les cas suivants :
>
>1. La variable d’événement ne contient rien hormis un événement non reconnu, par exemple *`shoppingCart`* ou *`cart`*, qui ne sont pas des événements valides.
   >
   >
1. La variable *`products`* n’est pas vide.
>
>
Effet secondaire possible : il se peut que les eVars de marchandisage déclenchées par les événements *`prodView`* soient associées à une variable *`product`* vide, mais seulement si la variable *`product list`* contient un produit non valide (tel un point-virgule sans produit répertorié).

La variable *`products`* surveille la manière dont les utilisateurs interagissent avec les produits de votre site. Par exemple, une variable « products » peut surveiller le nombre de fois où un produit est affiché, ajouté au panier, passé en caisse et acheté. Elle peut également surveiller l’efficacité relative des catégories de marchandisage de votre site. Les scénarios ci-dessous sont courants pour l’utilisation de la variable « products ».

La variable *`products`* doit toujours être définie conjointement avec un événement de succès.

<table id="table_D5A11AFDDD364D0993D387906343DDF3"> 
 <thead> 
  <tr> 
   <th class="entry"> Taille maximale </th> 
   <th class="entry"> Paramètre du débogueur </th> 
   <th class="entry"> Rapports renseignés </th> 
   <th class="entry"> Valeur par défaut </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>La chaîne « <span class="wintitle"> products </span> » a une taille maximale de 64 Ko. </p> </td> 
   <td> products </td> 
   <td> Produits <p>Catégories (facultatif) </p> <p>Recettes (facultatif) </p> <p>Unités (facultatif) </p> <p>Evénements personnalisés (facultatif) </p> <p>eVars (facultatif) </p> </td> 
   <td> " " </td> 
  </tr> 
 </tbody> 
</table>

**Syntaxe**

```js
"Category;Product;Quantity;Price;eventN=X[|eventN2=X2];eVarN=merch_category[|eVarN2=merch_category2]"
```

| Champ | Définition |
|---|---|
| Catégorie | Comporte la catégorie de produit associée. Dans la version 15, les produits peuvent être associés à plusieurs catégories, ce qui corrige une limite présente dans la version 14. Si vous n’enregistriez pas auparavant une catégorie de produit, nous vous encourageons à commencer à remplir ce champ pour les suites de rapports présentes dans la version 15. |
| Produit | (Obligatoire) Identifiant utilisé pour le suivi d’un produit. Cet identifiant est utilisé pour compléter le rapport Produits. Veillez à utiliser le même identifiant pendant tout le processus de passage en caisse. |
| Quantité | Nombre d’unités achetées. Ce champ doit être défini avec un événement d’achat pour être enregistré. |
| Prix | Fait référence au coût associé de la quantité totale achetée (unités x prix unitaire), et non au prix unitaire. Ce champ doit être défini avec un événement d’achat pour être enregistré. |
| Événements | Evénements monétaires associés à un produit spécifique. Voir [Evénements monétaires spécifiques à un produit](https://helpx.adobe.com/analytics/kb/comparing-event-types.html) et [Evénements monétaires à l’échelle de la commande](https://helpx.adobe.com/analytics/kb/comparing-event-types.html). |
| eVars | Valeurs d’eVars de marchandisage associées à un produit spécifique. Voir [Variables de marchandisage](/help/components/c-variables/c-merch-variables/var-merchandising.md). |

Les valeurs incluses dans la variable *`products`* sont basées sur le type d’événement que vous enregistrez. Le délimiteur de catégorie/produit (;) est obligatoire comme espace réservé lors de l’omission de catégories. D’autres délimiteurs ne sont obligatoires que s’ils sont nécessaires pour distinguer le paramètre que vous incluez, comme indiqué dans les exemples de cette page.

**Définition de la variable « products » avec des événements de défaut d’achat**

La variable *`products`* doit être définie conjointement avec un événement de succès.

**Définition de la variable « products » avec un événement d’achat**

L’événement *`purchase`* doit être défini au niveau de la confirmation finale (« Merci ! »). du processus de commande. Le nom, la catégorie, la quantité et le prix du produit sont tous capturés dans la variable Variable *`products`*. Bien que la variable *`purchaseID`* ne soit pas obligatoire, il est vivement conseillé de l’utiliser pour éviter les commandes en double.

**Evénements de devise spécifique à un produit**

Si un événement de devise reçoit une valeur dans la variable *`products`* au lieu de la variable events, il s’applique uniquement à cette valeur. Cette fonction est utile pour effectuer le suivi de remises spécifiques à des produits, de l’expédition d’un produit et des valeurs similaires. Par exemple, si vous avez configuré l’événement 1 pour le suivi de l’expédition d’un produit, un produit avec des frais d’expédition de « 4,50 » (4.50) peut apparaître comme suit :

```js
s.events="event1" 
s.products="Footwear;Running Shoes;1;99.99;event1=4.50"
```

Dans cet exemple, la valeur de 4,50 (4.50) est associée directement au produit « Chaussures de courses » (Running Shoes). Si vous ajoutez event1 dans le rapport des produits, vous verrez « 4.50 » répertorié sur l’élément de ligne « Running Shoes ». Similaire au prix, cette valeur doit refléter le total correspondant à la quantité répertoriée. Si vous avez 2 éléments avec des frais d’expédition de 4,50 chacun, event1 doit être égal à « 9,00 » (9.00).

**Evénements de devise à l’échelle de la commande**

Si un événement de devise reçoit une valeur dans la liste des événements au lieu de la variable *`products`*, il s’applique à tous les produits de la variable *`products`*. Cela s’avère utile pour effectuer un suivi des remises à l’échelle de la commande, sur l’expédition et sur des valeurs similaires, sans modifier le prix des produits ou en effectuant un suivi sur celui-ci séparément dans la liste de produits.

Par exemple, si vous avez configuré event10 pour contenir les remises à l’échelle de la commande, un achat avec une remise de 10 % peut ressembler à ce qui suit :

```js
s.events="purchase,event10=9.95" 
s.products="Footwear;Running Shoes;1;69.95,Running Essentials;Running Socks;10;29.50" 
s.purchaseID="1234567890"
```

Dans les rapports sur les événements monétaires, le total correspond au total des événements dédupliqués (dans cet exemple, le montant total des remises durant la période du rapport) et non à la somme des valeurs d’événement pour chaque produit. Par exemple, vous verriez « 9,95 » (9.95) répertorié à la fois pour les chaussettes et les chaussures de course et le total serait également de « 9,95 » (9.95).

> [!NOTE] Si une valeur pour le même événement numérique/de devise est spécifiée dans la variable *`products`* et dans la variable *`events`*, la valeur de la variable *`events`* est utilisée.

**Pièges, questions et conseils**

* La variable *`products`* doit toujours être définie conjointement avec un événement de succès (events). Si aucun événement de succès n’est spécifié, l’événement par défaut est prodView.

* Débarrassez le nom des produits et des catégories de toute virgule ou point-virgule avant de renseigner la variable « products ».
* Eliminez tout caractère HTML (symboles de marque déposée, de marque de commerce, etc.).
* Eliminez le symbole de devise (€) du prix.

**Exemples**

<table id="table_6F1334E73CE048A5AC0CC28B561C1B2D"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <code> s.products="Category;ABC123" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category2;ABC123,;ABC456" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category3;ABC123;1;10" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category;ABC123;1;10,;ABC456;2;19.98" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;;;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99,;ABC123;2;19.98;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping|evar2=3 Stars" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping, ;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2,event3" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2,event3=9.95" </code> <p> <code> s.products="Category;ABC123;,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

