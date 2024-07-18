---
description: Le Créateur de segments permet de comparer et de contraindre les valeurs à l’aide d’opérateurs sélectionnés.
title: Opérateurs de comparaison pour les segments
feature: Segmentation
exl-id: 1ec1ff05-03a9-4151-8fcb-a72ebbce87dd
source-git-commit: 7a47d837eeae65f2e98123aca78029bfeb7ffe9d
workflow-type: tm+mt
source-wordcount: '1105'
ht-degree: 95%

---

# Opérateurs de comparaison pour les segments

Le Créateur de segments vous permet de comparer et de contraindre les valeurs à l’aide d’opérateurs sélectionnés. Il existe trois catégories d’opérateurs : Standard, Data Warehouse et Comptage distinct.

L’astérisque : &#42; est le seul caractère générique pris en charge. Si vous devez rechercher &#42;, vous pouvez l’échapper avec une barre oblique inverse.

**Exemple** : supposons que vous ayez une page nommée « Mon super produit ». La règle de segment &quot;Le nom de page correspond à Mon&#42;produit&quot; correspondra au nom de page ci-dessus. Cependant, la règle &quot;Le nom de page correspond à Mon\\&#42;produit&quot; correspond uniquement au nom de page &quot;Mon&#42;produit&quot;.

## Opérateurs standard

| Opérateur | La dimension, le segment ou l’événement de mesure sélectionné... |
|--- |--- |
| est égal à | Renvoie des éléments qui correspondent exactement à une valeur numérique ou de chaîne. Remarque : Si vous utilisez des caractères génériques, utilisez l’opérateur « correspond à ». |
| n’est pas égal à | Renvoie les éléments qui ne comportent pas une correspondance exacte avec la valeur saisie.  Remarque : Si vous utilisez des caractères génériques, utilisez l’opérateur « ne correspond pas à ». |
| égal à n’importe lequel ; | Renvoie les éléments qui correspondent exactement à n’importe quelle valeur du champ de saisie (jusqu’à 500 éléments). Par exemple, la saisie de « Résultats de la recherche, page d’accueil » avec cet opérateur correspondrait à « Résultats de la recherche » et « Page d’accueil », et serait considérée comme deux éléments. Le champ de saisie de cet opérateur est délimité par des virgules. |
| n’est pas égal à n’importe lequel. | Identifie les éléments qui correspondent exactement à n’importe quelle valeur du champ de saisie (jusqu’à 500 éléments), puis renvoie uniquement les éléments sans ces valeurs. Par exemple, la saisie de « Résultats de la recherche, page d’accueil » avec cet opérateur identifierait « Résultats de la recherche » et « Page d’accueil », puis les exclut des éléments renvoyés. Cet exemple serait considéré comme deux éléments. Le champ de saisie de cet opérateur est délimité par des virgules. |
| contient | Renvoie les éléments qui sont comparés aux sous-chaînes des valeurs saisies. Par exemple, si la règle pour « Page » contient « Recherche », elle correspondra à toute page dont la sous-chaîne est « Recherche », y compris « Résultats de la recherche », « Rechercher » et « En cours de recherche ». La condition « contient » n’est pas sensible à la casse dans Adobe Analytics, mais elle l’est dans Customer Journey Analytics. |
| ne contient pas | Renvoie l’inverse de la règle « contient ». Plus précisément, tous les éléments qui correspondent à la valeur entrée seront exclus des valeurs entrées. Par exemple, si la règle pour « Page » ne contient pas « Recherche », elle ne correspondra à aucune page comportant la sous-chaîne « Recherche », y compris « Résultats de la recherche », « Rechercher » et « En cours de recherche ». Ces valeurs seront exclues des résultats. |
| contient tous les | Renvoie les éléments comparés aux sous-chaînes, notamment plusieurs valeurs associées. Par exemple, la saisie de « Résultats de la recherche » avec cet opérateur correspondrait à « Résultats de la recherche » et « Résultats de recherche » mais pas à « Recherche » ou « Résultats » indépendamment. Cet opérateur correspondrait à Recherche ET Résultats réunis. Le champ de saisie de cet opérateur est délimité par des espaces (100 mots). |
| ne contient pas tous les | Identifie les éléments par rapport aux sous-chaînes (y compris plusieurs valeurs jointes ensemble) puis renvoie uniquement les éléments sans ces valeurs. Par exemple, la saisie de « Résultats de la recherche » avec cet opérateur identifierait « Résultats de la recherche » et « Résultats recherche » (mais pas « Recherche » ni « Résultats » indépendamment), puis exclurait ces éléments. Le champ de saisie de cet opérateur est délimité par des espaces (100 mots). |
| contient n’importe lequel | Renvoie les éléments comparés aux sous-chaînes, notamment plusieurs valeurs associées ou identifiées indépendamment. Par exemple, la saisie de « Résultats de la recherche » avec cet opérateur correspondrait à « Résultats de la recherche », « Résultats de recherche », « Recherche » et « Résultats ». Cet opérateur correspondrait à « Recherche » OU « Résultats » réunis ou indépendants. Le champ de saisie de cet opérateur est délimité par des espaces (100 mots). |
| ne contient pas n’importe lequel | Identifie les éléments d’après les sous-chaînes, puis renvoie les valeurs qui ne contiennent pas ces sous-chaînes. Il peut y avoir plusieurs valeurs jointes ou des valeurs identifiées individuellement. Par exemple, « Résultats de la recherche » correspondrait à « Résultats de la recherche », « Résultats recherche », « Recherche » et « Résultats », où « Résultats » et « Recherche » sont identifiés ensemble ou individuellement. Les éléments qui contiennent ces sous-chaînes seraient ensuite exclus. Le champ de saisie de cet opérateur est délimité par des espaces (100 mots). |
| commence par | Renvoie les éléments qui commencent par le caractère ou les chaînes de la valeur saisie. |
| ne commence pas par | Renvoie tous les éléments qui ne commencent pas par les caractères ou les chaînes des valeurs saisies. Il s’agit de l’inverse de l’opérateur « commence par ». |
| se termine par | Renvoie les éléments qui se terminent par le caractère ou les chaînes de la valeur saisie. |
| ne se termine pas par | Renvoie tous les éléments qui ne se terminent pas par les caractères ou les chaînes de la valeur saisie. Il s’agit de l’inverse de l’opérateur « se termine par ». |
| correspond à | Renvoie des éléments qui correspondent exactement à une valeur numérique ou de chaîne donnée. La clause « correspond à » est sensible à la casse dans Adobe Analytics et dans Customer Journey Analytics. **Remarque :** utilisez cet opérateur lorsque vous utilisez les fonctions de caractère générique (extension métacaractère). Exemples d’« extension métacaractère » :<ul><li>`a*e` correspondrait à `ae`, `abcde`, `adobe` et `a whole sentence`.</li><li>`adob*` correspondrait à `adobe`, `adobe analytics` et `adobo recipe`.</li><li>`*dobe` correspondrait à `dobe`, `adobe` et `cute little dobe`.</li></ul> |
| ne correspond pas à | Renvoie les éléments qui ne comportent pas une correspondance exacte avec la valeur saisie. Remarque : Utilisez cet opérateur lorsque vous utilisez les fonctions de caractère générique (expansion de nom de fichier). |
| existe | Renvoie le nombre d’éléments existants. Par exemple, si vous évaluez la dimension Pages introuvables à l’aide de l’opérateur « existe », le nombre de pages d’erreur existantes est renvoyé. |
| n’existe pas | Renvoie tous les éléments qui n’existent pas. Par exemple, si vous évaluez la dimension Pages introuvables à l’aide de l’opérateur « n’existe pas », le nombre de pages où cette page d’erreur n’existe pas est renvoyé. |

## Opérateurs Data Warehouse

| Opérateur | La dimension, le segment ou l’événement de mesure sélectionné... |
| --- | --- |
| est inférieur à | Renvoie les éléments dont le nombre est inférieur à la valeur saisie. |
| est inférieur ou égal à | Renvoie les éléments dont le nombre est inférieur ou égal à la valeur saisie. |
| est supérieur à | Renvoie les éléments dont le nombre est supérieur à la valeur saisie. |
| est supérieur ou égal à | Renvoie les éléments dont le nombre est supérieur ou égal à la valeur saisie. |

## Opérateurs Comptage distincts

Vous pouvez segmenter un nombre d’éléments distinct dans une dimension. Exemples : « Visiteurs ayant consulté plus de 5 produits distincts » ou « Visites où plus de 5 pages distinctes ont été vues ».

| Opérateur | La dimension, le segment ou l’événement de mesure sélectionné... |
| --- | --- |
| est égal à | Renvoie les éléments de dimension dont le nombre de valeurs uniques est égal à la valeur saisie. |
| n’est pas égal à | Renvoie les éléments de dimension dont le nombre de valeurs uniques n’est pas égal à la valeur saisie. |
| est supérieur à | Renvoie les éléments de dimension dont le nombre de valeurs uniques est supérieur à la valeur saisie. |
| est inférieur à | Renvoie les éléments de dimension dont le nombre de valeurs uniques est inférieur à la valeur saisie. |
| est supérieur ou égal à | Renvoie les éléments de dimension dont le nombre de valeurs uniques est supérieur ou égal à la valeur saisie. |
| est inférieur ou égal à | Renvoie les éléments de dimension dont le nombre de valeurs uniques est inférieur ou égal à la valeur saisie. |

Regardez cette vidéo concernant la segmentation sur des nombres de dimensions distincts :

>[!VIDEO](https://video.tv.adobe.com/v/27257/?quality=12)