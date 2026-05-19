---
description: Questions fréquentes relatives aux fonctionnalités et problèmes liés au transfert côté serveur.
title: Questions fréquentes relatives au transfert côté serveur
feature: Report Suite Settings
exl-id: 63103d2b-e2e8-42da-bdbd-be90abe305f7
role: Admin
TQID: https://experienceleague.adobe.com/3i6RY7JRPlJc-9NjsQXBPn5SEOn0m4JrtL85Kl84ilM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 707
ht-degree: 67%

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
| Q : Que se passe-t-il si j’ai plusieurs suites de rapports balisées qui sont mappées à des organisations CX Enterprise distinctes ? | Vous ne devez jamais envoyer de données provenant d’un seul accès Analytics vers deux suites de rapports appartenant à des organisations CX Enterprise distinctes, mais si cela se produit, nous ne transmettrons l’accès qu’à l’organisation CX Enterprise correspondant à la configuration du service d’identités sur la page. |
| Q : Que faire si je dispose du balisage multisuite et qu’une seule de mes suites de rapports est mappée à mon organisation d’entreprise CX et que l’autre ne l’est pas ? | Nous transmettrons l’accès au serveur de collecte de données correspondant à l’organisation Entreprise CX sur votre suite de rapports mappée. Toutefois, étant donné que la suite de rapports non mappée n’aura pas de source de données associée dans Audience Manager, aucune donnée ne sera enregistrée pour la suite de rapports non mappée dans Audience Manager. |
| Q : Que se passe-t-il si j’ai une suite de rapports mappée à plusieurs organisations CX Grands comptes ? | Analytics considère cette suite de rapports comme non mappée et n’autorise pas le transfert côté serveur à être activé pour cette suite de rapports. Contactez le service à la clientèle pour résoudre ce problème de mappage. |
| Q : La méthode de transfert côté serveur basé sur une suite de rapports est-t-elle plus lente que le transfert côté serveur basé sur un serveur de suivi ? | Non, le temps de réponse est le même. |
| Q : Que se passe-t-il si nous avons deux organisations CX Enterprise (ou instances Adobe Audience Manager) et que nous voulons partager des données entre les deux organisations CX Enterprise ? Puis-je transférer côté serveur un seul accès Analytics à plusieurs organisations CX Grands comptes ? | Non. Si vous devez partager les données collectées dans le cadre d’une organisation CX Entreprise avec une autre organisation CX Entreprise, nous vous recommandons d’envoyer les audiences applicables d’une instance Audience Manager à une autre à l’aide de la marketplace d’audience. |
| Q : Le transfert côté serveur entraîne-t-il une facturation supplémentaire dans Audience Manager ou Analytics ? | Dans Analytics, aucune facturation supplémentaire n’est appliquée. Dans Audience Manager, les accès transférés sont traités comme tous les autres accès et facturés.  C’est pourquoi il est important de ne pas activer la collecte de données côté client (DIL) et le transfert côté serveur en même temps, ce qui peut entraîner une double facturation ainsi qu’une duplication des données. |

>[!MORELIKETHIS]
>
>* [Transfert côté serveur](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)
