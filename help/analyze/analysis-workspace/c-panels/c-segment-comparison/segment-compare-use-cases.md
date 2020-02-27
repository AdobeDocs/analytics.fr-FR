---
title: Cas d’utilisation de la comparaison de segments
description: Découvrez des cas d’utilisation concrets sur la manière d’utiliser le panneau de comparaison de segments pour mieux comprendre la stratégie marketing.
keywords: Segment IQ
translation-type: ht
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# Cas d’utilisation de Segment IQ

Le panneau de comparaison de segments est une fonctionnalité largement utilisée dans Analysis Workspace. Les clients découvrent fréquemment de nouvelles façons de générer des informations à partir de celui-ci. Vous trouverez ci-dessous plusieurs cas d’utilisation réussie.

## Cas d’utilisation 1 : comparaison des mises en œuvre mobiles et de bureau

> *« Nous avons comparé les accès d’un site à un autre et relevé un certain nombre d’incohérences en termes de balisage. Nous avons évité ainsi des problèmes liés aux données avant la mise sur le marché d’un produit. »*

Un chef de produit responsable d’un site web mobile et d’un site web d’ordinateur de bureau devait s’assurer que les balises des deux types de sites web étaient cohérentes. Afin de s’assurer qu’il n’avait rien omis d’important, il a utilisé le panneau de comparaison de segments afin de comparer les accès issus du site mobile à ceux du site d’ordinateur de bureau. Il a remarqué qu’il n’y avait pas d’événement de passage en caisse sur le site web mobile et a mis en ordre les balises correctes avant la publication du site mobile. Les conversions ayant lieu sur le site mobile ont ainsi bien été enregistrées, ce qui a évité un désastre en termes de données.

| Segment 1 | Segment 2 |
|--- |--- |
| Conteneur d’accès pour lequel Type de périphérique mobile est égal à Téléphone mobile ou Tablette | Tous les autres |

## Cas d’utilisation 2 : comparaison des clients qui utilisent une certaine fonction par rapport à ceux qui ne l’utilisent pas

> *« Nous avons constaté que les clients qui avaient recours à notre fonction de comparaison de produits étaient 10 % plus susceptibles de convertir leur visite en achat. Nous l’avons donc placée en haut de la page et augmenté les commandes de 4 % ! »*

Une équipe chargée de l’optimisation d’un site web de vente au détail cherchait à mieux comprendre les internautes qui utilisaient une nouvelle fonction de comparaison des produits. Elle a utilisé le panneau de comparaison des segments pour comparer les utilisateurs qui ont utilisé la fonction de comparaison des produits à tous les autres utilisateurs du site. Elle a rapidement identifié plusieurs différences notables, notamment le fait que ces utilisateurs étaient 10 % plus susceptibles d’acheter un produit. L’équipe d’optimisation du site a alors décidé de placer la fonction de comparaison des produits en haut de la page afin de la tester davantage.

| Segment 1 | Segment 2 |
|--- |--- |
| Conteneur de visiteurs dans lequel il existe un événement personnalisé (outil de comparaison de prix) | Tous les autres |

## Cas d’utilisation 3 : comparaison des visiteurs de la section Actualités d’un site par rapport aux visiteurs d’autres sections du site

> *« Nous avons constaté que les visiteurs de notre section d’actualités étaient deux fois plus susceptibles de regarder des publicités vidéo. Nous avons donc ajouté d’autres options vidéo à cette section. Nous avons alors enregistré une hausse de 7 % des publicités vidéo regardées ! »*

Une importante société de médias cherchait à optimiser l’engagement du contenu pour les visiteurs de leur section d’actualités. Elle a créé un segment de visiteurs qui avaient visité la section du site d’actualités afin de mieux comprendre le public. Elle a immédiatement constaté que ces utilisateurs avaient deux fois plus de chances de regarder des publicités vidéo que les visiteurs de toute autre section du site. L’équipe vidéo a alors ajouté une section de vidéos recommandées sur son rail des actualités, et a ainsi enregistré une hausse de 7 % des publicités vidéo regardées.

| Segment 1 | Segment 2 |
|--- |--- |
| Conteneur de visiteurs pour lequel la section du site est égale à « Actualités » | Tous les autres |

## Cas d’utilisation 4 : comparaison des visiteurs issus du référencement payant par rapport aux autres visiteurs

> *« Les visiteurs sur notre site issus des moteurs de recherche étaient trois fois plus susceptibles de répondre aux ventes incitatives que les autres. Nous avons donc renforcé nos efforts sur des mots-clés spécifiques et constaté une hausse de 56 % des ventes incitatives. »*

Une grande société de services B2B souhaitait comprendre le type de trafic sur leur site issu des mots-clés de recherche payante. Les recherches payantes n’engendraient pas directement de nombreuses conversions et les responsables du marketing envisageaient de réduire le budget de ce poste. L’équipe marketing a alors créé un segment de visiteurs du site issus d’un référencement payant et l’a comparé, avec le panneau de comparaison des segments, à tous les autres visiteurs. Ils ont constaté que même si ces visiteurs n’étaient pas aussi susceptibles de convertir directement leur visite en achat, ils étaient trois fois plus susceptibles d’acheter la gamme supérieure d’un service déjà acheté. L’équipe marketing a concentré son budget simplement sur les mots-clés liés aux ventes incitatives et a enregistré une hausse de 56 % des ventes incitatives de service.

| Segment 1 | Segment 2 |
|--- |--- |
| Conteneur de visiteurs pour lequel le type de référent est égal au référencement payant | Tous les autres |

## Cas d’utilisation 5 : comparaison des acheteurs d’objets Fitbit par rapport aux autres acheteurs

> *« Nous avons constaté que les personnes achetant des objets connectés Fitbit étaient six fois plus susceptibles de recevoir un message « article épuisé » que les autres clients. Nous avons donc commandé plus d’articles Fitbit afin d’éviter les ruptures de stock. »*

**Scénario :** un grand détaillant en ligne voulait en savoir plus sur la vente d’un des produits phares des fêtes (Fitbit) et déterminer en quoi les acheteurs de Fitbit se distinguaient des autres clients. L’équipe marketing a simplement cliqué avec le bouton droit de la souris sur la ligne « Fitbit » de son rapport des produits, puis a exécuté une analyse rapide avec Segment IQ. Ils ont découvert que les acheteurs des objets connectés Fitbit étaient six fois plus susceptibles de recevoir un message « article épuisé » que n’importe quel autre client. Suite à une analyse plus poussée, l’équipe marketing a réussi à diriger ces visiteurs vers leurs magasins traditionnels en attendant que le service des achats commande davantage d’articles Fitbit. Le détaillant a ainsi évité la multiplication des messages de « rupture de stock » et a pu satisfaire la plus grande partie de la demande des Fêtes.

| Segment 1 | Segment 2 |
|--- |--- |
| Conteneur de visiteurs dans lequel il existe des commandes où la marque Dimension personnalisée est égale à FitBit | Tous les autres |
