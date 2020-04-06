---
description: Les filtres permettent de limiter le rapport en incluant ou en excluant des éléments de ligne qui correspondent à un filtre.
title: Filtrage des données de rapport
topic: Reports and analytics
uuid: b6dcaaf7-61f0-4793-870d-e1d156575d5a
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Filtrer les données du rapport {#concept_09DC5B986A644738B12204DAC76A90E1}

Les filtres permettent de limiter le rapport en incluant ou en excluant des éléments de ligne qui correspondent à un filtre.

## Filtre simple  {#section_5C4DE873F8D5484BB77F38A4AEB57B4A}

![](assets/filter.png)

Le filtre simple apparaît sur la plupart des rapports pour vous permettre de trouver rapidement des éléments de lignes spécifiques. Les filtres simples n’utilisent pas de caractères spéciaux. De ce fait, les caractères `-, ", ', +` ainsi que tout autre caractère spécial, correspondent à la valeur littérale dans le rapport. Vous pouvez rechercher des lignes qui contiennent plusieurs termes à l’aide d’un espace.

Par exemple :

```
help search
```

Correspond aux pages suivantes :

```
help:Search
help:Paid Search Detection
help:Configure paid search detection
help:Search Keywords Report
help:Internal Search Term
```

## Filtres avancés {#section_E016626C084640E8A066B2FDA5B932BF}

Les  avancées vous permettent de contrôler la portée de votre recherche à l’aide d’un ensemble de  de. Vous pouvez choisir de faire correspondre tous les  ou n’importe quel  de.

![](assets/advanced_filter.png)

**Contient**

Correspond si le terme se trouve n’importe où dans l’élément de ligne. Le filtre fonctionne de la même manière que le filtre simple.

>[!NOTE] Les espaces ne peuvent pas être utilisés dans les filtres, car ils jouent le rôle de délimiteurs dans les recherches.

**Ne contient pas**

Correspond si le terme est introuvable dans l’élément de ligne. Vous pouvez utiliser les filtres « non spécifié », « aucun », « mot-clé indisponible » ainsi que d’autres [valeurs spéciales](https://marketing.adobe.com/resources/help/fr_FR/reference/none-unspecified-unknown-other.html) depuis les rapports utilisant « Ne contient pas ».

Ne contient pas : `none`

Pour un filtre plus précis, vous pouvez utiliser un filtre avancé (caractères spéciaux) :

* Avancé (caractères spéciaux) : `-^none$`
* Avancé (caractères spéciaux) : `-"keyword unavailable"`

Par exemple, l’élément de ligne suivant est filtré par le critère &quot;Ne contient pas&quot;, mais pas par le critère &quot;Avancé (Caractère spécial)&quot; :

```
help:Rename the None classification key
```

**Contient un(e) parmi**

Correspond si des termes, séparés par des espaces, se trouvent dans l’élément de ligne. Le filtre suivant affiche toutes les pages qui contiennent &quot;mens&quot; ou &quot;sale&quot; :

Contient un(e) parmi: `mens sale`

Correspond aux pages suivantes :

```
Womens
Mens
Mens:Desk & TravelJewelry & Accessories:Accessories:Hats:Mens
Sale & Values
```

**Est égal à**

Correspond si l’ensemble de l’élément de ligne, y compris les espaces et autres caractères, correspond à l’expression spécifiée.

Est égal à: `mens:desk & travel`

`Mens:Desk & Travel`

**Starts With (Commence par)**

Correspond si l’élément de ligne, y compris les espaces et autres caractères,  avec la phrase spécifiée.

Commence par: `mens`

Correspond aux pages suivantes :

```
Mens
Mens:Desk & Travel
Mens:Apparel
Mens Perfume Spray
Mens Hemp/Bamboo Flip Flops
```

**Ends With (Se termine par)**

Correspond si l’élément de ligne, y compris les espaces et autres caractères, se termine par la phrase spécifiée.

Se termine par: `jean`

Correspond aux pages suivantes :

```
Bell Bottom Jean
Velvet Dream Skinny Leg Jean
Dark Slimmer Jean
Bling Belt High Waist Jean
Ocean Blue Jean
```

## Avancé (caractères spéciaux) {#section_83DA3B6C23EB4C119DB6D74062DB501D}

Les options avancées vous permettent d’effectuer des recherches génériques et d’autres recherches complexes.

| Avancé (caractères spéciaux) | Description |
|--- |--- |
| `" "` | Correspond à une phrase exacte. |
| `*` | Caractère générique, correspondance maximale. <br>Par exemple, `r*p` correspond à « Registration Signup ». |
| `^` | Commence par. <br>N’incluez pas d’espace entre le caractère spécial et l’expression à rechercher. |
| `$` | Se termine par. <br>N’incluez pas d’espace entre le caractère spécial et l’expression à rechercher. |
| `-` | Pas. <br>N’incluez pas d’espace entre le caractère spécial et l’expression à rechercher. |
| `|` | Ou <br>Remarque : vous devez inclure un espace de chaque côté de la barre verticale, `" | "` |

## Création de filtres spécifiques aux rapports {#task_DEBB0632411D4CA8AA0B3BA267A5B35F}

Cette section décrit la procédure à suivre pour créer des  de rapports.

<!-- 

t_reports_filter_specific.xml

 -->

Certains rapports contiennent un filtre spécifique à ce rapport. Par exemple, un [!UICONTROL Purchase Conversion Funnel Report] filtre permet de filtrer par pages Web. Un [!UICONTROL Geosegmentation Report] permet de filtrer par région géographique. D’autres rapports comportent d’autres  spécifiques à ces rapports.

Lorsque vous accédez à ces  de, vous pouvez voir les mesures des rapports pour les éléments spécifiés dans le  du.

**Pour créer des  spécifiques aux rapports**

1. Générez un rapport, par exemple [!UICONTROL Purchase Report] ( **[!UICONTROL Site Metrics]** > **[!UICONTROL Purchases]** > **[!UICONTROL Purchase Conversion Funnel]**).
1. In the report header, click the **[!UICONTROL Filter]** link.
1. Sur la [!UICONTROL Filter Selector] page, cliquez sur **[!UICONTROL Apply a Filter]**, puis sélectionnez un type de filtre.
1. To search for an item, type a character string in the **[!UICONTROL Search]** field.
1. Cliquez sur **[!UICONTROL OK]**.

## Ajout d’un filtre de corrélation {#task_065042E384DA4BF3864C58AF2B88D6E2}

Cette section décrit la procédure à suivre pour ajouter un filtre de corrélation.

<!-- 

t_reports_correlation_filter.xml

 -->

Certains rapports vous permettent d’ajouter des  de corrélation personnalisés. Par exemple, si vous affichez le rapport [!UICONTROL Pages Report] pour une suite de rapports dont les sections du site sont corrélées à une page Femmes, vous pouvez créer une règle de filtre qui génère un rapport affichant les pages les plus populaires lorsque Sections du site = Femmes.

Vous pouvez filtrer les données affichées dans un rapport de corrélation à l’aide de n’importe quelle corrélation disponible. Cet exemple montre comment ajouter un filtre de corrélation de moteur de recherche.

**Pour ajouter un filtre de corrélation**

1. Exécutez un rapport qui prend en charge les corrélations. (Voir [Exécution d’un rapport de ventilation](/help/analyze/reports-analytics/reports-customize/breakdowns.md#task_F685624830E64C829C8BE6435A107F69).)
1. In the report header, click the **[!UICONTROL Correlation Filter]** link.
1. Sous [!UICONTROL Filter Rule Creator], sélectionnez un  à corréler avec un élément.
1. Cliquez sur **[!UICONTROL OK.]**
