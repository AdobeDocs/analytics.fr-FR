---
title: Cas d’utilisation de la comparaison de segments
description: Découvrez des cas d’utilisation concrets sur la manière dont le panneau de comparaison de segments peut être utilisé pour mieux comprendre la stratégie marketing.
keywords: Segment IQ
translation-type: tm+mt
source-git-commit: ca9f1ed00295b556250894ae4e7fa377ef8a593d

---


# Cas d’utilisation de Segment IQ

Le panneau de comparaison de segments est une fonctionnalité largement utilisée dans Analysis Workspace. Les clients découvrent fréquemment de nouvelles façons de générer des informations à partir de ces informations. Vous trouverez ci-dessous plusieurs exemples d’utilisation réussie.

## Cas d’utilisation 1 : comparer les mises en oeuvre mobiles et de bureau

> *« Nous avons comparé les accès d’un site à un autre et relevé un certain nombre d’incohérences en termes de balisage. Nous avons évité ainsi des problèmes liés aux données avant la mise sur le marché d’un produit. »*

Un gestionnaire de produit responsable d’un site Web mobile et d’un site Web de bureau a été chargé de s’assurer que les balises sont cohérentes sur les mobiles et les ordinateurs de bureau. Pour s’assurer qu’il n’avait rien manqué d’important, il a utilisé le panneau de comparaison des segments pour comparer les accès provenant de leur site mobile aux accès provenant de leur site de bureau. Il a remarqué qu'il n'y avait pas d'événement de passage en caisse sur le site web mobile et a obtenu les balises correctes avant la publication du site. Les conversions ayant lieu sur le site mobile ont ainsi bien été enregistrées, ce qui a évité un désastre en termes de données.

| Segment 1 | Segment 2 |
|--- |--- |
| Conteneur d’accès pour lequel Type de périphérique mobile est égal à Téléphone mobile ou Tablette | Tous les autres |

## Cas d’utilisation 2 : comparer les clients qui utilisent une certaine fonctionnalité à ceux qui ne le font pas

> *« Nous avons constaté que les clients qui avaient recours à notre fonction de comparaison de produits étaient 10 % plus susceptibles de convertir leur visite en achat. Nous l’avons donc placée en haut de la page et augmenté les commandes de 4 % ! »*

Une équipe d'optimisation de site de vente au détail voulait mieux comprendre les utilisateurs qui interagissaient avec une fonction de comparaison de produits qu'ils avaient récemment publiée. Ils ont utilisé le panneau de comparaison des segments pour comparer les utilisateurs qui ont utilisé la fonction de comparaison des produits à tous les autres utilisateurs du site. Ils ont rapidement identifié plusieurs différences importantes, notamment le fait que ces utilisateurs étaient 10 % plus susceptibles d'acheter un produit. L’équipe d’optimisation du site a alors décidé de placer la fonction de comparaison des produits en haut de la page afin de la tester davantage.

| Segment 1 | Segment 2 |
|--- |--- |
| Conteneur de visiteurs dans lequel existe un événement personnalisé (outil de comparaison de prix) | Tous les autres |

## Cas d’utilisation 3 : comparer les visiteurs du site d'actualités aux visiteurs d'autres sections du site ;

> *« Nous avons constaté que les visiteurs de notre section d’actualités étaient deux fois plus susceptibles de regarder des publicités vidéo. Nous avons donc ajouté d’autres options vidéo à cette section. Nous avons alors enregistré une hausse de 7 % des publicités vidéo regardées ! »*

Une importante société de publication de médias a cherché des moyens d'améliorer l'engagement du contenu pour les publics dans leur section d'actualités. Ils ont créé un segment de visiteurs qui avaient visité la section des actualités afin de mieux comprendre le public. Ils ont immédiatement constaté que ces utilisateurs étaient deux fois plus susceptibles de regarder des publicités vidéo que les visiteurs de toute autre section du site. L'équipe vidéo a mis en place une section vidéo recommandée sur son rail côté actualités et a atteint une augmentation de 7 % des publicités vidéo affichées.

| Segment 1 | Segment 2 |
|--- |--- |
| Conteneur de visiteurs pour lequel la section du site est égale à "Actualités" | Tous les autres |

## Cas d’utilisation 4 : comparer les visiteurs de la recherche payante à tous les autres

> *« Les visiteurs sur notre site issus des moteurs de recherche étaient trois fois plus susceptibles de répondre aux ventes incitatives que les autres. We upped our spend on specific keywords as a result and achieved a 56% increase in up-sells."*

Une grande société de services B2B souhaitait comprendre le type de trafic sur leur site issu des mots-clés de recherche payante. La recherche payante n'avait pas généré beaucoup de conversions directement, et le directeur marketing a envisagé de réduire le budget pour elle. L’équipe marketing a créé un segment de visiteurs venus sur le site par recherche payante et les a comparés à tous les autres visiteurs à l’aide du panneau de comparaison des segments. Ils ont découvert que, même si ces visiteurs étaient moins susceptibles de convertir directement, ils étaient trois fois plus susceptibles de vendre à la hausse sur un service précédemment acheté. L’équipe marketing a concentré son budget sur les mots-clés liés à la vente consécutive et a constaté une augmentation de 56 % des ventes consécutives de services.

| Segment 1 | Segment 2 |
|--- |--- |
| Conteneur de visiteurs pour lequel Type de référent est égal à Recherche payante | Tous les autres |

## Cas d’utilisation 5 : comparer les acheteurs Fitbit à tous les autres

> *« Nous avons constaté que les personnes achetant des objets connectés Fitbit étaient six fois plus susceptibles de recevoir un message « article épuisé » que les autres clients. Nous avons donc commandé plus d’articles Fitbit afin d’éviter les ruptures de stock. »*

Un important détaillant en ligne s'est intéressé à la façon dont l'un des produits de vacances les plus chauds, Fitbit, se vendait et à ce qui rendait les acheteurs Fitbit uniques parmi d'autres clients. En comparant les segments, ils ont constaté que les utilisateurs qui achetaient Fitbits étaient 6 fois plus susceptibles d’obtenir un message "en rupture de stock" que tout autre client. Après une analyse plus approfondie, l'équipe marketing a dirigé ces visiteurs vers leurs magasins de briques et de mortiers pendant qu'ils attendaient leur service d'achat pour commander plus de Fitbits à expédier. En conséquence, le détaillant a évité plus de messages "en rupture de stock" et a répondu à une plus grande partie de sa demande de vacances.

| Segment 1 | Segment 2 |
|--- |--- |
| Conteneur de visiteurs où des commandes existent et dimension personnalisée Marque égale à FitBit | Tous les autres |
