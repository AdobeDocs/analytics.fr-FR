---
description: La colonne « Pré » contient les données telles qu’elles ont été envoyées à la collecte de données. La colonne « Post » contient la valeur après traitement.
keywords: Flux de données ; tâche ; « pré » ; Colonne Post ; respect de la casse
seo-description: La colonne « Pré » contient les données telles qu’elles ont été envoyées à la collecte de données. La colonne « Post » contient la valeur après traitement.
seo-title: Colonnes Pré et Post
solution: Analytics
title: Colonnes Pré et Post
topic: Reports and Analytics
uuid: a 415327 b -6151-4 d 08-b 8 b 9-5 aaa 2348 eb 0 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Colonnes Pré et Post

La colonne « Pré » contient les données telles qu’elles ont été envoyées à la collecte de données. La colonne « Post » contient la valeur après traitement.

Par exemple, la persistance de la variable, les règles de traitement, les règles VISTA et la conversion de devise peuvent modifier la valeur finale enregistrée pour une variable affichée dans la colonne « Post ». Pour la plupart des calculs, il est conseillé d’utiliser la colonne « Post », sauf si vous appliquez une logique métier personnalisée (application d’une formule personnalisée pour déterminer l’attribution, par exemple).

Si une colonne ne contient pas de version « Pré » ou « Post » (`visit_num`, par exemple), elle peut être considérée comme une colonne « Post ». Columns prefixed with " `pre_`" typically contain data that was populated by Adobe and not sent by your implementation. For example, `pre_browser` is populated by Adobe, but `evar1` is populated by your implementation. Both of these columns have a " `post_`" column ( `post_browser`, `post_evar1`), which contains the value used by reporting.

## Respect de la casse des valeurs {#section_F979E099BFAB4AFEBEA2D7E228963CE8}

Aux fins de création de rapports, la casse de la plupart des variables d’Analytics n’est pas prise en compte, ce qui signifie qu’une valeur est considérée comme unique quelle que soit sa casse (par exemple, « neige », « Neige », « NEIGE » et « nEIGE » sont considérés comme une seule et même valeur). Toutefois, aux fins d’affichage, la casse est tout de même prise en compte puisque la plupart des utilisateurs préfèrent afficher des caractères à casse mixte dans les rapports.

Lors du traitement du flux de données, vous pouvez utiliser uniquement des minuscules aux fins de comparaison ; toutefois, vous souhaiterez sans doute préserver la casse aux fins d’affichage.

Si vous observez différentes variations de la casse pour une même valeur entre les colonnes « Pré » et « Post » (par exemple, « neige » dans la colonne « Pré » et « Neige » dans la colonne « Post »), cela signifie que vous transmettez des versions en majuscules et en minuscules de la même valeur sur votre site. Les différences de casse dans la colonne « Post » étaient précédemment transmises puis stockées dans un cookie virtuel ou étaient traitées à peu près en même temps pour cette suite de rapports. Par exemple :

Accès 1 : s.list1=“Gouttière,Persan,Siamois”;

Accès 2 : s.list1=“gouttière,persan,siamois”;

Lorsque l’accès 2 est reporté dans le flux de données, la colonne « Pré » contiendra exactement la même casse que celle qui a été transmise (gouttière,persan,siamois), mais la valeur issue de l’accès 1 persistera probablement pour cette visite et sera reportée dans la colonne « Post » (qui indiquera Gouttière,Persan,Siamois) puisque les accès 1 et 2 contiennent exactement la même valeur en cas de comparaison sans tenir compte de la casse.
