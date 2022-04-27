---
description: Explique la stratégie de mise à jour continue des fonctionnalités pour Adobe Analytics
title: Mises à jour des fonctionnalités Adobe Analytics
feature: Release Notes
exl-id: 1e403bef-4aab-4a9a-a358-62449ce801ff
source-git-commit: f6199620033af9c8e304bd0f537d4e0b052ed64d
workflow-type: ht
source-wordcount: '376'
ht-degree: 100%

---

# Mises à jour des fonctionnalités Adobe Analytics

Les versions dʼAdobe Analytics suivent un modèle de livraison continue, ce qui permet un déploiement plus flexible et progressif des fonctionnalités.

## Stratégie de mise à jour

[!UICONTROL Analysis Workspace] utilise des indicateurs de fonctionnalité (également appelés « bascules ») pour contrôler la visibilité des nouvelles fonctionnalités, ce qui permet de les tester à échelle contrôlée avant la mise à jour complète. Cette stratégie de mise à jour comprend les phases suivantes :

* **Mise en production** : le code est envoyé en production, mais la visibilité des fonctionnalités est désactivée dans Analysis Workspace. Cette fonctionnalité est parfois disponible dans lʼAPI Analytics 2.0.

* **Tests limités** : la mise à jour par étapes commence par un test réalisé par les utilisateurs Adobe internes. La visibilité de la mise à jour passe de 0 % à 100 % en quelques mois. Le déploiement par phases se produit au niveau de l’organisation Experience Cloud, de sorte que tous les utilisateurs autorisés d’une même organisation bénéficient de la même expérience.

* **Disponibilité générale** : la fonctionnalité est disponible pour 100 % des organisations Experience Cloud autorisées et la mise à jour est terminée.

Selon les mises à jour de fonctionnalité, la chronologie peut varier entre la mise en production et la disponibilité générale. L’objectif est que la mise à jour soit courte, afin qu’elle atteigne la disponibilité générale dans un délai de 2 mois à compter de la mise en production.

## Indicateurs de fonctionnalités

Les indicateurs de fonctionnalités permettent de contrôler la visibilité des nouvelles fonctionnalités pendant la mise à jour. Adobe recommande d’ajouter `app.launchdarkly.com` à la [liste autorisée](/help/technotes/ip-addresses.md) de votre pare-feu pour une expérience optimale lors de la mise à jour. Peu de temps après avoir atteint la disponibilité générale, l’indicateur est retiré.

Vous pouvez à tout moment afficher vos indicateurs de fonctionnalités actifs sous **Aide > À propos de Workspace > Indicateurs de fonctionnalités actifs**.

## Avantages

Les mises à jour par phases permettent à Adobe de mieux adapter le processus de déploiement des logiciels et de s’assurer que les fonctionnalités sont entièrement prêtes avant la disponibilité générale. Cela permet également de mettre les fonctionnalités à disposition tout de suite plutôt que de respecter une fenêtre de mise à jour mensuelle fixe.

## Questions fréquentes

| Question | Réponse |
| --- | --- |
| Puis-je demander un accès anticipé à une fonctionnalité ? | Non. Aucun accès anticipé ne sera accordé.<br>Si vous voulez tester les concepts Analytics en avant-première, nous vous encourageons à essayer [Adobe Analytics Labs](/help/analyze/labs.md) pour faire part de vos commentaires sur nos innovations de pointe. |
| Cette stratégie de mise à jour affecte-t-elle mon accès aux fonctionnalités ? | Non. Quand une fonctionnalité atteint la disponibilité générale, vous avez accès à la fonctionnalité à condition qu’elle soit incluse dans votre pack Analytics.<br>Vous pouvez vérifier les détails de votre pack Analytics sous [Niveaux dʼaccès aux fonctionnalités](/help/admin/company/feature-access-levels.md). |
