---
description: Cet exemple présente des appels au serveur émis dans le cadre d’une interaction client type.
keywords: Analytics Implementation
solution: Analytics
subtopic: Visitors
title: Exemple d’identification des visiteurs sur plusieurs périphériques
topic: Developer and implementation
uuid: bc5f8f56-52e3-42d8-af1a-7f5c7b9496c0
translation-type: tm+mt
source-git-commit: 3e2f0bccbe7183ea75b12b1ef2b5afdd87837629

---


# Exemple d’identification des visiteurs sur plusieurs périphériques

> [!IMPORTANT] Cette méthode d’identification des visiteurs sur plusieurs appareils n’est plus recommandée. Reportez-vous à la section Analyses [](/help/components/cda/cda-home.md) sur plusieurs périphériques dans le guide de l’utilisateur Composants.

L’exemple suivant illustre le fonctionnement de l’identification des visiteurs sur plusieurs périphériques à l’aide d’un exemple d’appels serveur envoyés dans le cadre d’une interaction client commune.

| Appel au serveur | Action | Cookie identifiant visiteur | Variable d’identifiant visiteur | Identifiant visiteur effectif | Numéro de page de la visite | Nombre de visites |
|--- |--- |--- |--- |--- |--- |--- |
| 1 | Un visiteur clique sur un lien contenu dans un courrier électronique marketing et consulte votre site à partir de son ordinateur personnel. Ce visiteur a déjà visité votre site 7 fois auparavant. | 1 | - | 1 | 1 | 8 |
| 2-8 | Consulte 7 autres pages de votre site. | 1 | - | 1 | 2-8 | 8 |
| 9 | Authentifie un ordinateur de bureau. | 1 | CID1 | CID1 | 9 <br>(This is CID1's first hit ever, so it takes over and continues on the visitor profile from Visitor ID 1.) | 8 |
| 10 | Visite 1 page supplémentaire. | 1 | CID1 | CID1 | 10 | 8 |
| 11 | Ouvre un site à partir d’un ordinateur portable sur son lieu de travail. Ce visiteur n’a pas visité votre site avant d’utiliser ce périphérique. | 2 | - | 2 | 1 | 1 |
| 12 | Authentifie un ordinateur portable. | 2 | CID1 | CID1 | 1 | 9 |
| 13 | Affiche 1 page supplémentaire. | 2 | CID1 | CID1 | 2 | 9 |

## Comptage des visites

Analytics comptabilise une visite chaque fois qu’il voit un accès avec un numéro de page de visite égal à 1.

En utilisant le tableau ci-dessus, une nouvelle visite a été comptée 4 fois : sur les accès 1, 9, 11 et 12.

## Comptage des visiteurs

Analytics comptabilise chaque identifiant visiteur effectif unique comme un visiteur unique.

À l’aide du tableau ci-dessus, un nouveau visiteur a été compté 3 fois : sur les accès 1, 9 et 10.

Lorsque vous utilisez l’identification des visiteurs sur plusieurs périphériques, le nombre de visiteurs uniques que vous voyez peut augmenter. Le visiteur peut être compté deux fois sur la même visite : une fois pour la visite initiale et une fois de plus après l’authentification de l’utilisateur.

![](assets/visitors.png)

Après l’association initiale, le nombre de visites revient à la normale, car le visiteur est associé par le biais du cookie de son navigateur. Si, par la suite, le visiteur consulte votre site, puis s’authentifie, le nombre de visites n’augmente pas, car l’identifiant visiteur effectif reste inchangé après l’authentification.

![](assets/visitors_2.png)

Veillez à être aussi cohérent que possible lors de l’identification des visiteurs uniques. Par exemple, utilisez toujours la `visitorID` variable lorsque l’utilisateur est authentifié.
