---
description: Exemples, remarques et notes syntaxiques concernant l’utilisation de périodes dans des expressions personnalisées.
title: Exemples de périodes utilisant des expressions personnalisées
uuid: 3f46816d-9eee-4b2d-83be-bf1c9fb97fcf
feature: Report Builder
role: User, Admin
exl-id: d936dd4e-d330-4ed9-a979-3273397d7d92
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 13%

---

# Exemples de périodes utilisant des expressions personnalisées

{{legacy-arb}}

Exemples, remarques et notes syntaxiques concernant l’utilisation de périodes dans des expressions personnalisées.

Le tableau suppose que la date d’aujourd’hui est le lundi 10 novembre 2011, selon le calendrier grégorien.

| Exemple | Période | Personnaliser l’expression | Plage de dates du rapport |
|---|---|---|---|
|  | | **De** | **À** |
| 1 | Il y a deux semaines | `cw-2w  \| cw-1w-1d` | 26 oct. au 1 nov. |
| 2 | Les 3 premiers jours du cinquième mois de l’année dernière | `cy-1y+4m  \| cy-1y+4m+2d` | 1er mai au 3 mai 2010 |
| 3 | Une semaine complète, à partir de 4 semaines auparavant | `cw-4w  \| cw-3w-1d` | Du 12 octobre au 18 octobre |
| 4 | Semaine dernière dans l’année précédente | `cw-53w  \| cw-52w-1d` | Novembre au 9 novembre 2010 |
| 5 | Un mois à partir de 2 mois auparavant | `cm-2m  \| cm-1m-1d` | Du 1er septembre au 30 septembre |
| 6 | il y a 12 mois de l&#39;année précédente | `cm-12m  \| cm-11m-1d` | 1er novembre au 30 novembre 2010 |

## Remarques sur les exemples {#section_37801B0D6D364ABAA8DCE3A4C0123B2C}

**Exemple 1**

Si nous sommes le lundi 10 novembre 2011, soustrayez la date actuelle d&#39;une semaine pour obtenir la dernière semaine complète d&#39;octobre.

**Exemple 2**

Ajoutez quatre mois au début de l’année (le mois de janvier) pour obtenir le mois de mai ; ajoutez deux jours au premier jour du mois pour obtenir le troisième jour du mois.

## Notes de syntaxe {#section_555D6563B2D94FA3BDD801DC0B8C289D}

Il est possible de créer des expressions personnalisées couvrant la plupart des périodes en liant deux termes à un opérateur. Un terme est une combinaison d&#39;un multiplicateur entier et d&#39;une abréviation de période. Un exemple de terme est 18d. Un exemple d’opérateur est +.

* Les espaces ne sont pas autorisés entre les opérateurs et les termes.
* Utilisez uniquement ces abréviations : cd cw cm cq cy d w m q y
* La bonne pratique consiste à utiliser la même référence de date dans la date de début et dans la date de fin : cd, cd ou cw, cw ou cy, cy. Le mélange des références de date peut entraîner des dates non valides à certains moments de l’année.
* Les multiples valides des abréviations d w m q y sont formés au moyen de nombres entiers ( 1 2 3 ... ) précédés de l’abréviation, tels que 53d 3w 5q 9m 2y
* Les nombres non entiers ne sont pas autorisés.
* Ne faites pas précéder l’abréviation de zéro. Par exemple, 0w n’est pas autorisé.
* Les opérateurs suivants sont utilisés pour concaténer des abréviations : + -
* Comme les périodes doivent être prises en compte par rapport à la période en cours, le premier terme d’une expression commence toujours par c.
