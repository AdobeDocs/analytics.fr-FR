---
title: Cas D’Utilisation De Comparaison De Segments
description: Découvrez des cas d’utilisation concrets sur la manière d’utiliser le panneau de comparaison de segments pour mieux comprendre la stratégie marketing.
keywords: Segment IQ
feature: Segmentation
role: User, Admin
exl-id: d7c02e5c-5313-4e12-86cb-d483644ccbc7
source-git-commit: b4c1636bdc9d5be522b16f945a46beabf4f7a733
workflow-type: tm+mt
source-wordcount: '853'
ht-degree: 15%

---

# Cas d’utilisation de la comparaison de segments

Le panneau de comparaison des segments est une fonctionnalité très utilisée dans Analysis Workspace. Les clients découvrent fréquemment de nouvelles façons d’obtenir des informations avec lors de l’utilisation du panneau. Vous trouverez ci-dessous quelques cas d’utilisation standard

## Cas d’utilisation 1 : comparaison des implémentations mobile et de bureau

> *« Vous avez comparé les accès d’un site à un autre et vous avez rapidement trouvé un certain nombre d’incohérences au niveau des balises. Vous avez ainsi évité des problèmes de données avant la sortie du produit. »*

Vous êtes responsable d’un site web mobile et d’un site web de bureau, et chargé de vous assurer que les balises sont cohérentes sur les appareils mobiles et de bureau. Pour vous assurer de ne rien manquer d’important, utilisez le panneau de comparaison des segments pour comparer les accès provenant de leur site mobile aux accès provenant de leur site de bureau. Notez qu’il n’y a aucun événement de passage en caisse sur le site web mobile et mettez en place les balises appropriées avant que le site mobile ne soit publié. Vous évitez ainsi un sinistre de données dû au fait que le site mobile n’enregistre aucune conversion.

| Segment 1 | Segment 2 |
|--- |--- |
| Conteneur d’accès pour lequel Type d’appareil mobile est égal à Téléphone mobile ou Tablette | Tous les autres |

{style="table-layout:fixed"}


## Cas d’utilisation 2 : comparaison des clients qui utilisent une certaine fonctionnalité avec les clients qui n’en utilisent pas

> *« Vous avez constaté que les clients qui utilisaient votre fonctionnalité de comparaison de produits étaient 10 % plus susceptibles de convertir leur visite en achat. Vous avez déplacé la comparaison des produits en haut de la page et augmenté les commandes de 4 % »*

Une équipe d’optimisation de site de vente au détail souhaite mieux comprendre les utilisateurs et utilisatrices qui interagissent avec une fonctionnalité de comparaison de produits qu’elle a récemment publiée. Il utilise le panneau de comparaison des segments pour comparer les utilisateurs qui utilisent la fonctionnalité de comparaison de produits à tous les autres utilisateurs du site. Ils identifient rapidement plusieurs différences importantes, notamment le fait que ces utilisateurs sont 10 % plus susceptibles d’acheter un produit. L’équipe d’optimisation du site décide de tester la fonctionnalité de comparaison de produits de manière plus visible en haut de la page.

| Segment 1 | Segment 2 |
|--- |--- |
| Conteneur de visiteurs dans lequel il existe un événement personnalisé (outil de comparaison de prix) | Tous les autres |

{style="table-layout:fixed"}


## Cas d’utilisation 3 : comparaison des visiteurs de la section Actualités d’un site par rapport aux visiteurs d’autres sections du site

> *« Vous avez découvert que les visiteurs de votre section d’actualités étaient deux fois plus susceptibles de regarder des publicités vidéo. Vous avez donc ajouté d’autres options vidéo à cette section. Vous avez enregistré une augmentation de 7 % des publicités vidéo visionnées ! »*

Une grande société d’édition multimédia cherche des moyens d’améliorer l’engagement du contenu pour les audiences dans sa section d’actualités. Ils créent un segment de visiteurs qui visitent la section Site d’actualités pour mieux comprendre le public des actualités. Ils constatent immédiatement que ces utilisateurs sont deux fois plus susceptibles de regarder des publicités vidéo que les visiteurs de n’importe quelle autre section du site. L’équipe vidéo a créé une section vidéo recommandée sur son rail latéral d’actualités et a obtenu une augmentation de 7 % du nombre de publicités vidéo visionnées.

| Segment 1 | Segment 2 |
|--- |--- |
| Conteneur de visiteurs pour lequel la section du site est égale à « Actualités » | Tous les autres |

{style="table-layout:fixed"}


## Cas d’utilisation 4 : comparaison des visiteurs issus du référencement payant par rapport aux autres visiteurs

> *« Les visiteurs qui accédaient à votre site à partir de moteurs de recherche étaient trois fois plus susceptibles de vendre leurs produits ou services à un prix supérieur que tout le monde. En conséquence, vous avez augmenté vos dépenses sur des mots-clés spécifiques et obtenu une augmentation de 56 % des ventes incitatives »*

Une grande entreprise de services B2B souhaite comprendre le type de trafic que les mots-clés de référencement payant apportent à son site. Le référencement payant n’a pas directement donné lieu à de nombreuses conversions, et le responsable marketing envisage de réduire son budget. L’équipe marketing crée un segment de visiteurs et visiteuses qui accèdent au site par le biais du référencement payant et compare ce segment à tous les autres visiteurs et visiteuses à l’aide du panneau de comparaison de segments. Ils découvrent que, bien que ces visiteurs ne soient pas aussi susceptibles de convertir directement, ils sont 3 fois plus susceptibles de faire de la vente incitative sur un service acheté précédemment. L&#39;équipe marketing concentre son budget sur les mots-clés liés aux ventes incitatives et constate une augmentation de 56 % des ventes incitatives de services.

| Segment 1 | Segment 2 |
|--- |--- |
| Conteneur de visiteurs pour lequel le type de référent est égal au référencement payant | Tous les autres |

{style="table-layout:fixed"}


## Cas d’utilisation 5 : comparaison des acheteurs d’objets Fitbit par rapport aux autres acheteurs

> *« Vous avez constaté que les personnes qui achetaient des objets connectés Fitbit étaient 6 fois plus susceptibles d’obtenir un message de « rupture de stock » que tout le monde. Donc, vous avez rapidement commandé plus de Fitbits et évité de manquer de stock ! »*

**Scénario :** un important retailer en ligne s’intéresse à la manière dont l’un des produits de vacances les plus prisés - Fitbit - est vendu et à ce qui rend les acheteurs de Fitbit uniques parmi les autres clients. L’équipe marketing peut sélectionner l’élément de ligne Ajuster dans son rapport de produits et exécuter rapidement une analyse de comparaison de segments à partir du menu contextuel. Ce qu&#39;ils découvrent, c&#39;est que les utilisateurs qui achètent des objets connectés Fitbit sont 6 fois plus susceptibles d&#39;obtenir un message de « rupture de stock » que tout autre client. Après une analyse plus approfondie, l&#39;équipe marketing est en mesure d&#39;orienter ces visiteurs vers leurs magasins physiques en attendant que leur service des achats commande d&#39;autres articles Fitbit à expédier. Par conséquent, le retailer évite davantage de messages « en rupture de stock » et peut répondre à une plus grande partie de la demande pendant les vacances.

| Segment 1 | Segment 2 |
|--- |--- |
| Conteneur de visiteurs dans lequel il existe des commandes où la marque Dimension personnalisée est égale à FitBit | Tous les autres |

{style="table-layout:fixed"}