---
description: Explique la nouvelle stratégie de mise à jour continue des fonctionnalités pour Adobe Analytics
title: Mises à jour des fonctionnalités Adobe Analytics
translation-type: tm+mt
source-git-commit: bbbe6dccfee81ae5111f295906aa3a23d68ad39e
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 79%

---


# Mises à jour des fonctionnalités Adobe Analytics

Historiquement, les mises à jour des fonctionnalités Adobe Analytics suivaient un calendrier mensuel fixe. À partir d’avril 2020, Adobe Analytics a adopté un modèle de diffusion continue qui permet une approche plus évolutive et progressive du déploiement des fonctionnalités.

## Stratégie de mise à jour

[!UICONTROL Analysis Workspace] utilise des indicateurs de fonctionnalité (également appelés « bascules ») pour contrôler la visibilité des nouvelles fonctionnalités, ce qui permet de les tester à échelle contrôlée avant la mise à jour complète. Cette stratégie de mise à jour comprend les phases suivantes :

* **Mise en production** : le code est envoyé en production, mais la visibilité des fonctionnalités est désactivée dans Analysis Workspace. **Remarque** : lors de la mise en production, la fonctionnalité peut être disponible dans l’API Analytics 2.0.

* **Tests limités** : la mise à jour par étapes commence par un test réalisé par les utilisateurs Adobe internes. La visibilité de la mise à jour passe de 0 % à 100 % en quelques mois. Le déploiement par phases se produit au niveau de l’organisation Experience Cloud, de sorte que tous les utilisateurs autorisés d’une même organisation bénéficient de la même expérience.

* **Disponibilité générale** : la fonctionnalité est disponible pour 100 % des organisations Experience Cloud autorisées et la mise à jour est terminée.

Selon les mises à jour de fonctionnalité, la chronologie peut varier entre la mise en production et la disponibilité générale. L’objectif est que la mise à jour soit courte, afin qu’elle atteigne la disponibilité générale dans un délai de 2 mois à compter de la mise en production.

## Indicateurs de fonctionnalités

Les indicateurs de fonctionnalités permettent de contrôler la visibilité des nouvelles fonctionnalités au cours de la version. adobe recommande d’ajouter app.launchdarkly.com à la [liste autorisée](https://docs.adobe.com/content/help/en/analytics/technotes/ip-addresses.html) de votre pare-feu pour une expérience optimale lors de la publication. Peu de temps après avoir atteint GA, le drapeau est retiré.

Vous pouvez à tout moment vue vos indicateurs de fonction principaux sous **Aide > A propos de Workspace > Indicateurs** de fonction Principaux.

## Avantages

Les mises à jour par phases permettent à Adobe de mieux adapter le processus de déploiement des logiciels et de s’assurer que les fonctionnalités sont entièrement prêtes avant la disponibilité générale. Cela permet également de mettre les fonctionnalités à disposition tout de suite plutôt que de respecter une fenêtre de mise à jour mensuelle fixe.

## Questions fréquentes

| Question | Réponse |
|---|---|
| Puis-je demander un accès anticipé à une fonctionnalité ? | Non. Aucun accès anticipé ne sera accordé.<br>Si vous voulez tester les concepts Analytics en avant-première, nous vous encourageons à essayer [Adobe Analytics Labs](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/tech-previews/overview.html) pour faire part de vos commentaires sur nos innovations de pointe. |
| Cette stratégie de mise à jour affecte-t-elle mon accès aux fonctionnalités ? | Non. Quand une fonctionnalité atteint la disponibilité générale, vous avez accès à la fonctionnalité à condition qu’elle soit incluse dans votre pack Analytics.<br>Vous pouvez vérifier les détails de votre pack Analytics sous [!UICONTROL Administration] > [!UICONTROL Paramètres de l’entreprise] > [Niveaux d’accès aux fonctionnalités](https://docs.adobe.com/content/help/fr-FR/analytics/admin/company-settings/feature-access-levels.html). |
