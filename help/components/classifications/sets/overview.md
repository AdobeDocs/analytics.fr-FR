---
title: Vue d’ensemble des jeux de classifications
description: Découvrez comment utiliser des jeux de classifications pour gérer les données de classification. Découvrez en quoi les jeux de classifications diffèrent des classifications héritées.
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
feature: Classifications
source-git-commit: 8a7dd06a26e6a4ad06c224543bc7fdda33ba7aaa
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Vue d’ensemble des jeux de classifications

Les jeux de classifications fournissent une interface unique pour gérer les classifications et les règles. Ce workflow combine la création de classifications dans les [Paramètres de la suite de rapports](/help/admin/tools/manage-rs/report-suites-admin.md) avec l’[Importateur de classifications](/help/components/classifications/sets/manage-sets.md). Le résultat est une interface intuitive unique pour créer et gérer des données de classification.


## Jeux de classifications et classifications héritées

La principale différence entre les jeux de classifications et les classifications héritées réside dans le fait que les jeux de classifications combinent toutes les fonctionnalités dans une seule interface, alors que les classifications héritées reposent sur trois interfaces.

### Classifications héritées

![Classification héritée](/help/components/classifications/sets/assets/classifications-legacy.svg)

Dans les classifications héritées, les classifications ![Schéma](/help/assets/icons2/Schema.svg) (comme pour le trafic, les conversions, les canaux marketing, etc.) ont chacune leur propre dimension (clé ![Clé](/help/assets/icons2/Key.svg)). Vous définissez ces classifications dans le cadre de vos [Paramètres de suite de rapports](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-classifications.md).

Vous définissez les règles ![BidRule](/help/assets/icons/BidRule.svg) séparément dans les jeux de règles au sein de l’interface [Créateur de règles de classification](/help/components/classifications/crb/classification-rule-builder.md). Dans cette interface, vous associez un jeu de règles à une ou plusieurs suites de rapports.

Utilisez l’[Importateur de classifications](/help/components/classifications/importer/c-working-with-saint.md) pour télécharger un modèle ![DocumentFragment](/help/assets/icons/DocumentFragment.svg), importer des classifications ![UploadToCloud](/help/assets/icons/UploadToCloud.svg) ou exporter des classifications ![Download](/help/assets/icons/Download.svg) à partir d’une combinaison suite de rapports - clé (jeu de données).



### Jeux de classifications

![Jeux de classifications](./assets/classifications-sets.svg)

Les jeux de classifications combinent toutes les interfaces de classification héritées en une seule. Chaque jeu de classifications définit :

* Un ou plusieurs abonnements, qui sont la combinaison des ![Données](/help/assets/icons2/Data.svg) d’une suite de rapports et de la dimension ![Clé](/help/assets/icons2/Key.svg) (clé), que vous souhaitez classer. Si vous souhaitez classer les produits en fonction d’un SKU de produit, vous pouvez définir toutes les suites de rapports avec une dimension de SKU de produit applicable. De plus, vous n’avez pas à répliquer les classifications entre les suites de rapports comme dans l’interface des classifications héritées.
* Une liste de classifications ![Schéma](/help/assets/icons2/Schema.svg) (schéma) pour la clé. Par exemple, pour les classifications de produits, vous pouvez spécifier la catégorie, la couleur, la taille, le genre, etc. Une fois vos classifications définies, vous pouvez télécharger un modèle ![DocumentFragment](/help/assets/icons/DocumentFragment.svg), charger des données de classification ![UploadToCloud](/help/assets/icons/UploadToCloud.svg), télécharger des données de classification ![Download](/help/assets/icons/Download.svg), etc.
* Une ou plusieurs règles ![BidRule](/help/assets/icons/BidRule.svg) pour prendre en charge les classifications.


Pour accéder au menu **[!UICONTROL Jeux de classifications]** à partir du menu **[!UICONTROL Composants]** dans l’interface d’Adobe Analytics, vous devez être un administrateur ou une administratrice de produit ou appartenir à un profil de produit contenant l’élément d’autorisation [!UICONTROL Outils de suites de rapports] > [!UICONTROL Classifications]. Notez que les interfaces de gestion des classifications héritées sont disponibles à partir du menu **[!UICONTROL Admin]**.

Les jeux de classifications se composent de trois zones fonctionnelles :

* [**[!UICONTROL Jeux de classifications]**](manage-sets.md) : créez, modifiez et supprimez des jeux de classifications.
* [**[!UICONTROL Traitements]**](job-manager.md) : affichez le statut des traitements des jeux de classifications.
* [**[!UICONTROL Consolidations]**](consolidations/manage.md) : combinez plusieurs jeux de classifications en un seul jeu de classifications.


## Workflow

Le workflow des jeux de classifications implique généralement les étapes suivantes :

1. Déterminez les combinaisons de suite de rapports et de dimension pour lesquelles vous souhaitez créer un jeu de classifications. Par exemple, définissez un jeu de classifications de produits que vous créez pour toute suite de rapports pour laquelle vous souhaitez classer les produits avec plus de détails. Par exemple, les détails tels que la catégorie et la couleur.
1. [Créez un jeu de classifications](/help/components/classifications/sets/create-set.md) avec des abonnements à une ou plusieurs suites de rapports et combinaisons de dimensions clés qui identifient les produits. Par exemple :

   | Suite de rapports | Dimension clé |
   |---|---|
   | Suite de rapports 1 | ID de produit |
   | Suite de rapports 2 | SKU du produit |

1. [Ajoutez les classifications](/help/components/classifications/sets/manage/schema.md#add) que vous avez identifiées au schéma du jeu de classifications. Par exemple :

   | Nom de classification | Nom d’identité |
   |---|---|
   | Catégorie | Catégorie |
   | Couleur | couleur |

1. Créez manuellement un fichier contenant des données de classification. [Utilisez un modèle](/help/components/classifications/sets/manage/schema.md#template) pour vous assurer d’utiliser le [format de fichier pris en charge](data-files.md#classification-set-file-formats) et les colonnes du fichier. Ajoutez ensuite les données au fichier de modèle.

   Vous pouvez également exporter des données directement à partir de votre catalogue de produits dans les [formats de fichiers pris en charge](data-files.md#classification-set-file-formats) avec des colonnes qui adhèrent au modèle. Par exemple, un fichier CSV tel que :

   ```
   Key,Category,Color
   Adobe Nike Tech Fleece Full-Zip Hoodie - Men's,Men,Black
   Adobe Nike Tech Fleece Full-Zip Hoodie - Women's,Women,Black
   Men's North Face Adobe Jacket,Men,Black
   Nike Air Hybrid 2 Golf Bag,Equipment,Blue
   STITCH&reg; Ultimate Garment Bag,Equipment,Brown
   Adobe Analytics Training Tee - Navy,Men,Navy
   AirPods Pro 2,Electronics,White
   Adobe Analytics Training Tee - Green,Men,Green
   Women's North Face Adobe Jacket,Women,Blue
   Adobe Analytics Training Tee - Grey,Men,Gray
   Adobe Analytics One Million Views - Grey,Equipment,Grey
   Adobe and MGM Tee - White,Women,White
   Adobe and MGM Tee - Charcoal,Women,Charcoal
   ```

   Dans le fichier de données de classification, vous faites référence à la dimension clé de chaque suite de rapports (par exemple : **[!UICONTROL Identifiant du produit]** et **[!UICONTROL SKU du produit]**) à l’aide de `Key`. Vous faites également référence à chaque classification à l’aide du **[!UICONTROL Nom de classification]** (par exemple `Category` ou `Color`).

1. [Chargez](/help/components/classifications/sets/manage/schema.md#upload) le fichier qui contient les données de classification dans le schéma du jeu de classifications.

1. Configurez [règles](manage/rules.md) pour classer automatiquement les données entrantes et les données du passé.

1. [Automatisez](/help/components/classifications/sets/manage/schema.md#automate) le processus de mises à jour de votre catalogue de produits que vous souhaitez voir répercuter dans les données de classification à l’aide d’un emplacement cloud.

1. [Téléchargez](/help/components/classifications/sets/manage/schema.md#download) vos données de classification pour valider le contenu.

1. [Examinez l’historique de traitement](/help/components/classifications/sets/job-manager.md) pour afficher les résultats de vos actions (chargement, téléchargement, modèle, etc.) sur les classifications.
1. Si plusieurs jeux de classifications similaires résultent d’une migration depuis la fonctionnalité de classification héritée, [consolidez](consolidations/manage.md) ces jeux de classifications.



## Améliorations

L’architecture back-end publiée avec les jeux de classifications contient plusieurs améliorations notables :

* Réduction du temps de traitement (de 72 heures à 24 heures).
* Une interface d’utilisation repensée pour gérer les classifications.
* Option d’utiliser des données de classification dans Adobe Experience Platform à l’avenir via le [connecteur source Adobe Analytics pour les données de classification.](https://experienceleague.adobe.com/fr/docs/experience-platform/sources/connectors/adobe-applications/classifications)

L’architecture back-end publiée avec les jeux de classifications contient également plusieurs modifications notables :

* Lors de l’utilisation du navigateur ou de l’import automatisé, l’option **[!UICONTROL Remplacer en cas de conflit]** est toujours activé.
* Lors de l’utilisation du navigateur ou de l’import automatisé, l’option permettant d’exporter immédiatement après l’import n’est plus prise en charge. Les exports doivent être lancés séparément.
* Le point d’entrée de l’API `GetDimensions` Analytics 2.0 renvoie désormais des identifiants de chaîne pour les classifications au lieu des identifiants numériques. Les identifiants numériques peuvent toujours être utilisés, mais il esst recommandé d’utiliser les nouveaux identifiants de chaîne si possible. Les identifiants numériques peuvent être récupérés à l’aide du paramètre de chaîne de requête `?expansion=hidden`.

>[!IMPORTANT]
>
>Les performances des jeux de classifications dépendent principalement du nombre de valeurs de clés uniques qui contiennent des données. Faites preuve de prudence lorsque vous avez des variables qui contiennent un grand nombre de valeurs uniques. Cela s’applique tout particulièrement lorsque vous combinez des variables de plusieurs suites de rapports et dimensions dans un seul jeu de classifications.

## Limites

* Les jeux de classifications ne prennent pas encore en charge les règles. La fonctionnalité Règles est ajoutée à l’interface des jeux de classifications avant que la fonctionnalité [créateur de règles hérité](/help/components/classifications/crb/classification-rule-builder.md) ne devienne indisponible.
* Il n’existe aucune migration des règles et configurations de classification héritées vers des jeux de classifications. Un utilitaire de migration est ajouté à l’interface des jeux de classifications avant que la fonctionnalité de classification héritée ne devienne indisponible.
