---
title: Format du fichier de source de données
description: Générer correctement un fichier à utiliser dans les sources de données.
exl-id: 6632b970-e931-4272-a69b-c1130ad6475f
feature: Data Sources
role: Admin
source-git-commit: cc25fe304d9cab3db3fa2ddd306338ff3bb88a55
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 5%

---

# Format du fichier de source de données

Les fichiers de source de données possèdent les propriétés suivantes :

* Le fichier est au format `.txt`.
* Les lignes commentées commencent par « `#` » et sont facultatives.
* La première ligne non commentée contient les en-têtes du fichier.
* La première valeur de chaque ligne est la date, au format `MM/DD/YYYY` ou `MM/DD/YYYY/HH/mm/SS`.
* Les valeurs de chaque ligne, y compris les en-têtes, sont délimitées par des tabulations.
* Chaque ligne doit comporter au moins une dimension et une mesure.

## Commentaires

Toute ligne commençant par « `#` » est un commentaire. Lors du téléchargement d’un fichier de modèle de source de données, les deux premières lignes sont des commentaires.

* Le premier commentaire indique le type de modèle que vous avez configuré pour la source de données, l’ID utilisateur principal qui a créé la source de données et l’ID de source de données.
* Le deuxième commentaire fournit des noms conviviaux pour chacun des en-têtes inclus dans le fichier de modèle.

Toutes les lignes de commentaire sont ignorées par Adobe lors du traitement du fichier. Vous pouvez donc supprimer les commentaires du modèle ou ajouter les vôtres dans tout le fichier. Seules les lignes complètes peuvent être commentées ; vous ne pouvez pas commenter des champs individuels ou des lignes partielles.

## En-têtes

Lors du chargement de fichiers de source de données, des en-têtes de colonne sont requis. Ces en-têtes de colonne ne sont pas sensibles à la casse, mais des espaces sont nécessaires (par exemple, `eVar1` est un en-tête non valide, tandis que `EVAR 1` est valide). Les en-têtes de colonne s’appliquent à toutes les suites de rapports. Utilisez les tableaux suivants pour vous assurer que chaque en-tête de votre fichier de source de données est correctement défini.

>[!TIP]
>
>Vous pouvez créer un fichier de sources de données à partir de zéro si vous incluez les en-têtes corrects dans votre fichier de source de données. Le nombre d’en-têtes que vous pouvez inclure dans un seul fichier n’est pas limité. Cependant, chaque ligne ne peut contenir qu’un maximum de 4 096 octets.

| Dimension | En-tête de la source de données |
| --- | --- |
| [Catégorie](/help/components/dimensions/category.md) | `Category` |
| [eVar1 - eVar250](/help/components/dimensions/evar.md) | `Evar 1` - `Evar 250` |
| [ Canal marketing ](/help/components/dimensions/marketing-channel.md) | `Marketing Channel` |
| [Détails du canal marketing](/help/components/dimensions/marketing-detail.md) | `Marketing Channel Detail` |
| [Produit](/help/components/dimensions/product.md) | `Product` |
| [Code de suivi](/help/components/dimensions/tracking-code.md) | `Tracking Code` |
| [ID de transaction](/help/implement/vars/page-vars/transactionid.md) | `transactionID` |
| [Code postal](/help/components/dimensions/zip-code.md) | `Zip` |

{style="table-layout:auto"}

Les dimensions et les mesures se trouvent dans la même ligne d’en-tête.

| Mesure | En-tête de la source de données |
| --- | --- |
| [Ajouts au panier](/help/components/metrics/cart-additions.md) | `Cart Adds` |
| [Retraits du panier](/help/components/metrics/cart-removals.md) | `Cart Removes` |
| [Consultations du panier](/help/components/metrics/cart-views.md) | `Cart Views` |
| [Paniers](/help/components/metrics/carts.md) | `Cart Opens` |
| [Passages en caisse](/help/components/metrics/checkouts.md) | `Checkouts` |
| [Événements personnalisés](/help/components/metrics/custom-events.md) | `Event 1` - `Event 1000` |
| [Commandes](/help/components/metrics/orders.md) | `Orders` |
| [Recettes](/help/components/metrics/revenue.md) | `Price` |
| [Unités](/help/components/metrics/units.md) | `Quantity` |

{style="table-layout:auto"}

Adobe ne prend en charge les sources de données pour aucune autre dimension ou mesure. Si des variables au-delà de ce qui est répertorié dans les tableaux ci-dessus sont requises, pensez à utiliser l’[API Bulk Data Insertion](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/) à la place.

## Date

La première valeur de chaque ligne **doit** être la date. Le format de date doit être dans l’un des formats suivants :

* **`MM/DD/YYYY/HH/mm/SS`**
* **`MM/DD/YYYY`**

L’omission des heures, minutes et secondes définit automatiquement l’horodatage sur 12 heures pour ce jour.

Un seul fichier de source de données prend en charge jusqu’à 90 jours uniques. Si vous souhaitez inclure plus de 90 jours uniques dans un chargement, divisez vos données en plusieurs fichiers.

## Dimension et données de mesure

Les valeurs suivantes après la date de chaque ligne contiennent les données à charger. Chaque ligne correspond à cet horodatage respectif. Assurez-vous que le même nombre d’onglets existe sur chaque ligne. Les colonnes peuvent être dans n’importe quel ordre. Assurez-vous que les données de chaque ligne s’alignent avec les en-têtes en haut. La quantité maximale de données qu’une seule ligne peut contenir est de 4 096 octets.

Les données Dimension ne peuvent pas contenir de points-virgules (`;`). Les lignes contenant des points-virgules sont ignorées.

## Étapes suivantes

[Chargement de fichier](file-upload.md) : découvrez le processus de chargement d’un fichier de sources de données en vue de son ingestion par Adobe.
