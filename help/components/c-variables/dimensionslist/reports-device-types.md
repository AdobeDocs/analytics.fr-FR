---
description: Regroupe les appareils mobiles en téléphones mobiles, tablettes, liseuses électroniques, consoles de jeu, télévisions, boîtiers décodeurs, lecteurs multimédias et autres catégories de niveau supérieur pour vous permettre de consulter la distribution entre les types d’appareils mobiles.
title: Types de périphérique
topic: Reports
uuid: e1224769-9a94-4cad-a1ed-e285d60d23f3
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Types de périphérique

Regroupe les appareils mobiles en téléphones mobiles, tablettes, liseuses électroniques, consoles de jeu, télévisions, boîtiers décodeurs, lecteurs multimédias et autres catégories de niveau supérieur pour vous permettre de consulter la distribution entre les types d’appareils mobiles.

Cette dimension est également utile pour définir les segments pour les utilisateurs de téléphones et de tablettes en segmentant lorsque Type de périphérique mobile est égal à « type de périphérique ».

**Données dynamiques de périphérique**

Cette dimension utilise des données de périphérique dynamiques qui sont continuellement mises à jour lorsque de nouveaux périphériques sont mis sur le marché et identifiés. Par exemple, une nouvelle tablette sortie au cours du mois en cours peut être mal identifiée, car elle n’existe pas encore dans la base de données des périphériques. Lorsque la base de données des périphériques est mise à jour avec le nouveau périphérique, toutes les modifications qui en résultent sont appliquées à toutes les dates de création de rapports (pas aux données historiques). De ce fait, vous pourrez constater de légères variations sur ce rapport pour les dates historiques dans le temps. En règle générale, le rapport le plus à jour comporte les données les plus exactes pour une période de création de rapports.

Les données de ce rapport sont renseignées à l’aide de la chaîne d’agent utilisateur du visiteur.

>[!Note] :
>seules les modifications apportées à un identifiant mobile existant sont rétroactives. Si le périphérique est nouveau et dépourvu d’identifiant mobile, les seules données qui sont liées à ce périphérique commencent à la date d’ajout d’un identifiant à la base de données des périphériques.
