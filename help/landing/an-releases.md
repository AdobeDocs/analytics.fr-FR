---
description: Explique la nouvelle stratégie de mise à jour continue des fonctionnalités pour Adobe Analytics
title: Mises à jour des fonctionnalités Adobe Analytics
exl-id: 1e403bef-4aab-4a9a-a358-62449ce801ff
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 95%

---

# Mises à jour des fonctionnalités Adobe Analytics

Historiquement, les mises à jour des fonctionnalités Adobe Analytics suivaient un calendrier mensuel fixe. Depuis avril 2020, Adobe Analytics a adopté un modèle de diffusion continu qui permet une approche plus évolutive et progressive du déploiement des fonctionnalités.

## Stratégie de mise à jour

[!UICONTROL Analysis Workspace] utilise des indicateurs de fonctionnalité (également appelés « bascules ») pour contrôler la visibilité des nouvelles fonctionnalités, ce qui permet de les tester à échelle contrôlée avant la mise à jour complète. Cette stratégie de mise à jour comprend les phases suivantes :

* **Mise en production** : le code est envoyé en production, mais la visibilité des fonctionnalités est désactivée dans Analysis Workspace. **Remarque** : lors de la mise en production, la fonctionnalité peut être disponible dans l’API Analytics 2.0.

* **Tests limités** : la mise à jour par étapes commence par un test réalisé par les utilisateurs Adobe internes. La visibilité de la mise à jour passe de 0 % à 100 % en quelques mois. Le déploiement par phases se produit au niveau de l’organisation Experience Cloud, de sorte que tous les utilisateurs autorisés d’une même organisation bénéficient de la même expérience.

* **Disponibilité générale** : la fonctionnalité est disponible pour 100 % des organisations Experience Cloud autorisées et la mise à jour est terminée.

Selon les mises à jour de fonctionnalité, la chronologie peut varier entre la mise en production et la disponibilité générale. L’objectif est que la mise à jour soit courte, afin qu’elle atteigne la disponibilité générale dans un délai de 2 mois à compter de la mise en production.

## Indicateurs de fonctionnalités

Les indicateurs de fonctionnalités permettent de contrôler la visibilité des nouvelles fonctionnalités pendant la mise à jour. Adobe recommande d’ajouter app.launchdarkly.com à la [liste autorisée](https://docs.adobe.com/content/help/fr-FR/analytics/technotes/ip-addresses.translate.html) de votre pare-feu pour une expérience optimale lors de la mise à jour. Peu de temps après avoir atteint la disponibilité générale, l’indicateur est retiré.

Vous pouvez à tout moment afficher vos indicateurs de fonctionnalités actifs sous **Aide > À propos de Workspace > Indicateurs de fonctionnalités actifs**.

## Avantages

Les mises à jour par phases permettent à Adobe de mieux adapter le processus de déploiement des logiciels et de s’assurer que les fonctionnalités sont entièrement prêtes avant la disponibilité générale. Cela permet également de mettre les fonctionnalités à disposition tout de suite plutôt que de respecter une fenêtre de mise à jour mensuelle fixe.

## Questions fréquentes

| Question | Réponse |
|---|---|
| Puis-je demander un accès anticipé à une fonctionnalité ? | Non. Aucun accès anticipé ne sera accordé.<br>Si vous voulez tester les concepts Analytics en avant-première, nous vous encourageons à essayer [Adobe Analytics Labs](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/tech-previews/overview.html) pour faire part de vos commentaires sur nos innovations de pointe. |
| Cette stratégie de mise à jour affecte-t-elle mon accès aux fonctionnalités ? | Non. Quand une fonctionnalité atteint la disponibilité générale, vous avez accès à la fonctionnalité à condition qu’elle soit incluse dans votre pack Analytics.<br>Vous pouvez vue les détails de votre package Analytics sous  [!UICONTROL Admin]  >  [!UICONTROL Tous les paramètres]  d’administration >  [!UICONTROL Société > Niveaux d’accès aux ]   [fonctionnalités.](https://docs.adobe.com/content/help/fr-FR/analytics/admin/company-settings/feature-access-levels.html) |
