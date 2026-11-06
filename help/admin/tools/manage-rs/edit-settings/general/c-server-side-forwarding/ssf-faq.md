---
description: Questions fréquentes relatives aux fonctionnalités et problèmes liés au transfert côté serveur.
title: Questions fréquentes relatives au transfert côté serveur
feature: Report Suite Settings
exl-id: 63103d2b-e2e8-42da-bdbd-be90abe305f7
role: Admin
TQID: 'https://experienceleague.adobe.com/av541DJd5Ga5QaK2856YBHWW1M-JjkbzRs8JXxYma6c'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
subfeature_v2:
  - id: c354699e-6555-4397-8706-1a9a89984069
    internal-label: Server side forwarding
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
    internal-label: Report Suite settings
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 0ba418a49e6a226540e0791f0138027566022d6f
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 69%
---
# Questions fréquentes relatives au transfert côté serveur

Questions fréquentes relatives aux fonctionnalités et problèmes liés au transfert côté serveur.

## Serveurs de suivi {#section_28E5BECC2034484AB9726E513F2CCFB7}

| Question | Réponse |
|--- |--- |
| Q : Que se passe-t-il si j’utilise actuellement le transfert côté serveur basé sur un serveur de suivi hérité ? | La méthode de transfert côté serveur basé sur un serveur de suivi hérité continue à transférer les données d’Analytics vers Audience Manager. Cependant, si vous souhaitez envoyer des segments d’Audience Manager vers Analytics, le nouveau transfert côté serveur basé sur une suite de rapports est requis. De plus, il n’y a aucun inconvénient à activer une suite de rapports pour le transfert côté serveur en plus de la configuration de votre serveur de suivi. Le nouveau paramètre de transfert côté serveur de la suite de rapports est utilisé en cas de conflit. |
| Q : Dois-je migrer le transfert côté serveur basé sur un serveur de suivi hérité vers le nouveau transfert côté serveur basé sur une suite de rapports ? | Nous continuons à prendre en charge le transfert côté serveur basé sur un serveur de suivi. Toutefois, si vous souhaitez bénéficier de l’intégration d’Audience Manager à Analytics (partage de segments vers Analytics), vous devez activer le nouveau transfert côté serveur basé sur une suite de rapports pour toutes les suites de rapports applicables. Cependant, il n’y a pas de raison urgente de désactiver le transfert côté serveur basé sur un serveur de suivi hérité. |

## Balisage et création de rapports {#section_71391BA901AC47B9A2286281644FF281}

| Question | Réponse |
|--- |--- |
| Q : Que faire en cas de balisage multisuite sur mon site ? Le transfert côté serveur double-t-il mes appels serveur à Audience Manager ? | Non, un hit transféré d’Analytics vers Audience Manager n’est transféré qu’une seule fois à Audience Manager, quel que soit le nombre de suites de rapports du hit. Si vous disposez de sources de données correspondantes dans Audience Manager pour chaque suite de rapports du hit, chacune d’elles est renseignée de manière appropriée à partir de ce hit unique.  Notez, cependant, que si vous utilisez actuellement la collecte de données côté client (DIL) et que vous activez le transfert côté serveur sans installer le module de gestion de l’audience, vous doublez les appels serveur à Audience Manager, quel que soit le nombre de suites de rapports du hit Analytics. |
| Q : Que se passe-t-il si j’ai des suites de rapports balisées sur plusieurs suites qui sont mappées à des organisations Adobe distinctes ? | Vous ne devriez jamais envoyer de données provenant d’un seul accès Analytics vers deux suites de rapports appartenant à des organisations distinctes, mais si cela se produit, nous ne transmettrons l’accès qu’à l’organisation correspondant à la configuration du service d’identification des visiteurs sur la page. |
| Q : Que se passe-t-il si j’ai le balisage multisuite et qu’une seule de mes suites de rapports est mappée à mon organisation, contrairement à l’autre ? | Nous transmettrons l’accès au serveur de collecte de données correspondant à l’organisation sur votre suite de rapports mappée. Toutefois, étant donné que la suite de rapports non mappée n’aura pas de source de données associée dans Audience Manager, aucune donnée ne sera enregistrée pour la suite de rapports non mappée dans Audience Manager. |
| Q : Que se passe-t-il si j’ai une suite de rapports mappée à plusieurs organisations ? | Analytics considère cette suite de rapports comme non mappée et n’autorise pas le transfert côté serveur à être activé pour cette suite de rapports. Contactez l’assistance clientèle pour résoudre ce problème de mappage. |
| Q : La méthode de transfert côté serveur basé sur une suite de rapports est-elle plus lente que le transfert côté serveur basé sur un serveur de suivi ? | Non, le temps de réponse est le même. |
| Q : Que se passe-t-il si nous avons deux organisations (ou instances Adobe Audience Manager) et que nous voulons partager des données entre les deux organisations ? Puis-je transférer un seul accès Analytics côté serveur à plusieurs organisations ? | Non. Si vous devez partager les données collectées sous une organisation avec une autre organisation, nous vous recommandons d’envoyer les audiences applicables d’une instance Audience Manager à une autre à l’aide de la marketplace d’audience. |
| Q : Le transfert côté serveur entraîne-t-il une facturation supplémentaire dans Audience Manager ou Analytics ? | Dans Analytics, aucune facturation supplémentaire n’est appliquée. Dans Audience Manager, les hits transférés sont traités comme tous les autres hits et facturés.  C’est pourquoi il est important de ne pas activer la collecte de données côté client (DIL) et le transfert côté serveur en même temps, ce qui peut entraîner une double facturation ainsi qu’une duplication des données. |

>[!MORELIKETHIS]
>
>* [Transfert côté serveur](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)
