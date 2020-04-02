---
description: Ces exemples fournissent des conseils pour importer des classifications numériques 2.
subtopic: Classifications
title: Exemples
topic: Admin tools
uuid: 0553d07f-87c1-4372-90ce-7118a6393a01
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Exemples

Les exemples suivants fournissent des conseils pour importer des classifications numériques 2.

<!-- 

c_example_1__rate.xml

 -->

Dans ce cas, vous avez créé la classification dans le gestionnaire de [!UICONTROL conversions de classification] et vous voulez importer les valeurs de janvier :

| Clé | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` |  | `.2` |
| Product2 | Text2 | `Cost2_jan_var` |  | `.3` |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | revenue | revenue |
| 2010/01/01 - 2010/01/31 | revenue | revenue |

En janvier, Product1 a eu un coût de 20 % des recettes (indiqué dans `~MyCost^~value~`) et Product2 a eu un coût de 30 % des recettes. Comme vous importez une nouvelle ligne, `~MyCost^~id~` est vide.

## Résultats {#section_E0569289C9B34C479C7D2CD9ECBF866E}

Voici un exemple de sortie du rapport :

Période : Janv 2010

Rapport : Produits

| Produits | Recettes | MyCost |
|---|---|---|
| Product1 | 10 000,23 $ | 2 000,05 $ |
| Product2 | 9 000,04 $ | 2 700,01 $ |

<!-- 

c_example_2__rate.xml

 -->

| Clé | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` | 1 | .2 |
| Product2 | Text2 | `Cost2_jan_var` | 2 | .3 |
| Product1 | Text1 | `Cost1_feb_var` |  | .15 |
| Product2 | Text2 | `Cost2_feb_var` |  | .25 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | revenue | revenue |
| 2010/01/01 - 2010/01/31 | revenue | revenue |
| 2010/02/01 - 2010/02/28 | revenue | revenue |
| 2010/02/01 - 2010/02/28 | revenue | revenue |

En février, le coût de Product1 de l’utilisateur a diminué pour atteindre 15 % des recettes et Product2 25 % de ces recettes.

## Résultats {#section_23DF5353AC1B478C88647F222703352C}

Voici un exemple de sortie du rapport :

Période : Janv 2010

Rapport : Produits

| Produits | Recettes | MyCost |
|---|---|---|
| Product1 | 10 000,23 $ | 2 000,05 $ |
| Product2 | 9 000,04 $ | 2 700,01 $ |

Période : Fév 2010

Rapport : Produits

| Produits | Recettes | MyCost |
|---|---|---|
| Product1 | 15 500,75 $ | 2 325,11 $ |
| Product2 | 12 300,52 $ | 3 075,13 $ |

Période : 1er janv 2010 - 28 fév 2010

Rapport : Produits

| Produits | Recettes | MyCost |
|---|---|---|
| Product1 | 25 500,98 $ | 4 325,16 $ |
| Product2 | 21 300,56 $ | 5 775,14 $ |

<!-- 

c_example_3__fixed.xml

 -->

Vous importez donc les données suivantes :

| Clé | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3 000,00 |
| Product2 | Text2 | `Cost2_jan_fixed` |  | 2 000,00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fixed | none |
| 2010/03/01 - 2010/03/31 | fixed | none |

## Résultats {#section_674B57ADB8284B878F9E670038C31464}

Voici un exemple de sortie du rapport :

Période : Mars 2010

Rapport : Produits

| Produits | Recettes | MyCost |
|---|---|---|
| Product1 | 11 023,75 $ | 3 000,00 $ |
| Product2 | 8 000,12 $ | $2 000,00 |

<!-- 

c_example_4__(advanced)_multiple_row_per_time_period.xml

 -->

Dans cet exemple, les frais de livraison de Product1 s’élèvent à 500 $ pour le mois de janvier et 600 $ pour le mois de février.

| Clé | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` | 1 | .2 |
| Product1 | Text1 | `Cost2_jan_fixed` |  | 500 |
| Product1 | Text1 | `Cost1_feb_var` | 2 | .15 |
| Product1 | Text1 | `Cost2_feb_fixed` |  | 600 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | revenue | revenue |
| 2010/01/01 - 2010/01/31 | fixed | none |
| 2010/02/01 - 2010/01/31 | revenue | revenue |
| 2010/02/01 - 2010/01/31 | fixed | none |

Les lignes précédemment importées possèdent un ID, ce qui indique qu’elles ne correspondent pas à de nouveaux coûts.

## Résultats {#section_2096084176614B9AA60F97D5853CB9EA}

Voici un exemple de sortie du rapport :

Période : Janv 2010

Rapport : Produits

| Produits | Recettes | MyCost |
|---|---|---|
| Product1 | 10 000,23 $ | 2 500,05 $ |

> [!NOTE] Cette fonctionnalité est destinée aux utilisateurs expérimentés qui souhaitent déterminer des valeurs approximatives. Les informations obtenues ne doivent pas être considérées comme des valeurs exactes.

<!-- 

c_example_5__identical_rate_hinge.xml

 -->

Voici un exemple :

| Clé | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_var` |  | 1 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | order | order |

## Résultats {#section_39E24ECCC3B34C9AADC25572662750E5}

Voici un exemple de sortie du rapport :

Période : Mars 2010

Rapport : Produits par page

| Produits par page | Commandes | MyCost |
|---|---|---|
| Product1 | 1000 | 1 000,00 $ |
| Page d’accueil | 600 | $600 |
| Panier | 400 | 400 $ |

<!-- 

c_example_5__fixed_no_hinge.xml

 -->

| Clé | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3 000,00 |
| Product2 | Text2 | `Cost2_mar_fixed` |  | 2 000,00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fixed | none |
| 2010/03/01 - 2010/03/31 | fixed | none |

## Résultats {#section_7F5F5970077D4E14A5DC91495E23540D}

Voici un exemple de sortie du rapport :

Période : Mars 2010

Rapport : Produits par page

| Produits par page | Commandes | MyCost |
|---|---|---|
| Product1 | 1000 | 3 000,00 $ |
| Page d’accueil | 600 | 0 |
| Panier | 400 | 0 |

<!-- 

c_example_7__fixed_hinge.xml

 -->

Vous importez donc les données suivantes :

| Clé | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3 000,00 |
| Product2 | Text2 | `Cost2_mar_fixed` |  | 2 000,00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fixed | revenue |
| 2010/03/01 - 2010/03/31 | fixed | revenue |

## Résultats {#section_5953BB6FD0CE4EF69D1D60B8B1203431}

Voici un exemple de sortie du rapport :

Période : Mars 2010

Rapport : Produits par page

| Produits par page | Commandes | MyCost |
|---|---|---|
| Product1 | 1000 | 3 000,00 $ |
| Page d’accueil | 600 | 1 800,00 $ |
| Panier | 400 | 1 200,00 $ |

<!-- 

c_example_7_continued__different_rate_hinge.xml

 -->

Vous importez donc les données suivantes :

| Clé | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | Cost1_mar_fixed |  | 3 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | order | revenue |

## Résultats {#section_6E2604D9A3B0455585EFF0F80FF54127}

Voici un exemple de sortie du rapport :

Période : Mars 2010

Rapport : Produits par page

| Produits par page | Commandes | MyCost |
|---|---|---|
| Product1 | 1000 | 3 000,00 $ |
| Page d’accueil | 600 | 1 000,00 $ |
| Panier | 400 | 2 000,00 $ |

