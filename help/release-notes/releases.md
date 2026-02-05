---
description: Explique la stratégie de mise à jour continue des fonctionnalités pour Adobe Analytics
title: Mises à jour des fonctionnalités Adobe Analytics
feature: Release Notes
exl-id: 1e403bef-4aab-4a9a-a358-62449ce801ff
source-git-commit: e09234ca27fbf923e026aa1f2ed0ebfed636bf7c
workflow-type: ht
source-wordcount: '394'
ht-degree: 100%

---

# Mises à jour des fonctionnalités Adobe Analytics

Les versions dʼAdobe Analytics suivent un modèle de livraison continue, ce qui permet un déploiement plus flexible et progressif des fonctionnalités.

## Stratégie de mise à jour

[!UICONTROL Analysis Workspace] utilise des indicateurs de fonctionnalité (également appelés « bascules ») pour contrôler la visibilité des nouvelles fonctionnalités, ce qui permet de les tester à échelle contrôlée avant la mise à jour complète. Cette stratégie de mise à jour comprend les phases suivantes :

* **Tests limités** : la mise à jour par étapes commence par un test réalisé par les utilisateurs et utilisatrices internes d’Adobe. Elle est ensuite mise à la disposition d’un petit groupe de comptes clients afin de s’assurer que la fonctionnalité répond aux besoins et aux attentes des clientes et clients.

* **Début du déploiement** : le déploiement d’une mise à jour par phases commence par la phase Tests limités. La mise à jour passe à une disponibilité de 0 % à 100 % pour les clients en quelques mois. Le déploiement par phases se produit au niveau de l’organisation Experience Cloud, de sorte que tous les utilisateurs autorisés d’une même organisation bénéficient de la même expérience.

* **Disponibilité générale** : la fonctionnalité est disponible pour 100 % des organisations Experience Cloud autorisées et la mise à jour est terminée.

Selon les mises à jour de fonctionnalité, la chronologie peut varier entre le début du déploiement et la disponibilité générale. L’objectif est que les mises à jour soient courtes, afin qu’une fonctionnalité atteigne la disponibilité générale dans un délai de 2 mois à compter du début du déploiement.

## Indicateurs de fonctionnalités

Les indicateurs de fonctionnalités permettent de contrôler la visibilité des nouvelles fonctionnalités pendant la mise à jour. Adobe recommande d’ajouter `app.launchdarkly.com` à la [liste autorisée](/help/technotes/ip-addresses.md) de votre pare-feu pour une expérience optimale lors de la mise à jour. Peu de temps après avoir atteint la disponibilité générale, l’indicateur est retiré.

Vous pouvez à tout moment afficher vos indicateurs de fonctionnalités actifs sous **Aide > À propos de Workspace > Indicateurs de fonctionnalités actifs**.

## Avantages

Les mises à jour par phases permettent à Adobe de mieux adapter le processus de déploiement des logiciels et de s’assurer que les fonctionnalités sont entièrement prêtes avant la disponibilité générale. Cela permet également de mettre les fonctionnalités à disposition tout de suite plutôt que de respecter une fenêtre de mise à jour mensuelle fixe.

## Questions fréquentes

| Question | Réponse |
| --- | --- |
| Puis-je demander un accès anticipé à une fonctionnalité ? | Non. Aucun accès anticipé ne sera accordé.<br>Si vous voulez tester les concepts Analytics en avant-première, nous vous encourageons à essayer [Adobe Analytics Labs](/help/analyze/labs.md) pour faire part de vos commentaires sur nos innovations de pointe. |
| Cette stratégie de mise à jour affecte-t-elle mon accès aux fonctionnalités ? | Non. Quand une fonctionnalité atteint la disponibilité générale, vous avez accès à la fonctionnalité à condition qu’elle soit incluse dans votre package Analytics.<br>Vous pouvez vérifier les détails de votre package Analytics sous [Niveaux dʼaccès aux fonctionnalités](/help/admin/tools/company/feature-access-levels.md). |
