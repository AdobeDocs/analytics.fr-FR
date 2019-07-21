---
description: Questions fréquentes relatives aux fonctionnalités et problèmes liés au transfert côté serveur.
seo-description: Questions fréquentes relatives aux fonctionnalités et problèmes liés au transfert côté serveur.
seo-title: FAQ sur le transfert côté serveur
title: FAQ sur le transfert côté serveur
uuid: ecd 0 bc 9 b-ebf 7-414 e -88 a 2-ebba 3 fd 75 c 92
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# FAQ sur le transfert côté serveur

Questions fréquentes relatives aux fonctionnalités et problèmes liés au transfert côté serveur.

## Serveurs de suivi {#section_28E5BECC2034484AB9726E513F2CCFB7}

| Question | Réponse |
|--- |--- |
| Q : Que se passe-t-il si j’utilise actuellement le transfert côté serveur basé sur un serveur de suivi hérité ? | La méthode de transfert côté serveur basé sur un serveur de suivi hérité continue à transférer les données d’Analytics vers Audience Manager. Cependant, si vous souhaitez envoyer des segments d’Audience Manager vers Analytics, le nouveau transfert côté serveur basé sur une suite de rapports est requis. De plus, il est intéressant d’activer une suite de rapports pour le transfert côté serveur en plus de la configuration de votre serveur de suivi. Le nouveau paramètre de transfert côté serveur de la suite de rapports est utilisé en cas de conflit. |
| Q : Dois-je migrer le transfert côté serveur basé sur un serveur de suivi hérité vers le nouveau transfert côté serveur basé sur une suite de rapports ? | Nous continuons à prendre en charge le transfert côté serveur basé sur un serveur de suivi. Toutefois, si vous souhaitez bénéficier de l’intégration d’Audience Manager à Analytics (partage de segments vers Analytics), vous devez activer le nouveau transfert côté serveur basé sur une suite de rapports pour toutes les suites de rapports applicables. Cependant, il n’y a pas de raison urgente de désactiver le transfert côté serveur basé sur un serveur de suivi hérité. |

## Balisage et création de rapports {#section_71391BA901AC47B9A2286281644FF281}

| Question | Réponse |
|--- |--- |
| Q : Que faire en cas de balisage multi-suite sur mon site ? Le transfert côté serveur double-t-il mes appels serveur à Audience Manager ? | Non, un accès transféré d’Analytics vers Audience Manager n’est transféré qu’une seule fois à Audience Manager, quel que soit le nombre de suites de rapports de l’accès. Si vous disposez de sources de données correspondantes dans Audience Manager pour chaque suite de rapports de l’accès, chacune d’elles est renseignée de manière appropriée à partir de cet accès unique.  Notez, cependant, que si vous utilisez actuellement la collecte de données côté client (DIL) et que vous activez le transfert côté serveur sans installer le module de gestion de l’audience, vous doublez les appels serveur à Audience Manager, quel que soit le nombre de suites de rapports de l’accès Analytics. |
| Q : Que se passe-t-il si j'ai des suites de rapports balisées multi-suite mises en correspondance pour séparer les différentes instances d'Experience Cloud ? | Vous ne devez jamais envoyer de données d'un accès Analytics à deux suites de rapports qui appartiennent à des instances d'Experience Cloud distinctes. Toutefois, si cela se produit, nous transmettrons uniquement l'accès à l'entreprise Experience Cloud correspondant à la configuration du service d'identité sur la page. |
| Q : Que faire si j'ai un balisage multi-suite et qu'une seule de mes Report Suites est mappée sur Mon entreprise Experience Cloud et que l'autre ne l'est pas ? | Nous allons transférer l'accès au serveur de collecte de données correspondant pour l'entreprise Experience Cloud sur votre suite de rapports mappée. Cependant, puisque la suite de rapports non mappée n'aura pas de source de données associée dans Audience Manager, aucune donnée ne sera enregistrée pour la suite de rapports non mappée dans Audience Manager. |
| Q : Que se passe-t-il si j'ai une suite de rapports mappée à plusieurs instances d'Experience Cloud ? | Analytics considère cette suite de rapports comme non mappée et n’autorise pas le transfert côté serveur à être activé pour cette suite de rapports. Contactez le service à la clientèle pour résoudre ce problème de mappage. |
| Q : La méthode de transfert côté serveur basé sur une suite de rapports est-t-elle plus lente que le transfert côté serveur basé sur un serveur de suivi ? | Non, le temps de réponse est le même. |
| Q : Que se passe-t-il si nous disposons de deux instances d'Experience Cloud (ou d'instances AAM) et que vous souhaitez partager des données entre les deux instances d'Experience Cloud ? Puis-je côté serveur transférer un accès Analytics unique à plusieurs instances d'Experience Cloud ? | Non. Si vous devez partager des données collectées sous une entreprise Experience Cloud dans une autre entreprise Experience Cloud, nous vous recommandons d'envoyer toutes les audiences applicables d'une instance Audience Manager à une autre à l'aide du marché d'audience. |
| Q : Le transfert côté serveur entraîne-t-il une facturation supplémentaire dans Audience Manager ou Analytics ? | Dans Analytics, aucune facturation supplémentaire n’est appliquée. Dans Audience Manager, les accès transférés sont traités comme tous les autres accès et facturés.  C’est pourquoi il est important de ne pas activer la collecte de données côté client (DIL) et le transfert côté serveur en même temps, ce qui peut entraîner une double facturation ainsi qu’une duplication des données. |

>[!MORE_LIKE_THIS]
>
>* [Transfert côté serveur](ssf.md#concept_9563FCADF29748928E770EC5221B2685)

