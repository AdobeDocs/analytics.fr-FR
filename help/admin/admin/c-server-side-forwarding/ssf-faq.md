---
description: Questions fréquentes relatives aux fonctionnalités et problèmes liés au transfert côté serveur.
title: Questions fréquentes relatives au transfert côté serveur
uuid: ecd0bc9b-ebf7-414e-88a2-ebba3fd75c92
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Questions fréquentes relatives au transfert côté serveur

Questions fréquentes relatives aux fonctionnalités et problèmes liés au transfert côté serveur.

## Serveurs de suivi {#section_28E5BECC2034484AB9726E513F2CCFB7}

| Question | Réponse |
|--- |--- |
| Q : Que se passe-t-il si j’utilise actuellement le transfert côté serveur basé sur un serveur de suivi hérité ? | La méthode de transfert côté serveur basé sur un serveur de suivi hérité continue à transférer les données d’Analytics vers Audience Manager. Cependant, si vous souhaitez envoyer des segments d’Audience Manager vers Analytics, le nouveau transfert côté serveur basé sur une suite de rapports est requis. De plus, il est intéressant d’activer une suite de rapports pour le transfert côté serveur en plus de la configuration de votre serveur de suivi. Le nouveau paramètre de transfert côté serveur de la suite de rapports est utilisé en cas de conflit. |
| Q : Dois-je migrer le transfert côté serveur basé sur un serveur de suivi hérité vers le nouveau transfert côté serveur basé sur une suite de rapports ? | Nous continuons à prendre en charge le transfert côté serveur basé sur un serveur de suivi. Toutefois, si vous souhaitez bénéficier de l’intégration d’Audience Manager à Analytics (partage de segments vers Analytics), vous devez activer le nouveau transfert côté serveur basé sur une suite de rapports pour toutes les suites de rapports applicables. Cependant, il n’y a pas de raison urgente de désactiver le transfert côté serveur basé sur un serveur de suivi hérité. |

## Balisage et création de rapports {#section_71391BA901AC47B9A2286281644FF281}

| Question | Réponse |
|--- |--- |
| Q : Que faire en cas de balisage multi-suite sur mon site ? Le transfert côté serveur double-t-il mes appels serveur à Audience Manager ? | Non, un accès transféré d’Analytics vers Audience Manager n’est transféré qu’une seule fois à Audience Manager, quel que soit le nombre de suites de rapports de l’accès. Si vous disposez de sources de données correspondantes dans Audience Manager pour chaque suite de rapports de l’accès, chacune d’elles est renseignée de manière appropriée à partir de cet accès unique.  Notez, cependant, que si vous utilisez actuellement la collecte de données côté client (DIL) et que vous activez le transfert côté serveur sans installer le module de gestion de l’audience, vous doublez les appels serveur à Audience Manager, quel que soit le nombre de suites de rapports de l’accès Analytics. |
| Q : Que se passe-t-il si je dispose de suites de rapports balisées multi-suite mappées à des organisations Experience Cloud distinctes ? | Vous ne devez jamais envoyer de données provenant d’un seul accès Analytics à deux suites de rapports appartenant à des organisations Experience Cloud distinctes. Mais, si cela se produit, nous ne transférons l’accès que vers l’organisation Experience Cloud correspondant à la configuration du service d’identité de la page. |
| Q : Que se passe-t-il si je dispose d’un balisage multi-suite, que seule une de mes suites de rapports est mappée à mon organisation Experience Cloud et que l’autre ne l’est pas ? | Nous transférons l’accès au serveur de collecte de données correspondant à l’organisation Experience Cloud de la suite de rapports mappée. Toutefois, comme la suite de rapports non mappée ne comporte pas de source de données associée dans Audience Manager, aucune donnée n’est enregistrée pour la suite de rapports non mappée dans Audience Manager. |
| Q : Que faire si je dispose d’une suite de rapports mappée à plusieurs organisations Experience Cloud ? | Analytics considère cette suite de rapports comme non mappée et n’autorise pas le transfert côté serveur à être activé pour cette suite de rapports. Contactez le service à la clientèle pour résoudre ce problème de mappage. |
| Q : La méthode de transfert côté serveur basé sur une suite de rapports est-t-elle plus lente que le transfert côté serveur basé sur un serveur de suivi ? | Non, le temps de réponse est le même. |
| Q : Que se passe-t-il si nous disposons de deux organisations Experience Cloud (ou instances AAM) et que nous souhaitons partager des données entre les deux organisations Experience Cloud ? Puis-je effectuer un transfert côté serveur d’un seul accès Analytics vers plusieurs organisations Experience Cloud ? | Non. Si vous devez partager des données collectées dans une organisation Experience Cloud vers une autre organisation Experience Cloud, il est recommandé d’envoyer les audiences applicables d’une instance Audience Manager vers une autre par l’intermédiaire du marché des audiences. |
| Q : Le transfert côté serveur entraîne-t-il une facturation supplémentaire dans Audience Manager ou Analytics ? | Dans Analytics, aucune facturation supplémentaire n’est appliquée. Dans Audience Manager, les accès transférés sont traités comme tous les autres accès et facturés.  C’est pourquoi il est important de ne pas activer la collecte de données côté client (DIL) et le transfert côté serveur en même temps, ce qui peut entraîner une double facturation ainsi qu’une duplication des données. |

>[!MORELIKETHIS]
>
>* [Transfert côté serveur](/help/admin/admin/c-server-side-forwarding/ssf.md)

