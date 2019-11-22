---
description: Les variables de page renseignent directement un rapport (pageName, props de liste, variables de liste, etc.).
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variables de page
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---



# Événements

La variable sert à enregistrer des événements de succès courants de panier, ainsi que des événements de succès personnalisés.


<!-- 

events.xml

 -->

<table id="table_9EB9D08C80544CD68C4B1A2012440472"> 
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
   <td> Sans limite </td> 
   <td> events </td> 
   <td> <p>Événements du panier </p> <p>Événements personnalisés </p> </td> 
   <td> N/D </td> 
  </tr> 
 </tbody> 
</table>

Un [!UICONTROL événement] doit être considéré comme un « jalon » d’un site. Les événements de succès sont le plus souvent renseignés sur la page de confirmation finale d’un processus tel qu’une inscription ou l’abonnement à un bulletin d’information. Les événements personnalisés sont définis en renseignant les variables events avec les valeurs littérales définies dans la section Valeurs possibles ci-dessous.

Par défaut, les événements de succès sont configurés en tant qu’événements « *compteur* ». Les événements de compteur comptabilisent le nombre de fois où un événement de succès est défini (x+1). Les événements peuvent également être configurés en tant qu’événements « *numériques* » qui vous permettent de spécifier la valeur d’incrément (cela peut notamment s’avérer nécessaire lors du décompte de valeurs dynamiques ou arbitraires, telles que le nombre de résultats renvoyés par une recherche interne).

Un type d’événement final, « *devise* », vous permet de définir le montant à ajouter (semblable à des événements numériques). Cependant, il s’affiche sous la forme d’une devise dans les rapports et est sujet à des conversions monétaires sur la base de la valeur s. *`currencyCode`* et du paramètre de devise par défaut de votre suite de rapports. Pour plus d’informations sur l’utilisation des événements numériques et monétaires, reportez-vous à la section [Produits](/help/implement/js-implementation/page-variables/page-variables.md).

**Configuration de la variable**

La variable `s.events` est activée par défaut pour toutes les implémentations. Les sept événements de conversion préconfigurés sont automatiquement activés pour toutes les nouvelles suites de rapports. Les nouveaux événements personnalisés (event1- [event100 ou event1000](/help/implement/js-implementation/page-variables/page-variables.md)) peuvent être activés par un utilisateur de niveau administrateur à l’aide de la console d’administration.

**Valeurs possibles**

Voici la liste des valeurs possibles pour la variable « events » :

| Événement | Description | Rapports renseignés |
|---|---|---|
| prodView | Consultations produits | Produits |
| scOpen | Ouvrir / Initialiser un nouveau panier | Paniers |
| scAdd | Ajouter un/des article(s) au panier | Ajouts au panier |
| scRemove | Retirer un/des article(s) du panier | Retraits du panier |
| scView | Afficher le panier | Consultations du panier |
| scCheckout | Début du processus de passage en caisse | Achats |
| purchase | Finalisation d’un achat (d’une commande) | Commandes |
| événement1 - événement1000 (événement100 pour un produit ponctuel) | Evénements personnalisés | Événements personnalisés |

**Syntaxe et exemples**

Des événements de compteur sont définis en plaçant les événements souhaités dans la variable `s.events`, dans une liste de valeurs séparées par des virgules (si plusieurs événements doivent être transmis).

```js
s.events="scAdd"
```

```js
s.events="scAdd,event1,event7"
```

```js
s.events="event5"
```

```js
s.events="purchase,event10"
```

Si vous utilisez du code H23 ou une version antérieure, des valeurs entières supérieures à un peuvent être affectés aux événements de compteur.

```js
s.events="event1=10"
```

```js
s.events="scRemove=3,event6,event2=4"
```

L’implémentation d’événements de compteur lorsque des valeurs entières sont affectées traite l’événement comme s’il est déclenché à plusieurs reprises dans la demande d’image. Les événements de compteur ne prennent pas en charge les décimales. Il est recommandé d’utiliser à la place des événements numériques en cas de besoin.
Les événements numériques et monétaires doivent être définis dans la variable [!UICONTROL s.events], mais ils reçoivent leur valeur numérique (24,99, par exemple) dans la variable [!UICONTROL s.products]. Vous avez ainsi la possibilité d’associer des valeurs numériques et monétaires spécifiques à des entrées de produit individuelles.

**Sérialisation d’événements**

Par défaut, un événement est comptabilisé chaque fois qu’il est défini sur votre site.

Reportez-vous à la section [Sérialisation d’événements](/help/implement/js-implementation/event-serialization.md) pour plus d’informations.

**Syntaxe**

```js
s.events="event1:3167fhjkah"
```

**Exemples**

```js
s.events="scAdd:003717174"
```

```js
s.events="scAdd:user228197,event1:577247280,event7:P7fhF8571"
```
