---
description: Exemples, remarques et notes syntaxiques concernant l’utilisation de périodes dans des expressions personnalisées.
title: Exemples de plages de dates utilisant des expressions personnalisées
topic: Report builder
uuid: 3f46816d-9eee-4b2d-83be-bf1c9fb97fcf
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Exemples de plages de dates utilisant des expressions personnalisées

Exemples, remarques et notes syntaxiques concernant l’utilisation de périodes dans des expressions personnalisées.

Dans ce tableau, on suppose que nous sommes aujourd’hui le lundi 10 novembre 2011, selon le calendrier grégorien.

| Exemple | Période | Expression personnalisée | Période du rapport |
|---|---|---|---|
|  |  | **Du** | **À** |  |
| 1 | ll y a deux semaines | cw-2w | cw-1w-1d | 26 oct. au 1er nov. |
| 2 | 3 premiers jours du cinquième mois de l’année dernière | cy-1y+4m | cy-1y+4m+2d | 1er mai au 3 mai 2010 |
| 3 | Une semaine complète, commençant il y a 4 semaines | cw-4w | cw-3w-1d | 12 oct. au 18 oct. |
| 4 | Semaine précédente de l’année précédente | cw-53w | cw-52w-1d | 3 nov. au 9 nov. 2010 |
| 5 | Un mois commençant il y a 2 mois | cm-2m | cm-1m-1d | 1er sept. au 30 sept. |
| 6 | Il y a 12 mois au cours de l’année précédente | cm-12m | cm-11m-1d | 1 nov. au 30 nov. 2010 |

## Notes on examples {#section_37801B0D6D364ABAA8DCE3A4C0123B2C}

**Exemple 1**

Si nous sommes aujourd’hui le lundi 10 novembre 2011, prenez la date actuelle et soustrayez une semaine afin d’obtenir la dernière semaine complète d’octobre.

**Exemple 2**

Ajoutez quatre mois au début de l’année (le mois de janvier) afin d’obtenir le mois de mai ; ajoutez deux jours au premier jour du mois pour obtenir le troisième jour du mois.

## Syntax notes {#section_555D6563B2D94FA3BDD801DC0B8C289D}

Il est possible de créer des expressions personnalisées couvrant la plupart des périodes en liant deux termes à l’aide d’un opérateur. Un terme est la combinaison d’un multiplicateur entier et d’une abréviation de période. Exemple de terme : 18d ; exemple d’opérateur : +.

* Les espaces blancs ne sont pas autorisés entre les opérateurs et les termes.
* Utilisez uniquement ces abréviations : cd cw cm cq cy d w m q y
* La bonne pratique est d’utiliser la même référence de date pour la date de début et la date de fin : cd, cd ou cw, cw ou cy, cy. Le mélange de références de dates risque d’engendrer des dates incorrectes à certains moments de l’année.
* Les multiples valides d’abréviations d w m q y sont formés au moyen d’entiers ( 1 2 3 ... ) précédés de l’abréviation, par exemple 53d 3w 5q 9m 2y

   * Les nombres non entiers ne sont pas autorisés.
   * L’abréviation ne peut pas être précédée d’un simple zéro. Par exemple, 0w n’est pas autorisé.

* Les opérateurs suivants permettent de concaténer les abréviations : + -
* Puisqu’on suppose que les périodes sont relatives à la période en cours, le premier terme est une expression qui commence toujours par c.

